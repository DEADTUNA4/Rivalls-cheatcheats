# 🌿 Leafytoxins Research Suite V8
 The Definitive Game Security Testing Framework for Rivals & Edge of Honors
 
## 📖 What is Leafytoxins?
#### Leafytoxins V8 is a high-performance framework developed by Leafy Toxins to test the boundaries of modern game security. It is specifically engineered to bypass BAC (Blox Anti-Cheat) triggers and Ugc service-level obfuscation, providing developers and researchers a clean environment for "Red Team" security analysis.
### 🚀 Key Features: An In-Depth Glance

#### 🎯 Precision Combat Suite: 
This script uses a specific recursive filter to isolate the Head instance rather than generic hitboxes. This ensures maximum accuracy for hit-registration testing and allows for the study of headshot-specific server-side detection.

#### 🖱️ MouseButton2 Trigger: 
Hard-coded to the Right-Click input to simulate realistic "Aim Down Sights" (ADS) behavior. This is vital for researchers testing "Snap-to-Target" mechanics and analyzing how anti-cheats track rapid CFrame adjustments.

#### 🌀 Hardware-Rendered FOV Circle:
Utilizing the Drawing API, the script draws a 2D overlay directly onto the viewport. Because this exists in the overlay layer and not the DataModel, it bypasses standard UI-scanning scripts that check for unauthorized ScreenGuis.

#### ⚡ Adaptive Movement Mechanics:
A sophisticated movement exploit that monitors UserInputService for jump requests. If a second jump is detected within a 0.3-second window, the WalkSpeed is instantly multiplied to test state-based velocity blockers.

#### 🏃 State-Based Speed Reset: 
To bypass "Average Speed" checkers, the script tracks the Humanoid's state. As soon as the state changes from Freefall back to Landed, the speed is hard-reset to 16.

#### 👻 Collision-Layer Noclip:
Iterates through every BasePart in the character model during the Stepped physics frame to ensure collision is suppressed exactly when needed for high-speed traversal testing.

## 🛡️ Stealth & Bypass Architecture: 
High-security games often rename core services (like Players to Ugc) to crash scripts. Our suite uses game:GetService("Players"), which resolves via the engine's internal ClassName GUID, making the rename irrelevant.

### 🔌 BAC Request Masking: 
 BAC monitors for HttpGet requests to GitHub. By using a Local-First loading strategy (readfile), this script generates zero outbound network traffic, remaining "dark" to network-based packet sniffing.

## 📂 Installation & Deployment (High-Security Protocol)
### 1️⃣ Step 1: 
 Directory Configuration: Navigate to your executor's root folder and open the workspace folder. Create a sub-folder named scripts.

### 2️⃣ Step 2: 
Asset Placement: Download main.lua and rf.lua from this repository. Place both files into: .../workspace/scripts/.

### 3️⃣ Step 3: 
Local Launch: Open your executor (e.g., Xenno). In the file tab, open scripts/main.lua and Execute.

## 🛠️ For Blocker Developers (Detailed Security Guide)
If you are a developer for Edge of Honors, implement these server-side counters to mitigate the features in this suite:

### 🚩 Velocity Sanity: 
Log player position at T1 and T2. If (P2 - P1).Magnitude > 22 while the state is Freefall, force a position reset (Rubberband).

### 🔑 Remote Randomization: 
Randomize your Damage and Hit remotes every session so scripts cannot use string.find to locate them.

### 🔍 Highlight Monitoring:
Run a task.wait(5) loop on the server that checks for any object with ClassName == "Highlight" that doesn't have a server-verified security tag.

## ⚖️ Legal Disclaimer, Rights, and Acknowledgments
#### 🏷️ Intellectual Property & Trademarks: "Roblox," the Roblox logo, and "Powering Imagination" are trademarks of Roblox Corporation. This project is not affiliated with, sponsored by, or endorsed by Roblox Corporation. The UI framework utilized is based on the Rayfield Library by Sirius Software. All rights to the framework architecture belong to Sirius Software. The specific implementation, bypass logic, and "Ugc" resolution strategies are the intellectual property of Leafy Toxins (Copyright © 2026).

## 📜 Open Source & Licensing: This project is provided under the MIT License. You are permitted to fork, modify, and redistribute this code, provided that original credit is given to Leafy Toxins for the bypass logic and Sirius Software for the Rayfield UI framework.

⚠️ Ethical Research & Use: This suite is strictly for Educational and Research Purposes. The Developer (Leafy Toxins) takes no responsibility for any misuse of this tool, account bans, or damages resulting from the use of this software. Use of this software may violate the Terms of Service of specific games or the Roblox platform; user discretion is advised.

"Improving security through understanding vulnerabilities." — Leafy Toxins
