# EmbectaKit BLE

EmbectaKit Bluetooth PumpManager For Loop.

Created by rebelning on 31/03/2024.
Copyright © 2024 Randall Knutson. All rights reserved.

## Status

This repository contains code being tested in Loop.

## For more information

Please join loop zulipchat at https://loop.zulipchat.com/

## Upgrade 

-  Commits on Apr 15, 2024
-  fix: Cleanup state better
-  

### 修改基础率配置以小时为单位

- LoopKit
  - 
  - LoopKitUI/Views/ScheduleEditor
    - method: initialNewScheduleItem  Line:332
  - LoopKitUI/Views/Setting Editors/TherapySettingsView
    - TherapySettingsView_Previews 
      - Line:618
  - LoopKitUI/Views/ScheduleItemPicker
      - Line:39


LoopKit
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
    modified:   LoopKit.xcodeproj/project.pbxproj
    modified:   LoopKitUI/Views/ScheduleEditor.swift
    modified:   LoopKitUI/Views/ScheduleItemPicker.swift
    modified:   LoopKitUI/Views/Settings Editors/TherapySettingsView.swift
    
    
     
    ##  localization
    The localization is now nearly complete. Languages now just need work from Crowdin translators.

I have added hundreds of missing strings to my OmniBLE Crowdin branch. This OmniBLE is integrated with my Crowdin project for FreeAPS. Too bad we can't have the translation for both Loop dev and FreeAPS (Loop) in one project. Tested with Swedish language and everything seems to be localized , except some log entries and some special cryptic fault messages (which probably shouldn't be translated anyways).

Crowdin project: https://crowdin.com/project/freeaps-settings

My workspace (integrated with the Crowdin project) is tested and working : https://github.com/Jon-b-m/LoopWorkspace if you want to see the localization I did.

Adding this to Loop dev also would be possible , but I leave that to @Christian Aagaard
All base strings reside in two files: A0498CBF-D037-4E1C-8C49-D4721F82E17A.png . These files you will find in my OmniBLE fork, in the Crowdin branch.

https://github.com/Jon-b-m/LoopWorkspace

https://github.com/Jon-b-m/LoopKit/tree/1c97f52a6052d3afd996f18b40628f3ada27e553



### xdrip4ios

https://xdrip4ios.readthedocs.io/en/latest/
https://github.com/JohanDegraeve/xdripswift

https://zhuanlan.zhihu.com/p/457801963

https://www.loopandlearn.org/build-select/?fbclid=IwAR3bFSDbCSxcIgNktJzI6NK839CAt14eOo23RtGxgabg0AKYtc-gTCABtjI
