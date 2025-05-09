# ANDROID-DEBUG-PRACTICAL
ADB PRACTICAL Q1 2 AND 3 
 Android Data Extractor - Windows Forms App
This is a C# Windows Forms Application that uses ADB (Android Debug Bridge) to extract data from a connected Android device. The app pulls Contacts, SMS Messages, Call Logs, and Device Information, displays them on the GUI, and optionally stores them in files.

✅ Features
📇 Extract Contacts via ADB command

💬 Extract SMS Messages via ADB command

📞 Extract Call Logs via ADB command

💻 Get Device Info (CPU, Memory)

📁 Store data in .txt files

🖥️ Display all extracted data in list boxes

🛠 Prerequisites
Android device with USB debugging enabled

ADB installed and added to your system PATH

ADB must be able to detect the device:

nginx
Copy
Edit
adb devices
⚠️ Permissions Note
Due to Android’s security:

You cannot access contacts, SMS, or call logs via ADB on non-rooted devices

Workaround: Run content commands directly in the device terminal or extract logs via apps or exports

This app assumes that:

You have already extracted the data using ADB and saved it in .txt files (e.g., contacts.txt, sms.txt, calllogs.txt)

📂 File Structure
text
Copy
Edit
/YourProject
├── Form1.cs               # Main logic to read files and show data
├── Form1.Designer.cs      # Auto-generated layout code
├── contacts.txt           # Contacts data (optional - populated externally)
├── sms.txt                # SMS data (optional - populated externally)
├── calllogs.txt           # Call logs data (optional - populated externally)
├── bin/Debug              # Compiled output
└── README.md              # This file
🧪 Sample ADB Commands (Run in Command Prompt)
To pull exported data:

bash
Copy
Edit
adb pull /sdcard/contacts.txt
adb pull /sdcard/sms.txt
adb pull /sdcard/calllogs.txt
To query data directly (rooted devices only):

bash
Copy
Edit
adb shell content query --uri content://contacts/phones/
adb shell content query --uri content://sms/inbox
adb shell content query --uri content://call_log/calls
🚀 How to Use the App
Launch the Windows Forms App (finallpwq1.exe)

Click buttons:

Get Contacts — Reads and displays from contacts.txt

Get SMS — Reads and displays from sms.txt

Get Call Logs — Reads and displays from calllogs.txt

Get Device Info — Runs adb shell cat /proc/cpuinfo and meminfo

Ensure the .txt files are present in the same folder as the .exe

📌 Developer Notes
Written in C# using .NET Framework 4.8

Built in Visual Studio 2022

All commands are executed via:

csharp
Copy
Edit
ProcessStartInfo psi = new ProcessStartInfo("adb", "shell ...");
🙋 Troubleshooting
❌ File access error: Ensure contacts.txt, sms.txt, and calllogs.txt exist.

❌ ADB not found: Make sure ADB is added to system PATH.

❌ Permission Denied: Your Android device may not support access without root.

📄 License
This project is built for academic/demo purposes. No warranties provided.


![Screenshot 2025-05-09 161625](https://github.com/user-attachments/assets/0386987f-a280-4571-a823-3630a8ddfacb)
![Screenshot 2025-05-09 161941](https://github.com/user-attachments/assets/bc4d7d77-37ba-40ea-933f-d2969fdca4b4)




