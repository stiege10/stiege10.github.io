---
layout: post
title:  "Hidden folders in zip archive on windows"
date:   2021-04-16
categories: jekyll update
author: mrusa
---

I recently needed to update an existing zip archive generation task in a php script. When testing the script under Mac Os everything worked as expected.

It didn't on my customers end.

My first thought was this could be an issue with the archiver-app, so I booted up a windows machine, downloaded different unarchivers and tried to extract the zip archive.

The results were different with every unarchiver:

- one did not show the new folders at all
- another one showed the folders but they were empty
- the third one showed my folders, but with a leading `\`

This last result got me thinking I was doing something wrong with the paths, since Windows and Mac Os are using a different folder separator.

Indeed it turned out that I was not removing a leading forward-slash, so the folder and files I added to the zip-file were something like `//path/to/filename` instead of `/path/to/filename`.
