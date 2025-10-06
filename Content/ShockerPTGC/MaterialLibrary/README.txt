2.8 MaterialLibrary
If your project makes use of master materials, layered materials, or any form of reusable materials or textures that do not belong to any subset of assets, these assets should be located in Content/Project/MaterialLibrary.

This way all 'global' materials have a place to live and are easily located.

This also makes it incredibly easy to enforce a 'use material instances only' policy within a project. If all artists and assets should be using material instances, then the only regular material assets that should exist are within this folder. You can easily verify this by searching for base materials in any folder that isn't the MaterialLibrary.

The MaterialLibrary doesn't have to consist of purely materials. Shared utility textures, material functions, and other things of this nature should be stored here as well within folders that designate their intended purpose. For example, generic noise textures should be located in MaterialLibrary/Utility.

Any testing or debug materials should be within MaterialLibrary/Debug. This allows debug materials to be easily stripped from a project before shipping and makes it incredibly apparent if production assets are using them if reference errors are shown.

For more information: https://github.com/Allar/ue5-style-guide?tab=readme-ov-file#2.8