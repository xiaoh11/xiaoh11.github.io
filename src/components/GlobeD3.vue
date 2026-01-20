<template>
  <div class="globe-container">
    <svg ref="globeSvg" class="globe-svg"></svg>
  </div>
</template>

<script>
import * as d3 from 'd3';
import { feature } from 'topojson-client';

export default {
  name: 'GlobeD3',
  data() {
    return {
      width: 500,
      height: 500,
      projection: null,
      path: null,
      svg: null,
      globe: null,
      rotating: false,
      montrealCoords: [-73.5673, 45.5017],
      hasAnimated: false
    }
  },
  mounted() {
    this.initGlobe();
    this.setupIntersectionObserver();
    window.addEventListener('resize', this.handleResize);
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.handleResize);
  },
  methods: {
    async initGlobe() {
      const container = this.$refs.globeSvg;
      if (!container) return;

      const rect = container.getBoundingClientRect();
      this.width = rect.width;
      this.height = rect.height;

      this.projection = d3.geoOrthographic()
        .scale(Math.min(this.width, this.height) / 2.2)
        .translate([this.width / 2, this.height / 2])
        .clipAngle(90);

      this.path = d3.geoPath().projection(this.projection);

      this.svg = d3.select(container)
        .attr('width', this.width)
        .attr('height', this.height);

      const defs = this.svg.append('defs');
      
      const gradient = defs.append('radialGradient')
        .attr('id', 'sphere-gradient')
        .attr('cx', '35%')
        .attr('cy', '35%');
      
      gradient.append('stop')
        .attr('offset', '0%')
        .attr('stop-color', '#ffffff');
      
      gradient.append('stop')
        .attr('offset', '100%')
        .attr('stop-color', '#e0e0e0');

      this.globe = this.svg.append('g');

      this.globe.append('circle')
        .attr('cx', this.width / 2)
        .attr('cy', this.height / 2)
        .attr('r', this.projection.scale() * 1.05)
        .attr('class', 'globe-glow');

      this.globe.append('path')
        .datum({ type: 'Sphere' })
        .attr('class', 'sphere')
        .attr('d', this.path);

      const graticule = d3.geoGraticule();
      this.globe.append('path')
        .datum(graticule)
        .attr('class', 'graticule')
        .attr('d', this.path);

      try {
        const worldData = await d3.json('https://cdn.jsdelivr.net/npm/world-atlas@2/countries-110m.json');
        const countries = feature(worldData, worldData.objects.countries);
        
        this.globe.append('g')
          .selectAll('path')
          .data(countries.features)
          .enter()
          .append('path')
          .attr('class', 'country')
          .attr('d', this.path);
        
      } catch (error) {
        console.log('Using simple sphere without countries');
      }

      this.addMarker(this.montrealCoords[0], this.montrealCoords[1], 'Montreal, QC');

      this.updateMarkerPosition();

      this.startRotation();
    },

    addMarker(lon, lat, label) {
      const markerGroup = this.globe.append('g')
        .attr('class', 'marker-group')
        .attr('opacity', 0);

      markerGroup.append('circle')
        .attr('class', 'marker-dot')
        .attr('r', 3);

      markerGroup.append('circle')
        .attr('class', 'marker-pulse')
        .attr('r', 3);

      markerGroup.append('text')
        .attr('class', 'marker-label')
        .text(label);

      this.updateMarkerPosition();

      return markerGroup;
    },

    startRotation() {
    },

    updateMarkerPosition() {
      const coords = this.projection(this.montrealCoords);
      
      const isVisible = coords !== null;
      
      if (isVisible) {
        this.globe.selectAll('.marker-dot, .marker-pulse')
          .attr('transform', `translate(${coords[0] - 55},${coords[1]})`);
        
        this.globe.selectAll('.marker-label')
          .attr('transform', `translate(${coords[0] - 38},${coords[1] + 6})`);
      }
    },

    setupIntersectionObserver() {
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting && !this.hasAnimated) {
            this.rotateToMontreal();
            this.hasAnimated = true;
          }
        });
      }, { threshold: 0.3 });
      
      if (this.$refs.globeSvg) {
        observer.observe(this.$refs.globeSvg);
      }
    },

    rotateToMontreal() {
      this.rotating = false;
      
      const targetRotation = [73.5673, -45.5017, 0];
      const currentRotation = this.projection.rotate();
      const initialScale = this.projection.scale();
      const targetScale = initialScale * 5;
      
      const duration = 3000;
      const startTime = Date.now();
      
      const animate = () => {
        const elapsed = Date.now() - startTime;
        const progress = Math.min(elapsed / duration, 1);
        
        const eased = progress < 0.5
          ? 4 * progress * progress * progress
          : 1 - Math.pow(-2 * progress + 2, 3) / 2;
        
        const rotation = [
          currentRotation[0] + (targetRotation[0] - currentRotation[0]) * eased,
          currentRotation[1] + (targetRotation[1] - currentRotation[1]) * eased
        ];
        this.projection.rotate(rotation);
        
        const scaleProgress = progress < 0.5 ? 0 : (progress - 0.5) * 2;
        const scaleEased = scaleProgress * scaleProgress * scaleProgress;
        const currentScale = initialScale + (targetScale - initialScale) * scaleEased;
        this.projection.scale(currentScale);
        
        this.globe.selectAll('path').attr('d', this.path);
        this.updateMarkerPosition();
        
        this.globe.select('.globe-glow')
          .attr('r', currentScale * 1.05);
        
        if (progress < 1) {
          requestAnimationFrame(animate);
        } else {
          this.globe.select('.marker-group')
            .transition()
            .duration(800)
            .attr('opacity', 1);
        }
      };
      
      animate();
    },

    handleResize() {
      const container = this.$refs.globeSvg;
      if (!container) return;

      const rect = container.getBoundingClientRect();
      this.width = rect.width;
      this.height = rect.height;

      if (this.projection) {
        this.projection
          .scale(Math.min(this.width, this.height) / 2.2)
          .translate([this.width / 2, this.height / 2]);
      }

      if (this.svg) {
        this.svg
          .attr('width', this.width)
          .attr('height', this.height);
        
        this.globe.selectAll('path').attr('d', this.path);
        
        this.globe.select('.globe-glow')
          .attr('cx', this.width / 2)
          .attr('cy', this.height / 2)
          .attr('r', this.projection.scale() * 1.05);
        
        this.updateMarkerPosition();
      }
    }
  }
}
</script>

<style scoped>
.globe-container {
  width: 100%;
  height: 500px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 3rem 0;
  background: transparent;
  border-radius: 20px;
  overflow: visible;
}

.globe-svg {
  width: 100%;
  height: 100%;
}

.globe-svg canvas {
  display: block;
}

:deep(.sphere) {
  fill: url(#sphere-gradient);
  stroke: none;
}

:deep(.globe-glow) {
  fill: rgba(200, 200, 200, 0.15);
  filter: blur(25px);
}

:deep(.graticule) {
  fill: none;
  stroke: rgba(200, 200, 200, 0.25);
  stroke-width: 0.5;
}

:deep(.country) {
  fill: #c0c0c0;
  stroke: rgba(150, 150, 150, 0.4);
  stroke-width: 0.5;
  transition: fill 0.3s;
}

:deep(.country:hover) {
  fill: #b0b0b0;
}

:deep(.marker-dot) {
  fill: #ff3333;
  stroke: #fff;
  stroke-width: 2;
  filter: drop-shadow(0 0 8px rgba(255, 51, 51, 0.8));
  animation: markerPulse 2s ease-in-out infinite;
}

:deep(.marker-pulse) {
  fill: none;
  stroke: #ff3333;
  stroke-width: 2;
  opacity: 0.6;
  animation: pulseExpand 2s ease-out infinite;
}

:deep(.marker-label) {
  fill: white;
  font-size: 16px;
  font-weight: 600;
  text-anchor: start;
  pointer-events: none;
  text-shadow: 0 0 6px rgba(0, 0, 0, 0.8), 0 0 12px rgba(0, 0, 0, 0.6);
}

@keyframes markerPulse {
  0%, 100% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.2);
    opacity: 0.8;
  }
}

@keyframes pulseExpand {
  0% {
    transform: scale(1);
    opacity: 0.6;
  }
  100% {
    transform: scale(2.5);
    opacity: 0;
  }
}

@media (max-width: 768px) {
  .globe-container {
    height: 400px;
    margin: 2rem 0;
  }
}
</style>
