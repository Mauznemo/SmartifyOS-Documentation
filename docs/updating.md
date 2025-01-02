---
sidebar_position: 8
---

# Updating project

## How to update
To update your Unity project you can click `SmartifyOS > Check for Update` and then click on `Check for Update`.
If there is an update it will show you a changelog and which files will change. Then you can just click on `Sync Repository`.

## How file changes are handled
Files modified by you will never be overwritten!

## Errors while updating
If you modified one of the files and it was also modified on the remote you will get an error while trying to update.

### Error saying to commit or to stash changes
If you get an error like this you first need to [commit](https://code.visualstudio.com/docs/sourcecontrol/overview#_commit) your local changes.
If you want an relatively easy to use GUI tool to do this you can use [VS Code](https://code.visualstudio.com/)

### Merge conflict
If you run the updater (or `git pull`) again after committing you may get an Merge conflict in the files that you changed an which where also changed on the remote.

To fix this open the project in [VS Code](https://code.visualstudio.com/). Under the `Source control` tab you will see these files (they should have a ❗ icon). You then can click on them and on the button `Resolve in Merge Editor` and fix the conflict.

Here is a tutorial for the Merge Editor (explanation of editor starts at `02:18`)
<iframe width="560" height="315" src="https://www.youtube.com/embed/HosPml1qkrg?si=-AiqxcGwBerSz63P" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>