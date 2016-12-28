# Hello, World! for NodeCG

This is a minimum viable [NodeCG](https://github.com/nodecg/nodecg) bundle for learning and demonstration. Only package.json and graphics/index.html are needed for this case. package.json has the near minimum required, and graphics/index.html is a simple html "Hello, World!' with an internal style sheet to make the text big, centered and white with black shadowing.

## Installation

- Install NodeCG and any dependencies
- Copy or clone this repo into the bundles/ folder
- `nodecg start` or `node index.js` from the top-level NodeCG folder.
- Point client (web browser or OBS BrowserSource) to <http://localhost:9090/graphics/midnightfreddie-hello-nodecg/index.html> (set OBS BrowserSource width to 1920 and height to 1080)
- For educational purposes, browse to <http://localhost:9090/>, use menu to go to Graphics and view the graphics info there including URL and size.

![Screenshot of "Hello, World!" in OBS](http://www.midnightfreddie.com/images/2016/obs-nodecg-helloworld.png)

## Terms

- bundle - In NodeCG this is an npm module containing graphics, dashboard items and/or extensions as a kind of plug-in for a NodeCG instance.
- graphics - These are HTML pages. It's that simple. And that complex. The HTML page is what the client (usually an [OBS](https://github.com/jp9000/obs-studio) BrowserSource) accesses, and all the power of HTML, DOM, JavaScript, Canvas, SVG, etc. is available to create the "graphics" imagery/text/animation for the client. The HTML and dependent files are located in the graphics/ folder.
- dashboard - The NodeCG dashboard is a web-based control panel for the NodeCG instance. Bundles defining a dashboard panel will have an html file under dashboard/ , usually (always?) dashboard/panel.html . In this simple "Hello, World" example bundle with only a graphic, you can still go to the dashboard, use the menu to choose "Graphics" and get the client URL for the graphics page.
- extension - I haven't dug far into this yet, but it appears to be the way too add functionality such as listening for tweets, Twitch comments, subscriptions and tips, etc., and then triggering events for the graphics pages to act upon. Code for these goes under extention/ , usually (always?) extention/index.js .

## Required files

- package.json - This is required, and its contents are described in the [NodeCG manifest tutorial](https://github.com/nodecg/nodecg/blob/master/tutorials/manifest.md).
- One or more of the following, depending upon bundle contents. These all need references in package.json; I'm not yet sure if these exact names are required or just conventional. The directory names appear to be mandatory, though. Naturally there may be many supporting files.
    - graphics/index.html
    - dashboard/panel.html
    - extension/index.js

## Other files

At first the sheer number of files and folders in example bundles confused me, which is why I started this project. Here is some help as to the other types of files. If you don't know what they are, you don't need them. They are more about managing development, testing and deployment than making broadcast graphics.

- node_modules/ - This will appear and be empty in bundle folders due to the use of package.json as a bundle configuration tool. It can be ignored. Any npm dependencies are installed into the top-level NodeCG node_modules folder.
- bower.json - This is a Bower package manager dependency listing. It tells Bower what dependent javascript libraries to download.
- .travis.yml - Build, test and deploy automation. Cool DevOps-ey stuff that gets triggered when developing and git'ing and such. Often responsbile for the pass/fail badges on GitHub readme pages.
- .eslintrc - Developer tool config file to help keep javascript code pretty and organized.
- .gitignore - For keeping temporary  and extra files out of git and GitHub repos
