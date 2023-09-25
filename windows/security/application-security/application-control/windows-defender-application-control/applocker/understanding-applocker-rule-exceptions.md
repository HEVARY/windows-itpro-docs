---
title: Understanding AppLocker rule exceptions
description: This topic describes the result of applying AppLocker rule exceptions to rule collections.
ms.localizationpriority: medium
ms.topic: conceptual
ms.date: 09/21/2017
---

# Understanding AppLocker rule exceptions

>[!NOTE]
>Some capabilities of Windows Defender Application Control are only available on specific Windows versions. Learn more about the [Windows Defender Application Control feature availability](/windows/security/threat-protection/windows-defender-application-control/feature-availability).

This topic describes the result of applying AppLocker rule exceptions to rule collections.

You can apply AppLocker rules to individual users or a group of users. If you apply a rule to a group of users, all users in that group are affected by that rule. If you need to allow a subset of a user group to use an app, you can create a special rule for that subset.

For example, the rule "Allow Everyone to run Windows except Registry Editor" allows Everyone to run Windows binaries, but doesn't allow anyone to run Registry Editor (by adding %WINDIR%\regedit.exe as a Path Exception for the rule).  
The effect of this rule would prevent users such as Helpdesk personnel from running the Registry Editor, a program that is necessary for their support tasks.  
To resolve this problem, create a second rule that applies to the Helpdesk user group: "Allow Helpdesk to run Registry Editor" and add %WINDIR%\regedit.exe as an allowed path. If you create a deny rule that doesn't allow any users to run Registry Editor, the deny rule will override the second rule that allows the Helpdesk user group to run Registry Editor.

## Related topics

- [How AppLocker works](how-applocker-works-techref.md)