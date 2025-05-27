# OpenCurve Documentation - Deployment Guide

This document provides instructions for deploying the OpenCurve documentation site to GitHub Pages.

## Prerequisites

- GitHub account
- Git installed on your local machine
- Basic familiarity with Git and GitHub

## Deployment Steps

### 1. Create a GitHub Repository

1. Log in to your GitHub account
2. Create a new repository named `opencurve-docs`
3. Make the repository public

### 2. Push the Documentation to GitHub

From the command line, navigate to the documentation directory and run:

```bash
# Initialize git repository
git init

# Add all files
git add .

# Commit the files
git commit -m "Initial commit of OpenCurve documentation"

# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR-USERNAME/opencurve-docs.git

# Push to GitHub
git push -u origin main
```

### 3. Configure GitHub Pages

1. Go to your repository on GitHub
2. Click on "Settings"
3. Scroll down to the "GitHub Pages" section
4. For "Source", select "GitHub Actions"
5. GitHub will automatically detect and suggest the Jekyll workflow
6. Click on "Configure" and commit the workflow file

GitHub will now build and deploy your site automatically. The site will be available at:
`https://YOUR-USERNAME.github.io/opencurve-docs/`

### 4. Custom Domain (Optional)

If you want to use a custom domain:

1. In your repository settings, go to the "GitHub Pages" section
2. Under "Custom domain", enter your domain name (e.g., docs.opencurve.fun)
3. Click "Save"
4. Configure your DNS provider by adding a CNAME record pointing to `YOUR-USERNAME.github.io`

## Local Development

To develop and test the documentation locally:

1. Install Ruby and Jekyll:
   ```bash
   # Install Ruby (if not already installed)
   # For Ubuntu/Debian:
   sudo apt-get install ruby-full build-essential

   # For macOS (using Homebrew):
   brew install ruby
   ```

2. Install Bundler and dependencies:
   ```bash
   cd opencurve-docs
   gem install bundler
   bundle install
   ```

3. Run the local server:
   ```bash
   bundle exec jekyll serve
   ```

4. View the site at `http://localhost:4000/opencurve-docs/`

## Updating the Documentation

To update the documentation after making changes:

1. Commit your changes:
   ```bash
   git add .
   git commit -m "Update documentation"
   ```

2. Push to GitHub:
   ```bash
   git push
   ```

GitHub Actions will automatically rebuild and deploy your site.

## Troubleshooting

- If your site isn't building, check the Actions tab in your GitHub repository for error messages
- Make sure your repository is public for GitHub Pages to work
- If you're using a custom theme, ensure it's compatible with GitHub Pages
- Check that your _config.yml has the correct baseurl setting
