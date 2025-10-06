This is a placeholder to retain file structure - delete by 1/1/26 if still empty.

2.9 No Empty Folders
There simply shouldn't be any empty folders. They clutter the content browser.

If you find that the content browser has an empty folder you can't delete, you should perform the following:

Be sure you're using source control.
Immediately run Fix Up Redirectors on your project.
Navigate to the folder on-disk and delete the assets inside.
Close the editor.
Make sure your source control state is in sync (i.e. if using Perforce, run a Reconcile Offline Work on your content directory)
Open the editor. Confirm everything still works as expected. If it doesn't, revert, figure out what went wrong, and try again.
Ensure the folder is now gone.
Submit changes to source control.

For more information: https://github.com/Allar/ue5-style-guide?tab=readme-ov-file#2.7