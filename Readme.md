# LocationSimulator-Help

This repository contains all required files for the help menu entry of LocationSimulator. It is based on the [jekyll-apple-help](https://github.com/chuckhoupt/jekyll-apple-help) project.

### Add a new entry

To add more help menu entries create a new markdown file (`.md`) somewhere inside the `_YOUR_LANGUAGE.lproj` folder and add the following content: 
```
---
title: YOUR_TITLE
group: YOUR_GROUP
---
```

`YOUR_TITLE` will automatically be added to the sidebar in the category `YOUR_GROUP`. 

### Add a new translation

To create a translation for a new language, copy and paste the folder `_English.lproj` and rename it to `_YOUR_LANGUAGE.lproj` e.g. `_German.lproj`. Change the content of the markdown files inside the newly created folder to your prefered language. 

### Debug changes

Execute `./jekyll-server.command`. A new tab in Safari will be opened with the help menu pages. Make your changes and reload the Safari page to see your changes. 
