---
label: Game Modes And Loading Game
order: 88
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
Directory :  `~/CustomCommonUI/Blueprints/BP_MenuPawn`
:::

# New Game and Game Modes

For starting a game we use the `BP_MenuPawn` function named `StartGameMode` its work with hashs
- `GameMode` the name of the level or mode
- `Difficulty` the difficulty of level or mode

# Load, Save Game and Delete
!!!
Save Slots Load or Delete function is in `BP_MenuPawn` but its can be used anywhere with loading a custom SaveGame class 
!!!
- `BP_MenuPawn` create and load some dummy data with a custom SaveGame class
- The `WBP_LoadGameScreen` pull the loaded data in `BP_MenuPawn` and generate list members

