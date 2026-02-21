---
sidebar_position: 99
title: "Contributing to Documentation"
---

# Contributing to Documentation

Thank you for your interest in contributing to the Hackathon Book Creation documentation! This guide will help you understand how to contribute effectively to our documentation.

## Getting Started

1. Fork the repository
2. Clone your fork locally
3. Create a new branch for your changes
4. Make your changes to the documentation files
5. Test your changes locally (see Development section below)
6. Submit a pull request

## Documentation Structure

Our documentation is organized as follows:

- **Module 1**: ROS 2 Middleware for Humanoid Robotics
  - Introduction
  - Chapter 1: Introduction to ROS 2 Architecture
  - Chapter 2: Python Integration with rclpy
  - Chapter 3: URDF Applications for Humanoid Robots

## Writing Documentation

### File Format

All documentation files are written in Markdown format with Docusaurus-specific frontmatter:

```markdown
---
sidebar_position: 1
title: "Your Page Title"
---

# Your Main Heading

Your content here...
```

### Frontmatter Properties

- `sidebar_position`: Controls the order of the page in the sidebar (lower numbers appear first)
- `title`: The title of the page that appears in the browser tab and sidebar

### Best Practices

- Use proper heading hierarchy (#, ##, ###)
- Include code examples where relevant
- Use descriptive alt text for images
- Keep paragraphs concise
- Use bullet points and numbered lists appropriately

## Development

To run the documentation site locally:

1. Navigate to the `website` directory
2. Install dependencies: `npm install`
3. Start the development server: `npm start`
4. Visit `http://localhost:3000` in your browser

## Building for Production

To build the site for production:

1. Navigate to the `website` directory
2. Run: `npm run build`
3. The built site will be in the `build` directory

## Style Guide

- Write in clear, concise language
- Use active voice when possible
- Be consistent with terminology
- Follow accessibility guidelines
- Test code examples to ensure they work