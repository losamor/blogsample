# Blog with Netlify CMS

A simple blog with Netlify CMS for easy content management.

## Setup Instructions

### 1. Push Files to GitHub

Upload all these files to your GitHub repository:
- `index.html` (main blog page)
- `admin/config.yml` (Netlify CMS configuration)
- `admin/index.html` (admin interface)
- `posts/` folder (with sample post)

### 2. Configure Netlify

1. **Enable Netlify Identity:**
   - Go to your Netlify dashboard
   - Select your site
   - Go to "Site settings" > "Identity"
   - Click "Enable Identity"

2. **Enable Git Gateway:**
   - In the Identity settings, scroll to "Services"
   - Click "Enable Git Gateway"

3. **Set Registration Preferences:**
   - Go to "Identity" > "Registration"
   - Choose "Invite only" (recommended for security)

### 3. Invite Your Client

1. Go to "Identity" tab in Netlify dashboard
2. Click "Invite users"
3. Enter your client's email address
4. They'll receive an invitation email

### 4. Access the Admin Panel

- Your client can access the admin at: `https://yoursite.netlify.app/admin/`
- They'll log in using the invitation link
- After logging in, they can create, edit, and delete blog posts

### 5. Update the index.html

In `index.html`, find this line:
```javascript
const response = await fetch('https://api.github.com/repos/YOUR_USERNAME/YOUR_REPO/contents/posts');
```

Replace `YOUR_USERNAME` with your GitHub username and `YOUR_REPO` with your repository name.

## How It Works

1. **Creating Posts:** When your client creates a post in `/admin/`, Netlify CMS commits the post (as a markdown file) to your GitHub repository
2. **Automatic Deployment:** GitHub triggers a new build on Netlify
3. **Display:** The blog automatically loads and displays all posts from the `posts/` folder

## File Structure

```
├── index.html              # Main blog page
├── admin/
│   ├── index.html         # Netlify CMS interface
│   └── config.yml         # CMS configuration
├── posts/                 # Blog posts (markdown files)
│   └── 2024-01-30-welcome.md
└── images/
    └── uploads/           # Uploaded images
```

## Customization

- Edit `admin/config.yml` to change post fields or add new content types
- Modify `index.html` styles to match your brand
- Update the CMS configuration to add categories, tags, or other fields

## Notes

- Posts are stored as markdown files in the `posts/` folder
- Images are uploaded to `images/uploads/`
- Each post is automatically committed to GitHub when saved
- The blog refreshes automatically when new posts are added
