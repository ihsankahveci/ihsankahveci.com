VS Code Agent Instructions: Hidden Redirect Setup
Copy and paste the block below into your VS Code agent to implement the hidden /video redirect for your site.

Task: Implement Hidden YouTube Redirect
Context: This is a Quarto website project deployed via GitHub Pages from the docs/ directory. We need to create a hidden redirect to a YouTube tape without adding it to the navigation menu.

1. Create the Redirect Folder and File
Create a new directory at the project root named video.

Inside the video folder, create a new file named index.html.

Paste the following HTML code into video/index.html.

Action Required: Replace YOUR_YOUTUBE_URL_HERE with your actual unlisted YouTube link.

HTML
<!DOCTYPE html>
<html>
  <head>
    <meta name="robots" content="noindex">
    <meta http-equiv="refresh" content="0; url='YOUR_YOUTUBE_URL_HERE'">
    <title>Redirecting...</title>
  </head>
  <body>
    <p>If you are not redirected, <a href="YOUR_YOUTUBE_URL_HERE">click here</a>.</p>
  </body>
</html>
2. Configure Quarto to Include the Folder
Open the _quarto.yml file located in the root directory.

Under the project section, add a resources key to ensure this folder is copied to the docs output folder.

Your project section should look like this:

YAML
project:
  type: website
  output-dir: docs
  resources:
    - "video"
3. Verification
Confirm that video is not added to the navbar section in _quarto.yml to ensure it remains hidden from the public-facing site navigation.

Deployment Commands
Once the agent has finished the file operations, run these commands in your terminal to push the changes live:

Bash
git add .
git commit -m "Add hidden comedy tape redirect"
git push origin main
Your link will be active at ihsankahveci.com/video as soon as the GitHub Actions build completes.