![Registry](https://github.com/user-attachments/assets/7d5c2dad-706e-4b76-9d76-153090349c49)

> A hierarchical centralized database file system resembling the Windows Registry.

#

The Windows Registry is a hierarchical database used by the Windows operating system to store configuration settings and options. It's primarily managed through system-level APIs provided by the Windows operating system. Windows provides a set of APIs for interacting with the Registry. These are part of the Windows API and can be used in various programming languages like C, C++, C#, and Python.

#
### Windows 11 Registry Diagram

```
Windows 11 Registry
|
+-- HKEY_CLASSES_ROOT (HKCR)
|   |
|   +-- File Associations
|   |    - Contains information about file types and their associated programs. This includes file extensions and the programs that handle those file types.
|   |
|   +-- COM Objects
|   |    - Stores information about Component Object Model (COM) objects, including class identifiers (CLSIDs) and interface identifiers (IIDs). COM is used for enabling inter-process communication and dynamic object creation in Windows.
|   |
|   +-- Class Definitions
|        - Contains information about classes, which are templates for objects that can be created by applications. This includes registration of shell extensions and other components.
|
+-- HKEY_CURRENT_USER (HKCU)
|   |
|   +-- User-Specific Settings
|   |    - Contains configuration settings for the currently logged-in user, such as desktop background, display settings, and user-specific software preferences.
|   |
|   +-- Control Panel
|   |    - Stores settings for the Control Panel applets, including display settings, mouse and keyboard configuration, and other user-specific preferences.
|   |
|   +-- Software
|   |    - Holds settings and configurations for software installed for the current user, including user-specific application preferences.
|   |
|   +-- Environment Variables
|        - Contains user-specific environment variables, such as the PATH variable, which determines where the system looks for executable files.
|
+-- HKEY_LOCAL_MACHINE (HKLM)
|   |
|   +-- System Configuration
|   |    - Stores information related to the system’s hardware and software configuration, including driver and service settings.
|   |
|   +-- Hardware Settings
|   |    - Contains information about the system’s hardware components, including device drivers and resource allocations.
|   |
|   +-- Software (Installed Programs)
|   |    - Stores settings for software installed on the machine, applicable to all users. This includes application paths, configurations, and version information.
|   |
|   +-- SAM (Security Accounts Manager)
|   |    - Contains user and group information, including password hashes, for all accounts on the local machine. It’s a critical component for system security.
|   |
|   +-- SECURITY (Local Security Authority)
|        - Manages security policies and settings for the local system, including user rights, group policies, and audit policies.
|
+-- HKEY_USERS (HKU)
|   |
|   +-- Default User Profile
|   |    - Contains the default profile settings applied to new user accounts created on the system.
|   |
|   +-- User Profiles
|        - Stores the settings for all user profiles on the system, including preferences, desktop configurations, and user-specific software settings.
|
+-- HKEY_CURRENT_CONFIG (HKCC)
    |
    +-- Hardware Profiles
    |    - Contains information about the hardware profile currently in use. Hardware profiles store settings related to hardware devices that might vary depending on the computer's configuration.
    |
    +-- Display Settings
         - Stores information about the current display configuration, including screen resolution, color depth, and refresh rate.
```

#
### Registry Mods

Modifications to the Windows Registry should be approached with caution, as improper changes can lead to system instability or even render the system unbootable. However, certain areas are commonly modified, either manually or through software, to customize system behavior, improve performance, or troubleshoot issues. 

HKEY_CLASSES_ROOT (HKCR)

Modifiable Areas:

- File Associations: You can change or create file associations, determining which program opens specific file types.
- COM Objects: You can modify or register new COM objects if you're developing software that requires custom COM components.
- Class Definitions: Shell extensions or other class-related settings can be modified to customize the user experience.

Common Modifications:

- Changing the default application for a specific file extension.
- Adding or modifying context menu options for file types.

HKEY_CURRENT_USER (HKCU)

Modifiable Areas:

- User-Specific Settings: Customizing desktop appearance, input device settings (e.g., mouse sensitivity), and user interface elements.
- Control Panel: Adjusting settings related to the Control Panel, such as themes, screensavers, or power settings.
- Software: Modifying software preferences or disabling specific features for the current user.
- Environment Variables: Adding or changing environment variables that apply only to the current user.

Common Modifications:

- Changing desktop background or screensaver settings.
- Customizing application settings like startup options or user interface preferences.
- Modifying environment variables to change the command line behavior or paths for the user.

HKEY_LOCAL_MACHINE (HKLM)

Modifiable Areas:

- System Configuration: Changing settings related to services, drivers, or startup configurations.
- Hardware Settings: Modifying driver settings or hardware configurations.
- Software (Installed Programs): Adjusting global software settings, like application paths or default installation directories.
- SAM (Security Accounts Manager): Modifying user and group permissions (typically done through the system, not directly via the Registry).
- SECURITY (Local Security Authority): Changing security policies, although this is usually done via Group Policy, not direct Registry edits.

Common Modifications:

- Disabling or enabling services or drivers.
- Changing network configuration settings.
- Modifying system-wide software settings or preferences.

HKEY_USERS (HKU)

Modifiable Areas:
- Default User Profile: Changing default settings that will apply to new user accounts created on the system.
- User Profiles: Modifying settings for specific users, especially if troubleshooting issues related to user profiles.

Common Modifications:
- Pre-configuring settings for new users, such as default desktop backgrounds or application configurations.
- Adjusting user-specific settings when troubleshooting profile issues.

HKEY_CURRENT_CONFIG (HKCC)

Modifiable Areas:

- Hardware Profiles: Changing settings related to hardware configurations, such as how devices are initialized during boot.
- Display Settings: Adjusting display settings like resolution, color depth, or refresh rate.

Common Modifications:

- Tweaking display settings for different hardware profiles.
- Adjusting hardware profiles to optimize performance or compatibility for different configurations.

General Considerations:

What Can Be Safely Modified:

- Customization Settings: These include user interface tweaks, file associations, desktop configurations, and software preferences.
- Performance Tweaks: Changes aimed at optimizing system performance, like disabling unnecessary startup programs or services.
- Troubleshooting: Temporarily changing settings to resolve system issues, such as disabling problematic drivers or services.

What Should Be Avoided:

- Critical System Settings: Modifying essential system configurations (e.g., SAM, SECURITY) without a deep understanding of the consequences.
- Registry Keys Managed by Windows: Keys that are critical for the operating system's operation should generally not be altered.
- Sensitive Security Settings: Adjusting security policies or permissions that could compromise system security.

Backup and Restore:

- Always back up the Registry before making any changes. You can do this by exporting the relevant keys using the Registry Editor (regedit.exe).
- Be prepared to restore the Registry if any modifications cause issues, either through a system restore or by importing the previously exported keys.

#
### Double-Click Mods

![Mouse](https://github.com/user-attachments/assets/199eb508-668c-4d6d-8619-482996d1af35)

Customizing the double-click behavior can enhance user experience and productivity, especially when it comes to how files, folders, and applications respond to double-clicks.

Optional Double-Click Mods: 

- Assign a custom action (like opening with a specific application, compressing a file, or moving it to a predefined folder) to double-clicking a file or folder.
- Adjust the double-click speed dynamically based on the type of file or application in focus.
- Use double-click to initiate a sequence of actions, such as opening a file, copying it to a clipboard, and launching a related application.
- Quickly preview the contents of a file with a double-click without fully opening it in its associated application.
- Use double-click on the title bar or border of a window to toggle between maximized, minimized, or custom window sizes.
- Double-click a desktop icon to switch to another user profile or log in as a different user quickly.
- Use double-click to toggle specific system settings, like turning on/off Wi-Fi, switching power plans, or enabling/disabling Night Light.
- Double-click a file or text to automatically copy it to the clipboard without additional keyboard commands.
- Double-click a specific file or icon to launch multiple applications or open multiple files at once.
- Use double-click to quickly switch between virtual desktops or to create a new one.

#

Alex: "*I have double-click turned off.*"

#
### Related Links

[ChatGPT](https://github.com/sourceduty/ChatGPT)
<br>
[Windows Deviance](https://github.com/sourceduty/Windows_Deviance)
<br>
[Windows](https://github.com/sourceduty/Windows)
<br>
[Regulated File Manager](https://github.com/sourceduty/Regulated_File_Manager)
<br>
[Windows Registry Expert](https://chatgpt.com/g/g-vGNiWQSoA-windows-registry-expert)

***
Copyright (C) 2024, Sourceduty - All Rights Reserved.
