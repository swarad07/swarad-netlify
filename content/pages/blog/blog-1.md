---
type: PostLayout
title: Testing Visual Studio Code - a not so biased review
date: '2018-10-18'
excerpt: >-
  This is probably the first time I am sharing what I have found when switching
  to something else as my daily code editor.
featuredImage:
  type: ImageBlock
  url: 'https://assets.stackbit.com/components/images/default/post-4.jpeg'
  altText: Post thumbnail image
  caption: Caption of the image
  elementId: ''
media:
  type: ImageBlock
  url: 'https://assets.stackbit.com/components/images/default/post-4.jpeg'
  altText: Post image
  caption: Caption of the image
  elementId: ''
addTitleSuffix: true
colors: colors-a
backgroundImage:
  type: BackgroundImage
  url: /images/bg2.jpg
  backgroundSize: cover
  backgroundPosition: center
  backgroundRepeat: no-repeat
  opacity: 100
author: content/data/team/swarad.json
---
Hello world! Let us get straight to the point, for quite a while now I have been flirting with VSCode aside from my usual PHPStorm IDE which I have been using for many years now. I downloaded VS Code the first day it was available. The idea of a good free “IDE” has always intrigued me.

If you must know, I am one of those who have clear definitions in his head for an IDE and an editor, that will be a separate post. For a large part of my initial career I have used [Eclipse](https://www.eclipse.org/), I remember people using Notepad++ at that time, but Notepad as a everyday code editor never landed right in my mind, even then. But code editors have improved massively since those days, [Sublime Text](https://www.sublimetext.com/), [Atom](https://atom.io/) are worth a mention from the huge list.

This is probably the first time I am sharing what I have found when switching to something else as my daily code editor.

I am in no way an expert, so this is more of an opinionated review. Infact, I am pretty sure many of the problems I faced would be fixable either via some extension or configuration, but sadly I have not yet been able to resolve them.

## Things I like,

1.  Customization - I am firmly on the “dark mode” everything side when it comes to my tools, as someone who stares at the screen for a significant portion of my day, I find that dark modes strain my eyes less than the usual white background. So themes, fonts, and line heights, were something that were easy to find, customize and tailor just the way I wanted.

2.  VS Code advertises [IntelliSense](https://code.visualstudio.com/docs/editor/intellisense) as a code completion and code hinting feature, and from what I have used it works brilliantly, apparently it uses a language service to analyze your source code and provide better completion and from what I have used it was on point.

3.  Faster and less memory consumption - The biggest & the only reason I want to move away from my IDE is that it consumes significant portion of my tiny Macbook’s processing power. A couple of browsers, one terminal, a couple of design tools, slack for messages, zoom for meetings are pretty normal apps which I all use at the same time, so you can see processing power is at a premium (Atleast till I upgrade my machine).

4.  The quick info option for any property is very good, you can quickly see the function defination as you type. ![](https://swarad07.github.io/img/property-info.png)

## Things I didn't link, some were fixable.

1.  Copy Paste Mess - I had to find my inner peace for this one, for some reason, the formatting of the entire file kept getting messed up when I did copy paste. Bit of searching and I wasn't the only one, found this [stackoverflow answer](https://stackoverflow.com/questions/42747498/vs-code-indentation-when-copying-and-pasting-is-messed-up), I honestly dont know why this is ON by default.

2.  Search - autofilling the selected directory as scope. When I tried initially to search by selecting a directory and doing search it always searched in the scope that was last auto-filled or entered manually, I expected it to autofill the directory path where to search based on which directory I selected. Luckily this was an easy fix using the keybindngs option in Code > Preferences > Keyboard Shortcuts. Here you will find all the possible functions you can do and bind them to a shortcut, I added this in keybindings.json,

```
[{"key": "cmd+shift+f","command": "filesExplorer.findInFolder","when": "filesExplorerFocus"}]
```

Now the search autofill works just the way I want on `CMD+SHIFT+F`

## Things I want to find a solution for,

1.  For some reason my Xdebug doesnt work, I use drupal-vm as my local development stack, I am pretty sure something silly I am missing as the instruction [here ](http://docs.drupalvm.com/en/latest/extras/xdebug/)is pretty straightforward to make it work.

2.  (Fix updated below) - When I click on a file in sidebar, it opens in new tab, if I click on a different file it opens again in the same tab closing the previous file. I think this has got to do with whether that file has any change or not, I dont know how to make each file open in a new tab always.

3.  (Fix updated below) - CSS hierarchy - When you hover on selector I get to see the hierarchy of the selectors, this is helpful in SCSS files. But I would love a bar at the bottom similar to how PHPStrom does it, where you see the parents as you type. This saves that additional hover action. ![](https://swarad07.github.io/img/CSS-hierrachy.png)

4.  Search - Old keywords. I find that I often do two separate searches and then have to go back to the old keyword to find a file I had just seen which is now not showing up. But there is no way I see that I can select that old keyword from a dropdown or something and run the old search again.

5.  GIT history view - Finding old revisions of a file, comparing them with current revision or quickly checking out that old revision is all possible, but I feel it is not an optimal UX right now. I have seen other IDEs and editors do this better and I hope VS Code improves this.

## Conlusion

After a long time, I have found a code editor that I can see myself using as my daily driver. Granted I have spent the last few months, switching to VS Code only to find something I dont like, mostly because I have gotten used to my current IDE. What I am really happy about is that for nearly all those things that I didnt like I either to find a workaround or straight up fix it by some config or extension. I am pretty sure if I use it for a month or two (that is the plan as of now) I will find solutions to the above dislikes, Let's see how that goes, probably be another post after that.

Cheers!

## Update

1.  workbench.editor.enablePreview should be false [Link](https://stackoverflow.com/questions/38713405/how-to-config-vscode-to-open-files-always-in-a-new-tab)

```
"workbench.editor.enablePreview":false 
```

1.  Enable breadcrumbs - View > Toggle Breadcrumbs. This shows the CSS hierarchy like I want.

