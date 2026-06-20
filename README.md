# 🚀 How to Manage Your Website Using Antigravity AI

Welcome! This website is a simple, single-page video portfolio designed for your book design business. 

Since you are not a developer, **you do not need to write code, use the terminal, or edit files manually.** Instead, you can use **Antigravity AI** as your personal webmaster. This guide shows you exactly how to talk to the AI to make updates, save your history (Git), and prevent the website from getting messy over time.

---

## 📁 What is in this folder?
*   **`index.html`**: The main code file containing the text, design, and logic of your website.
*   **`.mp4` files**: Your client video testimonials.
*   **`.jpg` files**: Thumbnail images for your videos.

---

## 💬 AI Prompt Cheat-Sheet (How to talk to the AI)

When you want to update your site, open your chat with Antigravity AI and copy-paste or adapt these templates. 

### 1. Daily Updates & Text Changes
To change prices, descriptions, bios, or stats, tell the AI exactly what text to swap:
> **Prompt Template:**
> *"Please update the pricing for 'Book Cover Design' from $X to $Y in the code. Once done, save (commit) this change to Git as 'Update cover design pricing' and push it to GitHub."*

### 2. Adding a New Video Testimonial
Before asking the AI, copy your new video (`.mp4`) and its thumbnail image (`.jpg`) into this project folder. Then tell the AI:
> **Prompt Template:**
> *"I have copied 'client_name.mp4' and 'client_name_thumb.jpg' into the project folder. Please add this video to the video grid in `index.html`. Once done, save (commit) this change to Git as 'Add video testimonial for Client Name' and push it to GitHub."*

### 3. Adding a New Written Review
To add a text review to the scrolling carousel:
> **Prompt Template:**
> *"Please add a new 5-star review in the carousel: 'Quote text here' from 'Client Name' for the service 'Book Formatting'. Once done, save (commit) this change to Git as 'Add written review from Client Name' and push it to GitHub."*

### 4. Adding a Client Location Dot on the Map
To add a new dot on the world map:
> **Prompt Template:**
> *"Please add a dot for [Country Name] on the interactive world map. Once done, save (commit) this change to Git as 'Add Country Name to world map' and push it to GitHub."*

---

## 🛡️ Keeping Your Changes Safe (Save & Undo)

Your project uses **Git** (a code history saver). Every time the AI makes a change, you should ask it to "commit" (save a snapshot) and "push" (back it up to GitHub). This creates a safety net.

### How to Undo a Mistake
If the AI makes a change and something looks broken or you change your mind:
> **Prompt Template:**
> *"I don't like the last changes. Please revert/restore the project to the last saved state in Git."*
*(The AI will automatically reset the project to your last safe snapshot).*

### How to Back Up to the Internet & Update Live Site
If you made several changes and want to make sure they are saved online and deployed:
> **Prompt Template:**
> *"Please push all my current changes to GitHub."*

---

## ☁️ How Your Website is Hosted & Published (Netlify + GitHub)

Your website is hosted on **Netlify** using a feature called **Continuous Deployment**. Here is how the loop works:

1.  You test and approve changes locally with the AI.
2.  You ask the AI to push to GitHub (which updates your backup repository).
3.  Netlify automatically detects this push, grabs the new code, and updates your live domain (e.g. your custom domain) within 10 seconds.

### Setting up the connection (One-time Setup):
1.  Log in to your **[Netlify Dashboard](https://app.netlify.com/)**.
2.  Click on your existing site.
3.  Go to **Site settings** -> **Build & deploy**.
4.  Under **Continuous Deployment**, click **Link repository**.
5.  Select **GitHub**, log in, and authorize Netlify.
6.  Select the `jooneyd-site` repository and click **Deploy site**.

---

## 🧹 How to Prevent Website Bloat (Keeping it Clean)

Over time, websites can get messy ("bloated") with unused code or duplicate parts, making it hard for both humans and AI to read. 

To keep your project lean and clean for the long term, always add these rules to your prompts when asking for new features:

1.  **Keep it minimal**: *"Keep the code clean and well-structured, reusing existing CSS styles. Avoid adding new large external libraries."*
2.  **Delete unused files**: *"If we are replacing any videos or images, please delete the old files from the folder to keep the workspace clean."*
3.  **Use one file**: *"Keep all HTML, CSS, and JS inside `index.html` so the website remains self-contained and simple."*
