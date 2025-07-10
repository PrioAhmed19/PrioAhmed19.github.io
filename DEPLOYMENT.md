# GitHub Pages Deployment Guide

This guide will help you deploy your personal portfolio website to GitHub Pages for free hosting.

## Prerequisites

- A GitHub account
- Basic knowledge of Git (optional but helpful)

## Deployment Options

### Option 1: Direct Upload (Easiest)

1.  **Create a New Repository**
    *   Go to [GitHub](https://github.com) and sign in
    *   Click the "+" icon in the top right corner
    *   Select "New repository"
    *   Name your repository (e.g., `portfolio` or `your-name-portfolio`)
    *   Make sure it's set to "Public"
    *   Check "Add a README file"
    *   Click "Create repository"

2.  **Upload Your Files**
    *   Click "uploading an existing file" link
    *   Drag and drop all files from your portfolio folder
    *   Or click "choose your files" and select all files
    *   Write a commit message like "Add portfolio website"
    *   Click "Commit changes"

3.  **Enable GitHub Pages**
    *   Go to your repository's "Settings" tab
    *   Scroll down to "Pages" in the left sidebar
    *   Under "Source", select "Deploy from a branch"
    *   Choose "main" branch and "/ (root)" folder
    *   Click "Save"
    *   Your site will be available at `https://your-username.github.io/repository-name`

### Option 2: Using GitHub Desktop (Recommended)

1.  **Download GitHub Desktop**
    *   Download from [desktop.github.com](https://desktop.github.com)
    *   Install and sign in with your GitHub account

2.  **Create Repository**
    *   Click "Create a New Repository on your hard drive"
    *   Name: `your-name-portfolio`
    *   Local path: Choose where to save it
    *   Check "Initialize this repository with a README"
    *   Click "Create repository"

3.  **Add Your Files**
    *   Copy all portfolio files to the repository folder
    *   GitHub Desktop will show the changes
    *   Write a summary like "Add portfolio website"
    *   Click "Commit to main"
    *   Click "Publish repository"
    *   Make sure "Keep this code private" is unchecked
    *   Click "Publish repository"

4.  **Enable GitHub Pages**
    *   Go to your repository on GitHub.com
    *   Follow step 3 from Option 1

### Option 3: Using Git Command Line

```bash
# Create a new repository on GitHub first, then:

# Clone the repository
git clone https://github.com/your-username/your-repository-name.git
cd your-repository-name

# Copy your portfolio files
cp -r /path/to/portfolio-files/* .

# Add and commit files
git add .
git commit -m "Add portfolio website"
git push origin main

# Enable GitHub Pages through GitHub.com settings
```

## Custom Domain (Optional)

If you want to use your own domain:

1.  **Purchase a Domain**
    *   Buy from providers like Namecheap, GoDaddy, or Cloudflare

2.  **Configure DNS**
    *   Add these DNS records:
    ```
    Type: A
    Name: @
    Value: 185.199.108.153
    
    Type: A
    Name: @
    Value: 185.199.109.153
    
    Type: A
    Name: @
    Value: 185.199.110.153
    
    Type: A
    Name: @
    Value: 185.199.111.153
    
    Type: CNAME
    Name: www
    Value: your-username.github.io
    ```

3.  **Configure GitHub Pages**
    *   Go to repository Settings → Pages
    *   Under "Custom domain", enter your domain
    *   Check "Enforce HTTPS"
    *   Click "Save"

## Troubleshooting

### Site Not Loading
- Wait 5-10 minutes after enabling GitHub Pages
- Check that your main file is named `index.html`
- Ensure repository is public

### Images Not Showing
- Check image file paths are correct
- Ensure images are in the repository
- Use relative paths (e.g., `assets/images/photo.jpg`)

### CSS/JS Not Loading
- Verify file paths in HTML
- Check for typos in file names
- Ensure files are committed to repository

### 404 Error
- Make sure `index.html` is in the root directory
- Check repository name and GitHub Pages URL
- Verify branch is set to "main" in Pages settings

## Updating Your Site

### How to Modify or Do Any Change

To make changes to your website after it's deployed, you have a few options, depending on how you initially uploaded it:

1.  **Using GitHub.com (Directly in the Browser)**:
    *   Go to your repository on GitHub.com.
    *   Navigate to the file you want to edit (e.g., `index.html`, `styles.css`, or `script.js`).
    *   Click on the file name, then click the pencil icon (edit button) to make changes directly in your browser.
    *   After making your changes, scroll down, add a commit message (e.g., "Updated About Me section"), and click "Commit changes."
    *   GitHub Pages will automatically rebuild and update your site within a few minutes.

2.  **Using GitHub Desktop (Recommended for Larger Changes)**:
    *   If you used GitHub Desktop to set up your repository, open the application.
    *   Make changes to your website files (HTML, CSS, JS, images) directly in your local `refat-portfolio` folder using your preferred text editor.
    *   GitHub Desktop will detect these changes. You'll see a list of modified files.
    *   Write a summary for your changes (e.g., "Added Achievements section").
    *   Click "Commit to main" (or your primary branch).
    *   Then, click "Push origin" to upload these changes to your GitHub repository.
    *   GitHub Pages will automatically rebuild and update your site.

3.  **Using Git Command Line (For Developers)**:
    *   If you're comfortable with Git commands, you can make changes locally using your text editor.
    *   Open your terminal or command prompt, navigate to your `refat-portfolio` directory.
    *   After making changes, use the following commands:
        ```bash
        git add .                 # Stages all changes
        git commit -m "Your descriptive commit message" # Commits changes
        git push origin main      # Pushes changes to GitHub (replace 'main' with your branch name if different)
        ```
    *   Your site will be updated on GitHub Pages automatically.

**Important Note:** After making changes and pushing them to GitHub, it might take a few minutes for GitHub Pages to rebuild and reflect the updates on your live website. If you don't see changes immediately, clear your browser cache or try a different browser.

### Using GitHub.com
1. Go to your repository
2. Click on the file you want to edit
3. Click the pencil icon to edit
4. Make your changes
5. Scroll down and commit changes

### Using GitHub Desktop
1. Make changes to files locally
2. GitHub Desktop will show changes
3. Write commit summary
4. Click "Commit to main"
5. Click "Push origin"

### Using Git Command Line
```bash
# Make your changes, then:
git add .
git commit -m "Update portfolio content"
git push origin main
```

## Performance Tips

1.  **Optimize Images**
    *   Compress images using tools like TinyPNG
    *   Use appropriate formats (JPEG for photos, PNG for graphics)
    *   Consider WebP format for better compression

2.  **Minimize Files**
    *   Remove unused CSS and JavaScript
    *   Minify CSS and JS files for production

3.  **Use CDN for Libraries**
    *   Load Font Awesome and Google Fonts from CDN
    *   This improves loading speed

## Security Best Practices

1.  **Don't Include Sensitive Information**
    *   No API keys or passwords in code
    *   Be careful with personal information

2.  **Keep Dependencies Updated**
    *   Regularly update any libraries used
    *   Monitor for security vulnerabilities

3.  **Use HTTPS**
    *   Always enable "Enforce HTTPS" in GitHub Pages settings

## Analytics (Optional)

To track visitors, add Google Analytics:

1.  Create a Google Analytics account
2.  Get your tracking ID
3.  Add this code before `</head>` in your HTML:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_TRACKING_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag("js", new Date());
  gtag("config", "GA_TRACKING_ID");
</script>
```

## Support

If you need help:
- Check [GitHub Pages documentation](https://docs.github.com/en/pages)
- Visit [GitHub Community](https://github.community)
- Contact: refatahmed@iut-dhaka.edu

---

**Your portfolio will be live and accessible to the world! 🚀**

