To deploy Pig wolf game you need:

1) install node.js, npm and git on your platform
2) clone this repo: 
  $ git clone https://github.com/7cats/pig-wolf-game.git
3) in project folder install gulp and gulp-webserver:
  $ npm install gulp gulp-webserver
4) delpoy game:
  $ gulp server

HOTKEYS

Game:
  wasd - movement
  space - stay at place
  j - open/close the door(when you're staying on a button)
    - door can't be closed, if there is a wolf in the cell with door
  r - reload the level

Level-editor:
  wasd - movement
  space or z - stay at place
  j - open the door
  i - return to level initial state(before you start playing it)


CREATING LEVELS

Level-editor
To create wolf, click on the field, there it'll appear. To create trajectory for him click
consequently on the cells, with common side. At the end press key 'q', there will be
a message "wolf created".

If you want to bind a button and a door, create first button, then door.
If all right, you see a message "door binded with button"

When you are playing in Level-editor, to return to initial state press the key 'i'.
You can stay at place by pressing 'z'.


All levels are stored in one array in file LEVELS.js (folder levels)
You may create your own level in Level-Editor
After you created a JSON-file with your level you may add it to the LEVELS-array

You need node.js to be installed
Run script addLevelToArray.js with parameters:
  file name(or path to file, if it is not in directory with the script)
  level index(1-based) - new level will take place of index (next levels will move by 1 to the end)

You may also pass string 'end' as second parameter, in that case you will add level to the end

Examples:
  node.exe addLevelToArray.js my-new-created-level.txt end
  will add level to the end

  node.exe addLevelToArray.js MY_LEVELS/my-level.json end
  will do the same, but file is stored in folder MY_LEVELS

  node.exe addLevelToArray.js "C:\stuff\levels\latest-level.json" 7
  you will see your level on 7 position
  you may use full-path, no matter forward '/' or backward '\' slash

You can also delete levels
Run script deleteLevelFromArray.js with 1-based index as parameter
If you give program 'all' as parameter, it will delete all levels

Examples:
  node.exe deleteLevelFromArray.js 3
  node.exe deleteLevelFromArray.js all 
