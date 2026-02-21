# Quickstart Guide: Docusaurus Documentation Site

## Prerequisites
- Node.js (version 18.0 or higher)
- npm or yarn package manager
- Git for version control

## Setup Instructions

### 1. Install Docusaurus
```bash
npm init docusaurus@latest website classic
```

### 2. Navigate to Project Directory
```bash
cd website
```

### 3. Start Development Server
```bash
npm start
```

This will start a local development server at http://localhost:3000

## Project Structure
```
website/
├── blog/           # Blog posts (optional)
├── docs/           # Documentation files
├── src/
│   ├── components/ # React components
│   ├── css/        # Global styles
│   └── pages/      # Additional pages
├── static/         # Static assets
├── docusaurus.config.js  # Site configuration
├── sidebars.js     # Sidebar navigation
└── package.json    # Dependencies
```

## Creating Content

### Add a New Document
1. Create a new `.md` file in the `docs/` directory
2. Add frontmatter at the top:
```markdown
---
sidebar_label: 'Document Title'
sidebar_position: 1
description: 'Brief description'
---
```

### Organize in Sidebars
Edit `sidebars.js` to add your document to navigation:
```javascript
module.exports = {
  docs: [
    {
      type: 'category',
      label: 'Module 1',
      items: ['module1/chapter1', 'module1/chapter2', 'module1/chapter3'],
    },
  ],
};
```

## Configuration

### Basic Site Configuration
Edit `docusaurus.config.js`:
```javascript
module.exports = {
  title: 'Your Site Title',
  tagline: 'Your site tagline',
  url: 'https://your-site.example.com',
  baseUrl: '/',
  // ... other config
};
```

## Building for Production
```bash
npm run build
```

The build output will be in the `build/` directory, ready for deployment.

## Running Tests
```bash
npm run serve  # Serve built site locally
```