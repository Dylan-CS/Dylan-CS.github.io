# Dylan's Portfolio

A minimalist personal portfolio and blog.

## Stack

Pure HTML/CSS/JS - no frameworks, no build tools.

## Architecture

```
/
├── index.html          # Main page (loads posts from posts.json)
├── post.html           # Single post template (renders content dynamically)
├── posts.json          # All posts data (date, title, url, content)
├── archives/           # Archive page
├── css/                # Styles
├── images/             # Assets
└── _posts/             # Markdown source (for reference)
```

## How It Works

- **index.html** - Fetches `/posts.json` and renders blog list + latest updates
- **post.html** - Takes `?date=YYYY-MM-DD` parameter, fetches post content from `/posts.json` and renders dynamically
- **posts.json** - Single source of truth containing all posts

## Content Format

```json
{
  "date": "2024-01-15",
  "title": "Post Title",
  "url": "/post.html?date=2024-01-15",
  "content": "<p>HTML content...</p>"
}
```

## URL Structure

Old format: `/2023/01/19/` (static HTML)
New format: `/post.html?date=2023-01-19` (JS rendered)

## Add New Post

1. Add entry to `posts.json`
2. That's it!

## Development

Just open `index.html` in a browser (or use a local server for CORS).

```bash
python3 -m http.server 8000
```

## Deploy

Push to GitHub Pages or connect to Vercel.
