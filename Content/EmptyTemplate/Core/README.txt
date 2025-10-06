2.5 Use A Core Folder For Critical Blueprints And Other Assets
Use /Content/Project/Core folder for assets that are absolutely fundamental to a project's workings. For example, base GameMode, Character, PlayerController, GameState, PlayerState, and related Blueprints should live here.

This creates a very clear "don't touch these" message for other team members. Non-engineers should have very little reason to enter the Core folder. Following good code structure style, designers should be making their gameplay tweaks in child classes that expose functionality. World builders should be using prefab Blueprints in designated folders instead of potentially abusing base classes.

For example, if your project requires pickups that can be placed in a level, there should exist a base Pickup class in Core/Pickups that defines base behavior for a pickup. Specific pickups such as a Health or Ammo should exist in a folder such as /Content/Project/Placeables/Pickups/. Game designers can define and tweak pickups in this folder however they please, but they should not touch Core/Pickups as they may unintentionally break pickups project-wide.

For more information: https://github.com/Allar/ue5-style-guide?tab=readme-ov-file#2.5