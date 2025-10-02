# Tech Topics Blog

A GitHub Pages tech blog built with Jekyll for sharing technical content and insights.

## Features

- Jekyll-based static site generator
- Automatic deployment to GitHub Pages via GitHub Actions
- Convenient script for creating new posts
- Responsive design using the Minima theme
- RSS feed support

## Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/MrBaoDK/blog.git
   cd blog
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Run locally:
   ```bash
   bundle exec jekyll serve
   ```
   
   The site will be available at `http://localhost:4000`

## Creating New Posts

Use the `bin/newpost` script to create a new blog post:

```bash
bin/newpost "Your Post Title"
```

This will create a new file in `_posts/` with the current date and a URL-friendly slug based on your title. The file will include YAML front matter with:
- `layout: post`
- `title: "Your Post Title"`
- `date: YYYY-MM-DD HH:MM:SS TIMEZONE`
- `tags: []`

### Example

```bash
bin/newpost "Getting Started with Docker"
```

This creates `_posts/2025-10-02-getting-started-with-docker.md` with pre-filled front matter.

## Writing Posts

1. Open the generated file in `_posts/`
2. Edit the front matter to add relevant tags:
   ```yaml
   tags: [docker, containers, devops]
   ```
3. Write your content in Markdown below the front matter
4. Save the file

## Deployment

The blog automatically deploys to GitHub Pages when you push to the `main` branch:

1. Add and commit your changes:
   ```bash
   git add .
   git commit -m "Add new post"
   ```

2. Push to GitHub:
   ```bash
   git push origin main
   ```

3. GitHub Actions will automatically build and deploy your site to GitHub Pages

## GitHub Pages Configuration

To enable GitHub Pages for this repository:

1. Go to repository **Settings** → **Pages**
2. Under **Source**, select **GitHub Actions**
3. The site will be published at `https://mrbaoDK.github.io/blog/`

## File Structure

```
.
├── _config.yml           # Jekyll configuration
├── _posts/              # Blog posts (markdown files)
│   └── YYYY-MM-DD-title.md
├── _site/               # Generated site (git-ignored)
├── bin/
│   └── newpost          # Script to create new posts
├── .github/
│   └── workflows/
│       └── publish.yml  # GitHub Actions workflow
├── index.md             # Homepage
├── Gemfile              # Ruby dependencies
└── README.md            # This file
```

## Customization

### Site Configuration

Edit `_config.yml` to customize:
- Site title and description
- URL and baseurl
- Theme settings
- Plugins

### Theme

The default theme is [Minima](https://github.com/jekyll/minima). You can customize it by:
- Overriding layouts in `_layouts/`
- Overriding includes in `_includes/`
- Adding custom CSS in `assets/css/`

## Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Markdown Guide](https://www.markdownguide.org/)

## License

This blog repository is open source and available under the MIT License.
