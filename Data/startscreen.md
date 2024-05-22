---
label: Start Screens
order: 91
icon: "/static/add.png"
---


<style>
    .sample {
        text-align: left;
        color: #000000;
        border-radius: 10px;
        background-color: #5f99f5;
        border: 1px solid #1956AF;
        padding-left: 10px;
        padding-top: 20px;
        margin-bottom: 20px;
    }
</style>



:::sample
Directory :  `~/CustomCommonUI/Blueprints/Widgets/Bases/StartScreenActivatableWidget`
:::

# StartScreenActivatableWidget
- `StartScreenActivatableWidget` all start screen bases.
-  Contain a method for calling `NextStartScreen` in `BP_MenuPawn`
- `BP_MenuPawn` hold all start screens by class in a ordered list named `StartScreens`.
-  You can order the list or remove start screens, there is not any dependency in screens
-  In `BP_MenuPawn` the `CurrentStartScreenIndex` will open `WBP_MainMenuScreen` when outside the range of `StartScreens` 

---

# Switching
- In Blueprint Graph when your button pressed/clicked use the parent function named `NextStartScreen`
- `BP_MenuPawn` will handle the next screen with screen list as well as if the screen list index is out of range it will open the `WBP_MainMenuScreen`
