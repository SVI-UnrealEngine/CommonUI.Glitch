---
label: Screen Usage
order: 89
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
Directory :  `~/CustomCommonUI/Blueprints/Widgets/WBP_BaseUI`
:::

`WBP_BaseUI` hold screen stacks for displaying.

# Push Menu Screen
---
- `StackMenu` hold only menu screens like MainMenu, Settings,NewGame etc...
   - Placed at the back of the screen 
   - In Widget Graphs right click and write `GetBaseUI`
   - `GetBaseUI` use macro for quickly reach BaseUI
   - Select BaseUI pin and drag anywhere-
   - Use `PushOnMenu` function for open a new screen in this stack
   - The opened screen must be derived from `GenericActivatableWidget`
   - In `GenericActivatableWidget` set your focus (for gamepad navigation) with overrided `GetDesiredFocus` function
   - [OPTIONAL] if this screen can go back toggle the `IsBackHandler` variable in `Designer` section also you can override `BP_OnHandleBackAction` for custom back actions
   - Use the parent function named `OnScreenBack` for handle custom back actions in `GenericActivatableWidget`
---

# Push Modal Screen
---
- `StackModal` hold only modal like screens like load game details or custom sub screens
   - Placed at the top of the `StackMenu`
   - In Widget Graphs right click and write `GetBaseUI`
   - `GetBaseUI` use macro for quickly reach BaseUI
   - Select BaseUI pin and drag anywhere
   - Use `PushOnModalWindow` function and it will set automaticly the owner screen fetched in `StackMenu`
   - Also you can manipulate the owner and the modal window using the return value of `PushOnModalWindow`
   - ModalWindows derived from  `GenericActivatableWidget` set your focus (for gamepad navigation) with overrided `GetDesiredFocus` function
   - [REQUIRED] this screen can go back toggle the `IsBackHandler` variable in `Designer` section also you must override `BP_OnHandleBackAction` for custom back actions
   - Use the parent function named `OnScreenBack` for handle custom back actions in `GenericActivatableWidget`
---

# Push Prompt Screen
---
- `StackPrompt` hold only prompt screens like dialog screen or confirmation screens
   - Placed at the top of the screen
   - In Widget Graphs right click and write `GetBaseUI`
   - `GetBaseUI` use macro for quickly reach BaseUI
   - Select BaseUI pin and drag anywhere
   - Use `CreateBasicPromptScreen` function and set ActivatableOwner, Event Bindings
   - It will automaticly deactivated when the prompt closed and will invoke `OnInteractableStateChange` to inform the owner of prompt screen
---

# Loading Screen
---
- Use `StackMenu` and push like other screens 
   - In Widget Graphs right click and write `GetBaseUI`
   - `GetBaseUI` use macro for quickly reach BaseUI
   - Select BaseUI pin and drag anywhere
   - Use `PushOnMenu` function, returned value is the screen 
   - Cast the screen to `WBP_LoadingScreen` and iterate the progress bar when the bar is completed is will remove self automaticly
---
