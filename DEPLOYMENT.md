# Deployment Guide for GitHub Pages

This guide will walk you through deploying your Hugo site to GitHub Pages.

## Prerequisites

- A GitHub account
- Git installed on your computer
- Your Hugo site ready (which you already have!)

## Step-by-Step Deployment

### 1. Prepare Your Repository

First, make sure you're in your project directory:

```bash
cd /Users/RayChen/quickstart
```

### 2. Initialize Git Repository (if not already done)

```bash
git init
git branch -M main
```

### 3. Create a .gitignore File

The `.gitignore` file is already created for you. It excludes unnecessary files from Git.

### 4. Add Your Files

```bash
git add .
git commit -m "Initial commit: Hugo site with PaperMod theme"
```

### 5. Create a GitHub Repository

1. Go to [GitHub](https://github.com) and log in
2. Click the "+" icon in the top right corner
3. Select "New repository"
4. Choose a repository name (e.g., `portfolio` or `siruiraychen.github.io`)
   - **Important**: If you name it `YOUR_USERNAME.github.io`, your site will be at `https://YOUR_USERNAME.github.io/`
   - Otherwise, it will be at `https://YOUR_USERNAME.github.io/REPO_NAME/`
5. **Do NOT initialize with README, .gitignore, or license** (we already have these)
6. Click "Create repository"

### 6. Connect Your Local Repository to GitHub

Replace `YOUR_USERNAME` and `YOUR_REPO` with your actual GitHub username and repository name:

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

### 7. Push the PaperMod Theme Submodule

```bash
git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
git add .gitmodules themes/PaperMod
git commit -m "Add PaperMod theme as submodule"
git push
```

### 8. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" (top right)
3. In the left sidebar, click "Pages"
4. Under "Build and deployment":
   - **Source**: Select "GitHub Actions"

### 9. Update Your baseURL

Edit `hugo.toml` and update the `baseURL`:

**Option A - If you named your repo `YOUR_USERNAME.github.io`:**
```toml
baseURL = 'https://YOUR_USERNAME.github.io/'
```

**Option B - If you used a different repo name:**
```toml
baseURL = 'https://YOUR_USERNAME.github.io/YOUR_REPO/'
```

Then commit and push:
```bash
git add hugo.toml
git commit -m "Update baseURL for GitHub Pages"
git push
```

### 10. Wait for Deployment

1. Go to the "Actions" tab in your GitHub repository
2. You should see a workflow running
3. Wait for it to complete (usually takes 1-2 minutes)
4. Once complete, your site will be live!

### 11. Visit Your Site

Your site will be available at:
- `https://YOUR_USERNAME.github.io/` (if repo name is `YOUR_USERNAME.github.io`)
- `https://YOUR_USERNAME.github.io/YOUR_REPO/` (for other repo names)

## 🎉 Troubleshooting

### Issue: 404 Page Not Found

**Solution**: Check your `baseURL` in `hugo.toml` matches your GitHub Pages URL exactly.

### Issue: Theme Not Loading

**Solution**: Make sure the submodule is properly initialized:
```bash
git submodule update --init --recursive
git add .
git commit -m "Update submodules"
git push
```

### Issue: GitHub Action Fails

**Solution**: Check the Actions tab for error messages. Common issues:
- Make sure the theme is added as a submodule
- Verify `hugo.toml` syntax is correct

## 📝 Making Updates

After your initial deployment, updating your site is easy:

1. Make your changes locally
2. Test with `hugo server -D`
3. Commit and push:
   ```bash
   git add .
   git commit -m "Description of changes"
   git push
   ```
4. GitHub Actions will automatically rebuild and deploy your site!

## 🌐 Custom Domain (Optional)

If you want to use your own domain (like siruiraychen.com):

1. Create a file `static/CNAME` with your domain:
   ```bash
   echo "siruiraychen.com" > static/CNAME
   ```

2. Update `baseURL` in `hugo.toml`:
   ```toml
   baseURL = 'https://siruiraychen.com/'
   ```

3. Configure DNS with your domain registrar:
   - Add an A record pointing to GitHub's IPs:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153
   
4. In GitHub Settings → Pages, add your custom domain

5. Commit and push your changes

## ✅ Checklist

Before deploying, make sure you have:

- [ ] Created all content pages (About, Projects, Experience)
- [ ] Added at least 2 blog posts
- [ ] Added your images to `static/images/`
- [ ] Updated `hugo.toml` with correct information
- [ ] Tested locally with `hugo server -D`
- [ ] Created GitHub repository
- [ ] Pushed code to GitHub
- [ ] Enabled GitHub Pages with GitHub Actions
- [ ] Updated `baseURL` in `hugo.toml`
- [ ] Verified deployment in Actions tab
- [ ] Visited your live site!

## 🆘 Need Help?

If you encounter issues:
1. Check the [Hugo documentation](https://gohugo.io/documentation/)
2. Review [PaperMod wiki](https://github.com/adityatelange/hugo-PaperMod/wiki)
3. Look at [GitHub Pages docs](https://docs.github.com/en/pages)

Good luck with your deployment! 🚀
