# Hongyu Xiao - Personal Portfolio

A modern, Apple-inspired portfolio website built with Vue 3 + Vite and deployed on GitHub Pages.

## 🚀 Features

- ✨ Clean, minimalist Apple-style design
- 🎨 Smooth animations and transitions
- 📱 Fully responsive layout
- ⚡️ Lightning fast with Vite
- 🔄 Auto-deployment with GitHub Actions

## 🛠️ Tech Stack

- **Framework**: Vue 3
- **Build Tool**: Vite 7
- **Deployment**: GitHub Pages via GitHub Actions
- **Styling**: Pure CSS with modern features

## 📦 Development

### Prerequisites

- Node.js (v18 or higher)
- npm (comes with Node.js)

### Local Development

```bash
# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## 🚢 Deployment

This site automatically deploys to GitHub Pages when you push to the main/master branch.

### Setup GitHub Pages

1. Go to your repository settings
2. Navigate to **Pages** section
3. Under **Source**, select "GitHub Actions"
4. Push your code to trigger the deployment

### Manual Deployment

If you need to deploy manually:

```bash
npm run build
# Then push the dist folder to gh-pages branch
```

## 📁 Project Structure

```
.
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions workflow
├── public/                     # Static assets
├── src/
│   ├── App.vue                # Main application component
│   ├── main.js                # Application entry point
│   └── style.css              # Global styles
├── Figure/                     # Images and photos
├── index.html                 # HTML template
├── vite.config.js             # Vite configuration
└── package.json               # Dependencies and scripts
```

## 🎨 Customization

### Changing Content

Edit `src/App.vue` to update:
- Personal information
- Research experience
- Projects
- Skills
- Photos

### Styling

All styles are in `src/App.vue` using scoped styles. The design system uses CSS variables for easy theming:

```css
:root {
  --bg-primary: #000000;
  --bg-secondary: #ffffff;
  --text-primary: #ffffff;
  --text-secondary: #000000;
  --accent: #0071e3;
}
```

### Adding Images

Place your images in the `Figure/` directory and reference them like:

```vue
<img src="/Figure/your-image.jpg" alt="Description" />
```

## 📝 License

© 2026 Hongyu Xiao. All rights reserved.

## 🔗 Links

- [Live Site](https://xiaoh11.github.io/)
- [LinkedIn](https://www.linkedin.com/in/hongyuxiao12138/)
- [GitHub](https://github.com/xiaoh11)
