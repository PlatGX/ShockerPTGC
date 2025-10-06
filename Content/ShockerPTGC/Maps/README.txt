2.4 All Map* Files Belong In A Folder Called Maps
Map files are incredibly special and it is common for every project to have its own map naming system, especially if they work with sub-levels or streaming levels. No matter what system of map organization is in place for the specific project, all levels should belong in /Content/Project/Maps.

Being able to tell someone to open a specific map without having to explain where it is is a great time saver and general 'quality of life' improvement. It is common for levels to be within sub-folders of Maps, such as Maps/Campaign1/ or Maps/Arenas, but the most important thing here is that they all exist within /Content/Project/Maps.

This also simplifies the job of cooking for engineers. Wrangling levels for a build process can be extremely frustrating if they have to dig through arbitrary folders for them. If a team's maps are all in one place, it is much harder to accidentally not cook a map in a build. It also simplifies lighting build scripts as well as QA processes.

For more information: https://github.com/Allar/ue5-style-guide?tab=readme-ov-file#2.4