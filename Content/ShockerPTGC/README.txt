2.2 Use A Top Level Folder For Project Specific Assets
All of a project's assets should exist in a folder named after the project. For example, if your project is named 'Project: Aurora', all of it's content should exist in Content/Project_Aurora.

The Developers folder is not for assets that your project relies on and therefore is not project specific. See Developer Folders for details about this.

There are multiple reasons for this approach.


2.2.1 No Global Assets
Often in code style guides it is written that you should not pollute the global namespace and this follows the same principle. When assets are allowed to exist outside of a project folder, it often becomes much harder to enforce a strict structure layout as assets not in a folder encourages the bad behavior of not having to organize assets.

Every asset should have a purpose, otherwise it does not belong in a project. If an asset is an experimental test and shouldn't be used by the project it should be put in a Developer folder.


2.2.2 Reduce Migration Conflicts
When working on multiple projects it is common for a team to copy assets from one project to another if they have made something useful for both. When this occurs, the easiest way to perform the copy is to use the Content Browser's Migrate functionality as it will copy over not just the selected asset but all of its dependencies.

These dependencies are what can easily get you into trouble. If two project's assets do not have a top level folder and they happen to have similarly named or already previously migrated assets, a new migration can accidentally wipe any changes to the existing assets.

This is also the primary reason why Epic's Marketplace staff enforces the same policy for submitted assets.

After a migration, safe merging of assets can be done using the 'Replace References' tool in the content browser with the added clarity of assets not belonging to a project's top level folder are clearly pending a merge. Once assets are merged and fully migrated, there shouldn't be another top level folder in your Content tree. This method is 100% guaranteed to make any migrations that occur completely safe.


2.2.2e1 Master Material Example
For example, say you created a master material in one project that you would like to use in another project so you migrated that asset over. If this asset is not in a top level folder, it may have a name like Content/MaterialLibrary/M_Master. If the target project doesn't have a master material already, this should work without issue.

As work on one or both projects progress, their respective master materials may change to be tailored for their specific projects due to the course of normal development.

The issue comes when, for example, an artist for one project created a nice generic modular set of static meshes and someone wants to include that set of static meshes in the second project. If the artist who created the assets used material instances based on Content/MaterialLibrary/M_Master as they're instructed to, when a migration is performed there is a great chance of conflict for the previously migrated Content/MaterialLibrary/M_Master asset.

This issue can be hard to predict and hard to account for. The person migrating the static meshes may not be the same person who is familiar with the development of both project's master material, and they may not be even aware that the static meshes in question rely on material instances which then rely on the master material. The Migrate tool requires the entire chain of dependencies to work however, and so it will be forced to grab Content/MaterialLibrary/M_Master when it copies these assets to the other project and it will overwrite the existing asset.

It is at this point where if the master materials for both projects are incompatible in any way, you risk breaking possibly the entire material library for a project as well as any other dependencies that may have already been migrated, simply because assets were not stored in a top level folder. The simple migration of static meshes now becomes a very ugly task.


2.2.3 Samples, Templates, and Marketplace Content Are Risk-Free
An extension to 2.2.2, if a team member decides to add sample content, template files, or assets they bought from the marketplace, it is guaranteed, as long your project's top-level folder is uniquely named,that these new assets will not interfere with your project.

You can not trust marketplace content to fully conform to the top level folder rule. There exists many assets that have the majority of their content in a top level folder but also have possibly modified Epic sample content as well as level files polluting the global Content folder.

When adhering to 2.2, the worst marketplace conflict you can have is if two marketplace assets both have the same Epic sample content. If all your assets are in a project specific folder, including sample content you may have moved into your folder, your project will never break.


2.2.4 DLC, Sub-Projects, and Patches Are Easily Maintained
If your project plans to release DLC or has multiple sub-projects associated with it that may either be migrated out or simply not cooked in a build, assets relating to these projects should have their own separate top level content folder. This make cooking DLC separate from main project content far easier. Sub-projects can also be migrated in and out with minimal effort. If you need to change a material of an asset or add some very specific asset override behavior in a patch, you can easily put these changes in a patch folder and work safely without the chance of breaking the core project.

For more information: https://github.com/Allar/ue5-style-guide?tab=readme-ov-file#2.2