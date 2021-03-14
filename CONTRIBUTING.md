> **TL;DR** Add or edit a file in  the "docs" directory or within a "docs/" folder.
> Include the `nav_order` in the page's YALM front matter. 

## Content

All of the content of the website is categorized into the  "docs" folder and writen as single page Markdown files.

A Markdown (.md) file is a plain text file which you can edit with your favorite text editor (or even on GitHub). 

Each file must have "front matter", the section fenced by `---` in the template below. The `nav_order` variable is essential front matter, the optional `title` variable overrides the title infered from the file name. `layout` sets the layout to default.

```
---
layout: default
title: Citing
nav_order: 8
---
```

`nav_order` will set the the navigation order in the sidebar in the [main page](https://gisumd.github.io/COVID-19-API-Documentation/README.html). 

### Add a a new sidebar section
If you want to add a sidebar section:
1. Create a new markdown file in the "docs" folder
2. Set the `nav_order` variable in the YALM front matter
3. Edit and save the file

### Add a nested sidebar section
If you want to add a nested sidebar section:\
1. Create a new folder with in the "docs" folder
2. Create a new markdown file in the "docs" folder
3. Set the `has_children` variable of the parent file to true
	```
	---
	layout: default
	title: Requests
	nav_order: 7
	has_children: true
	---
	```
4. Set the `parent` variable of the children file(s) to the corresponding parent name
	```
	---
	layout: default
	title: Retrieve country and region lists
	nav_order: 1
	parent: Requests
	---
	```
6. Set the `nav_order` variables in the YALM front matter
7. Edit and save the file(s)

See Just the Docs [documentation](https://pmarsceill.github.io/just-the-docs/) for further reference. 

