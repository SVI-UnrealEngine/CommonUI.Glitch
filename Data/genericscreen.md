---
label: Generic Screens
order: 90
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
Directory :  `~/CustomCommonUI/Blueprints/Widgets/Bases/GenericActivatableWidget`
:::
# GenericActivatableWidget
---
- Base of all menu screens and activatable screens bases
- Can hold another `GenericActivatableWidget` with a variable named `ActivatableOwner`
- `ActivatableOwner` use cases
    - When a `GenericActivatableWidget` screen generate a modal window or any other screen without using `PushOnMenu` in `WBP_BaseUI`
    - Create a tree structure without a stack
- Using `ActivatableOwner` in owner screen we can close unused elements, stop navigations, interactions etc...
    - In the `GenericActivatableWidget` we can listen for event named `OnInteractableStateChange`
    - `OnInteractableStateChange` invoke when the generated screen opened or closed
---


