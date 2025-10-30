# Sirui (Ray) Chen - Personal Website

A professional portfolio and blog website built with [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

## 🌐 Live Site

Visit the site at: [https://siruiraychen.com](https://siruiraychen.com)

## 📋 About

This website serves as my professional portfolio, showcasing:
- **About Me**: Background in Computer Science and Mathematics
- **Experience**: Work history and teaching experience
- **Projects**: Featured projects in AI, HPC, and full-stack development
- **Blog**: Technical articles and career insights

## 🛠️ Built With

- **Hugo** - Static site generator
- **PaperMod** - Clean and fast Hugo theme
- **GitHub Pages** - Hosting and deployment
- **GitHub Actions** - Automated CI/CD pipeline

## 🚀 Local Development

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.136.5 or later)
- Git

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
   cd YOUR_REPO
   ```

2. Initialize and update submodules:
   ```bash
   git submodule update --init --recursive
   ```

3. Run the development server:
   ```bash
   hugo server -D
   ```

4. Open your browser and visit: `http://localhost:1313`

## 📁 Project Structure

```
.
├── .github/workflows/    # GitHub Actions for deployment
├── content/             # Website content
│   ├── about.md        # About page
│   ├── experience.md   # Work experience
│   ├── projects.md     # Projects showcase
│   └── posts/          # Blog posts
├── static/             # Static assets
│   └── images/         # Images and media
├── themes/             # Hugo themes
│   └── PaperMod/       # PaperMod theme
├── hugo.toml           # Hugo configuration
└── README.md           # This file
```

## 📝 Adding Content

### Create a New Blog Post

```bash
hugo new posts/my-new-post.md
```

Edit the newly created file in `content/posts/` and set `draft: false` when ready to publish.

### Add Images

1. Place images in `static/images/`
2. Reference them in markdown: `![Alt text](/images/filename.jpg)`

## 🚀 Deployment to GitHub Pages

This site uses GitHub Actions for automatic deployment.

### Setup Instructions:

1. **Create a GitHub repository** for your site

2. **Push your code**:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Go to your repository settings
   - Navigate to "Pages" in the left sidebar
   - Under "Build and deployment":
     - Source: Select "GitHub Actions"

4. **Update baseURL**:
   - Edit `hugo.toml`
   - Change `baseURL` to: `https://YOUR_USERNAME.github.io/YOUR_REPO/`
   - Commit and push the change

5. **Deploy**:
   - The GitHub Action will automatically run on push to `main`
   - Check the "Actions" tab to monitor deployment
   - Your site will be live at: `https://YOUR_USERNAME.github.io/YOUR_REPO/`

### Custom Domain (Optional)

To use a custom domain:

1. Add a `CNAME` file in `static/`:
   ```bash
   echo "siruiraychen.com" > static/CNAME
   ```

2. Configure DNS settings with your domain provider:
   - Add an A record pointing to GitHub Pages IPs
   - Or add a CNAME record pointing to `YOUR_USERNAME.github.io`

3. Update `baseURL` in `hugo.toml` to your custom domain

## 🎨 Customization

### Theme Configuration

Edit `hugo.toml` to customize:
- Site title and description
- Navigation menu
- Social media links
- Theme features (reading time, share buttons, etc.)

See [PaperMod documentation](https://github.com/adityatelange/hugo-PaperMod/wiki) for more options.

### Styling

PaperMod supports custom CSS. Create `assets/css/extended/custom.css` to add your styles.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 📧 Contact

**Sirui (Ray) Chen**
- Email: ray_chensirui@hotmail.com
- Website: [siruiraychen.com](https://siruiraychen.com)

## 🙏 Acknowledgments

- [Hugo](https://gohugo.io/) - Fast and flexible static site generator
- [PaperMod](https://github.com/adityatelange/hugo-PaperMod) - Beautiful Hugo theme
- [GitHub Pages](https://pages.github.com/) - Free hosting for static sites
