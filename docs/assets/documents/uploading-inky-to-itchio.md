# Exporting Ink to itch.io 

## Export to web from Inky
To save your story as a set of files that can be played in a web browser, use the `Export to web` option from the File menu.

This creates a folder with the following things inside:
- __index.html__: This is the container for your game in a webpage. You can open this file with a web browser.
- __ink.js__: This is the Ink engine that runs your game.
- __main.js__: This is the script that handles the way the story is presented
- __YourProjectName.js__: This is your story/game!
- __style.css__: This is the file which controls how the webpage is rendered in the browser.

### Naming your file
When you export the story, save it with the name as you want it have as a title (with any capitalization and spacing).

### Export story.js only
Later, if you make changes to your story you can choose the `Export story.js only` and save it into the folder you created when exporting to web. This is helpful if you begin making changes to the look of your game's webpage.

### Want to share your game offline?
Just share this exported folder and everything inside! 

## Uploading to itch.io

### Zip your exported folder
First, zip your exported folder. It has to be a zip file, not any other kind of compressed format.

### Itch.io Dashboard
- Navigate to [itch.io/dashboard](https://itch.io/dashboard) and click the `Create new project` button.
- Enter the details of your game/story.
- Set Kind of project to HTML.
- Upload the zip file by clicking the `Upload files` button and locating it on your computer.
- Choose `This file will be played in the browser` from the options that pop up.

### Embed options
- Leave `Embed in page` selected.
- Set `Viewport dimensions` to 800 x 600.
- Check the `Mobile friendly` box.
- Optional: Check the `Automatically start` button.
- Optional: Check the `Fullscreen button`to allow the game to be played in the full browser window.
- Not needed: `Enable scrollbars` (These are already built-in)

### Details
Below the embed options are options for adding a description and tags to your game. These are beneficial in helping others discover and understand your work (if shared publicly). 

Some important details: 
- __Community__: Decide if you want to allow comments
- __Visibility & access__: Do you want this visible to everyone?

### Visibility options
- __Draft__ mode can be used if you want to preview your page without publishing it (you can return to the game in the dashboard later to publish).
- __Restricted__ mode can be used to limit access to your game. You can set a password to make it easy to share with select people.
- __Public__: You can make your game visible to anyone with the URL. This option becomes available after you click `Save & view page`.

### Need to make changes later?
You can edit your itch.io project page by clicking on your username in the top right corner and selecting Dashboard. From there, you can find the game and change settings with the `Edit` link associated with it.
