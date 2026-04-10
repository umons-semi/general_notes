# General Notes - general_notes


# Adding Collaborators

Here's the step-by-step process to add collaborators to your repository on GitHub:
Step-by-Step Instructions

1. Go to your repository on GitHub.com
2. Click "Settings" (the gear icon tab near the top of the repository page)
3. In the left sidebar, click "Collaborators" under the "Access" section
4. Click "Add people" (green button)
5. Enter their GitHub username or email address in the search field
6. Select the appropriate role for the collaborator (Read, Triage, Write, Maintain, or Admin)
7. Click "Add [username] to repository"

The person you invited will receive an email invitation and must accept it before they can access and contribute to your repository.

## Understanding Permission Levels

Here are the roles you can assign to collaborators:

| Role | What They Can Do |
|------|------------------|
| Read | View and clone the repository only |
| Triage | Manage issues and pull requests, but cannot push code |
| Write | Push to branches, create pull requests, and merge changes |
| Maintain | Manage repository settings without full admin access |
| Admin | Full control, including adding/removing collaborators |
 
## Important Notes

- You must have admin access to the repository to add collaborators
- The collaborator needs a GitHub account to accept the invitation
- Invitations can be viewed and accepted at https://github.com/notifications or through email
- For public repositories, people can contribute via pull requests without being added as collaborators

Once they accept, your collaborators can push changes to the repository just like you can (depending on their permission level). For better collaboration practices, consider having them work on feature branches and use pull requests rather than committing directly to the main branch.

# Adding Videos to the repository

Yes, you can add videos to GitHub, but there are important size limits and a few different ways to do it depending on where you want the video to appear.

## Quick Answer: Two Main Ways to Add Videos

| Method | Best For | Size Limit (Free) | Can Embed? |
|--------|----------|------------------|-------------|
| **Upload to repo** | Storing video files in your repository | 10MB  | Limited browser support |
| **Upload to issue/PR** | Getting a playable link for READMEs | 10MB  | Yes, with `<video>` tag |

---

## Method 1: Upload Video to Your Repository

You can add video files just like any other file in your repository:

```bash
# Add video file to your repo
git add my-video.mp4
git commit -m "Add demo video"
git push origin main
```

**Size Limits by Plan** :
- **Free plan**: 10MB per video
- **Paid plan**: 100MB per video

> ⚠️ **Warning**: Git wasn't designed for large files. Adding multiple videos can bloat your repository and slow down clones .

---

## Method 2: Upload via Issue or Pull Request (Recommended for Embedding)

This is the best way to get a video that plays inline in your README or documentation :

1. **Go to Issues or Pull Requests** tab in your repository
2. **Create a new issue or PR** (you can close it right after)
3. **Drag and drop** your video file into the comment box
4. GitHub uploads it and gives you a URL like:  
   `https://github.com/user/repo/files/1234567/my-video.mp4`
5. **Copy that URL** and use it in your README

---

## How to Embed Video in README or Markdown

Once you have a video URL (from an issue upload), use HTML tags in your Markdown :

```html
<video width="640" height="360" controls>
  <source src="https://github.com/your-username/your-repo/files/1234567/video.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```

Or just link to it:
```markdown
[Watch the demo video](https://github.com/your-username/your-repo/files/1234567/video.mp4)
```

> 💡 **Tip**: Use `controlsList="nodownload"` in the `<video>` tag to hide the download button (though tech-savvy users can still download it) .

---

## For Large Videos (>100MB): Use Git LFS

If you need to track large video files in your repository, use **Git LFS (Large File Storage)** :

```bash
# Install Git LFS
git lfs install

# Track video files
git lfs track "*.mp4"
git add .gitattributes

# Add and push as usual
git add my-large-video.mp4
git commit -m "Add large video with LFS"
git push origin main
```

**Git LFS Limits on Free Plan** :
- **Storage**: 1GB total across all repositories
- **Bandwidth**: 1GB per month free
- **File size**: Up to 2GB per file

---

## Alternative: Host Elsewhere and Embed

Given the limitations, many developers prefer to :

- **Upload to YouTube/Vimeo** (unlisted if needed)
- **Take a screenshot thumbnail**
- **Link the thumbnail to the external video**

```markdown
[![Video thumbnail](thumbnail.png)](https://youtu.be/your-video-link)
```

This approach:
- Keeps your repository lightweight
- Gives you full video controls
- Works reliably across all browsers

---

## Summary Table

| Your Need | Recommended Approach |
|-----------|---------------------|
| Small demo video (<10MB) | Upload directly to repo |
| Medium video, want it in README | Upload to issue, embed with `<video>` tag |
| Large video file (>100MB) | Use Git LFS |
| Professional project showcase | Host on YouTube/Vimeo, embed link |
| Full download protection | Not possible on public GitHub  |

The issue-upload method is usually the sweet spot—you get a playable embedded video without bloating your repository or hitting size limits.




