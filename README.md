PencilCode GSOC Pre-project - Visual Thumbnails
===============================================
[![Build Status](https://travis-ci.org/PencilCode/pencilcode.png?branch=master)](https://travis-ci.org/PencilCode/pencilcode)

## Visual Thumbnails Pre-project

This project is to create a server-side component that runs student programs to create visual thumbnails of each one, and that displays those thumbnails when browsing projects.

There are several possible approaches, and also several challenges.

 - A headless webkit could be used to run the student programs; but the programs need to be run quickly, without animation, to be able to render a program at a reasonable speed.
 - Or, after a student runs the program, a browser-side function could render the page into an offscreen canvas and send the bitmap to be saved on the server.

The challenge in both cases is to render the output faithfully to what the student sees when actually running the program.

## Implementation Details of Pre-project

Right now the feature is implemented using a browser side library (html2canvas) to capture a html snapshot of the game to a canvas and then an image. This is essential as PencilCode allows arbitrary HTML to be inserted inside the preview pane - therefore capture a canvas snapshot is insufficient for a project thumbnail.

![With Text](/dev/withtext.png?raw=true)
![Canvas Only](/dev/canvas.png?raw=true)
