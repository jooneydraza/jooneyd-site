# Jooneyd Raza — Landing Page & Portfolio

Welcome! This is the codebase for your personal Book Design & Production landing page. This page is designed to showcase your testimonials, services, and portfolio to prospective clients, offering direct links to contact you via WhatsApp, Email, or SMS/iMessage.

Since you are new to web development, this guide is written in plain English to help you understand how your website is structured, how to view and test it, how to make updates, and how to track your changes using **Git (Version Control)**.

---

## 📁 Project Structure

Here is a quick look at what is in your folder:

*   **`index.html`**: The entire core of your website. It contains the text layout (HTML), the visual design/styling (CSS), and the interactive behaviors (JavaScript) all in a single file.
*   **`.mp4` files** (e.g., `Aaron_Hundlay.mp4`, `Alpha_Parrot.mp4`): The actual video testimonials shown on the page.
*   **`.jpg` files** (e.g., `Aaron_Hundlay_thumb.jpg`): Backup thumbnail images corresponding to each video testimonial.

---

## 💻 How to View & Test Your Website Locally

Before making any changes public, you will want to test the website on your own machine. 

### Method 1: Just Double-Click (Quickest but limited)
1. Open your project folder (`jooneyd-site`) in macOS Finder.
2. Double-click the `index.html` file.
3. It will open in your default web browser (Safari, Chrome, etc.).
> [!NOTE]
> Modern web browsers block playing local video files (`.mp4`) when opening files directly like this due to security rules. To test video playback, use Method 2.

### Method 2: Use Visual Studio Code + Live Server (Recommended)
1. Download and install **[Visual Studio Code](https://code.visualstudio.com/)** (a free, lightweight code editor).
2. Open VS Code, select **File** -> **Open Folder...**, and select your `jooneyd-site` folder.
3. Click the Extensions icon on the left sidebar (it looks like 4 blocks), search for **"Live Server"** by Ritwick Dey, and click **Install**.
4. Once installed, open `index.html` in VS Code, and click the **"Go Live"** button in the bottom right corner of the window.
5. This opens your website on a local web server (usually at `http://127.0.0.1:5500`), where all features (including videos) work perfectly, and the page will automatically refresh whenever you edit and save the code!

---

## ✍️ How to Edit and Update the Code

To make updates, open `index.html` in your text editor (VS Code) and search for the section you want to modify using `Command + F` (Mac).

### 1. Modifying General Text
If you want to edit your name, bios, tags, or prices, open `index.html` and search for the text you want to change. Simply delete the old text between the tags and type your new text. For example:
```html
<!-- Locate the header and edit the text -->
<h1 class="hero-name">Jooneyd Raza</h1>
```

### 2. Updating the Services List (Rotating Typewriter)
The services that slide in on your header (and footer) are defined in a simple JavaScript list.
1. Scroll to the bottom of `index.html` around **Line 504**.
2. Look for `var SERVICES = [`:
   ```javascript
   var SERVICES = [
     'Book Formatting & Layout Design',
     'Book Cover Design',
     'Custom Line Art Illustrations',
     'Book Publishing Assistance',
     'High-Converting Social Media Book Posts',
     'Professional Book Trailer Videos',
   ];
   ```
3. Edit the items inside the single quotes, or add/delete lines to modify your list of services.

### 3. Adding or Replacing Video Testimonials
When a client sends you a new video testimonial:
1. Save the new video in your project folder as a `.mp4` file (e.g. `client_name.mp4`).
2. Save a thumbnail image for the video in the folder (e.g. `client_name_thumb.jpg`).
3. Scroll to the video grid in `index.html` around **Line 435** (inside `<div class="videos-grid">`).
4. Duplicate one of the existing video blocks and edit its fields:
   ```html
   <div class="vc" onclick="playVideo(this)" data-src="client_name.mp4" data-name="Client Name">
     <div class="vc-wrap">
       <!-- You can link directly to your thumbnail file here -->
       <img class="vc-thumb" src="client_name_thumb.jpg" alt="Client Name" loading="lazy">
       <div class="vc-overlay">
         <div class="play-ring"><div class="play-tri"></div></div>
       </div>
     </div>
     <div class="vc-name">Client Name</div>
   </div>
   ```
   *Note: While existing videos use embedded `data:image/jpeg;base64` codes to make the page self-contained, using the filename directly (`src="client_name_thumb.jpg"`) is much easier and works exactly the same.*

### 4. Editing Written Reviews
Your review carousel sits around **Line 420** of `index.html`. To add a new review, copy and paste an existing `rv` block and modify the contents:
```html
<div class="rv" onclick="toggleRv(this)">
  <div class="rv-q">“</div>
  <div class="rv-stars">★★★★★</div>
  <p class="rv-txt">Type the client's quote here...</p>
  <div class="rv-more">Read full review ↓</div>
  <div class="rv-foot">
    <div class="rv-av" style="background:linear-gradient(135deg,#b8924a,rgba(14,10,6,.5) 150%)">
      C <!-- First letter of their name for avatar -->
    </div>
    <div>
      <div class="rv-name">Client Name</div>
      <div class="rv-role">Service Provided</div>
    </div>
  </div>
</div>
```

### 5. Adding New Countries to the Map
You have a map showing dots in countries you have worked with. To add a new country dot:
1. Scroll to the bottom of the script section around **Line 701**.
2. Look for `var countries = [ ... ];`
3. Add a new row to the array:
   ```javascript
   {name: "New Country", x: 45, y: 30},
   ```
   *   `x`: Position of the dot from the left edge of the map (percentage, `0` to `100`).
   *   `y`: Position of the dot from the top edge of the map (percentage, `0` to `100`).

---

## 🐙 Git & Version Control (Safety Net & Collaboration)

Git is a version control system. Think of it as a super-powered "Save" and "Undo" system. It tracks every line of code you change, letting you revert mistakes and upload your project safely to remote servers (like GitHub).

We have already initialized a local Git repository in this folder and saved its current state.

### How to Use Git Day-to-Day (The Commands)
When you make updates (e.g. changing texts, adding a review), follow this 3-step cycle in your Terminal:

1. **Check what has changed**:
   ```bash
   git status
   ```
   *This tells you which files have been modified or added.*

2. **Stage your changes (prepare them to be saved)**:
   ```bash
   git add .
   ```
   *The dot `.` tells Git to prepare all changed files.*

3. **Commit your changes (save the state forever)**:
   ```bash
   git commit -m "Added a new video testimonial for John Doe"
   ```
   *Always write a short, clear description inside the quotes so you know what you did.*

### Using Visual Tools (Instead of typing commands)
If you do not want to use the terminal:
*   **VS Code**: Open the **Source Control** tab on the left (the branch icon with a badge). You will see your changed files. Click the **`+`** icon next to "Changes" to stage them, type your message in the box at the top, and click **Commit**.
*   **GitHub Desktop**: You can download the free **[GitHub Desktop](https://desktop.github.com/)** application, import your folder, and manage commits with a simple, visual click-and-point interface.

---

## ☁️ Connecting Your Project to a Remote Git Repository (GitHub)

To back up your project online, publish it to a live hosting provider, or share it with other developers, you should upload it to a remote Git platform like **GitHub**.

Here is how to set it up:

1. Go to **[GitHub.com](https://github.com/)** and sign up for a free account.
2. Log in and click the green **"New"** button on the left sidebar to create a repository.
3. Set your repository name (e.g., `jooneyd-site`).
4. **IMPORTANT**: Leave "Add a README file", "Add .gitignore", and "Choose a license" **UNCHECKED**. (We already have these locally).
5. Click **"Create repository"**.
6. You will see a page with some code blocks. Look for the block titled **"…or push an existing repository from the command line"** and run those exact commands in your terminal inside your project folder:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/jooneyd-site.git
   git branch -M main
   git push -u origin main
   ```
   *(Replace the URL with the actual URL shown on your GitHub page).*

After you run these commands, all your code and videos will be securely backed up on GitHub! Whenever you commit changes locally, you can upload them to the internet by running:
```bash
git push
```
Or by clicking **"Sync Changes" / "Publish"** in VS Code/GitHub Desktop.
