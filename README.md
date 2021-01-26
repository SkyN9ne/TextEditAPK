# ![Logo](src/main/res/drawable-hdpi/ic_launcher.png) Editor ![.github/workflows/main.yml](https://github.com/billthefarmer/editor/workflows/.github/workflows/main.yml/badge.svg) [![Release](https://img.shields.io/github/release/billthefarmer/editor.svg?logo=github)](https://github.com/billthefarmer/editor/releases) [![Available on F-Droid](https://f-droid.org/wiki/images/c/ca/F-Droid-button_available-on_smaller.png)](https://f-droid.org/packages/org.billthefarmer.editor)

Android simple generic text editor. The app is available from
[F-Droid](https://f-droid.org/packages/org.billthefarmer.editor)
and [here](https://github.com/billthefarmer/editor/releases)

![Editor](https://github.com/billthefarmer/billthefarmer.github.io/raw/master/images/Editor.png) ![Editor](https://github.com/billthefarmer/billthefarmer.github.io/raw/master/images/Editor-chooser.png)

![Editor](https://github.com/billthefarmer/billthefarmer.github.io/raw/master/images/Editor-landscape.png)

![Editor](https://github.com/billthefarmer/billthefarmer.github.io/raw/master/images/Editor-syntax.png)

This is a fairly simple generic text editor which may be used
standalone or to show or edit any sort of text file from another
app. If you select a text file in a file manager or similar app you
will be offered the option of using this editor along with whatever
other apps you have installed that can show or edit a text file. Files
will initially be opened read only, long touch on the display or touch
the edit item in the toolbar to enable editing.

There are five toolbar items which may appear:
* **Edit** &ndash; Edit the current read only file
* **View** &ndash; View the current file read only
* **Save** &ndash; Save the current file if modified
* **New** &ndash; Start a new empty file
* **Open** &ndash; Open a text file using a chooser

And on the menu:
* **Open recent** &ndash; Pop up a list of recent files
  * **Clear list** &ndash; Clear list of recent files
* **Search** &ndash; Interactive search of text using a regular
    expression
* **Find all** &ndash; Find all recent files containing search text
* **Save as** &ndash; Save the current file with a new name
* **View markdown** &ndash; View markdown in browser or html viewer
* **View files** &ndash; Open files read only for viewing
* **Auto save** &ndash; Save the current file on app pause
* **Word wrap** &ndash; Limit text width to screen width and word wrap
* **Suggestions** &ndash; Text input and spelling suggestions
* **Highlight syntax** &ndash; Highlight programming language syntax
* **Theme** &ndash; Choose theme
  * **Light**
  * **Dark**
  * **Retro**
* **Text size** &ndash; Choose text size
  * **Small**
  * **Medium**
  * **Large**
* **Typeface** &ndash; Choose typeface
  * **Monospace**
  * **Proportional**
* **About** &ndash; Show version, copyright and licence

### Edit
Edit the current read only text.

### View
View the current file read only.

### Save
Save the current file if modified.

### New
Start a new empty file. Use the **Save as** item to save the new file.

### Open
Choose a file to open from the chooser dialog that pops up. The parent
folder will be the first in the list. See [File
Chooser](Chooser.md). The file will initially be read-only. Touch the
**Edit** toolbar item to enable editing.

### Open recent
Choose a file from the list that pops up. As above the file will
initially be read only. The last entry, **Clear list**, will clear the
list.

### Save as
Enter a new file name in the dialog that pops up. Absolute names
starting with a slash '/' will be saved in that exact path if
possible. Names without a starting slash will be saved relative to the
main public folder, `/sdcard/`, or `/storage/emulated/0/`.

### Search
Enter search text in the field that pops up in the toolbar. The first
matching item will be highlighted. Use the search button in the
keyboard for find next. The exact regular expression syntax used is in
the android documentation for
[Pattern](https://developer.android.com/reference/java/util/regex/Pattern#sum).

### Find all
You may find all recent files that contain the current search
text. This menu item will only appear while the search widget is
active. A dialog will pop up with a list of matching files. Touch an
entry to open that file. You may repeat this or refine the search text
to find the desired file.

### View markdown
You will be prompted to choose a viewer for an html file containing
the encoded markdown from the current open file. If the text contains
no markdown the result will be the same text.

### Highlight syntax
If the current open file is a C, C++, Objective C, Go, Java,
Javascript, Python, Shell script, Swift, CSS, HTML or Markdown file,
the keywords, classes comments, strings, etc will be highlighted. See
[Syntax Highlighting](Syntax.md).

### Mode line
If a line of text is found within the first or last two or three lines
of the file which matches the mode line pattern, the mode of the
editor will be changed after the file is loaded. See [Mode
line](Mode.md).
```
# ed: [[no]vw] [[no]ww] [[no]sg] [[no]hs] [th:l|d|r] [ts:l|m|s] [tf:m|p]
```

### Extended selection
If the file being edited is not a plain text file, selections created
by double tapping or long touching on the text will be extended to
enclosing delimiters (brackets, quotes) on the same text line.

### Unsaved file
If you touch the new, back or open button, and the current file has been
modified, you will be prompted whether you want to save it, else the
editor will just exit or open a file chooser. The current file may be
saved on app pause using the menu option. The scroll position and name
will be remembered for the last 10 files opened.

### Changed file
If a file has changed in storage while it was open in the editor, if
you attempt to save it, or the app is resumed, you will be prompted
whether to overwrite or reload the file.

### Default file
If there is no open file any text entered will by default be saved in
`Documents/Editor.txt`. This file will be loaded on start if it
exists. Use the `Save as` menu item to save it elsewhere.

### Shared file
Text files opened or shared by another app may be viewed and
edited. Some apps may share files or text using a `content` URI that
is not resolvable to a path to a file in storage. In that case the
editor will read the file into the default file. The default file in
storage will not be overwritten. The **Save** item will save the file
in the original location if possible. Use the **Save as** menu item to
save the file elsewhere.

## SD cards
Android allows removable SD cards to be used like a USB stick or as
part of the device storage. Editing files on a removable SD card not
part of the device storage may work on some devices, but is not
supported.
