# MarkdownEditing

Markdown plugin for Sublime Text. Provides a decent Markdown color scheme (light and dark) with more robust syntax highlighting and useful Markdown editing features for Sublime Text.

![MarkdownEditing](screenshots/light.png)

![MarkdownEditing](screenshots/dark.png)

## Overview

* [Features](#Features)
* [Commands](#Commands)
* [Installation](#Installation)
* [Configuration](#Configuration)
* [License](#License)

## Features

* Asterisks and underscores are autopaired and will wrap selected text
* If you start an empty pair and hit backspace, both elements are deleted
* If you start an empty pair and hit space, the right element is deleted
* backticks are paired
* Left bracket pairing is modified to eliminate the selection and leave the cursor at a point where you can insert a `[]` or `()` pair for a link
* <kbd>⌘</kbd> <kbd>⌥</kbd> <kbd>V</kbd> will paste the contents of the clipboard as an inline link on selected text
* <kbd>⌘</kbd> <kbd>⌥</kbd> <kbd>R</kbd> will paste the contents of the clipboard as a reference link
* <kbd>⌘</kbd> <kbd>⌥</kbd> <kbd>K</kbd> inserts a standard inline link, <kbd>⌘</kbd> <kbd>⇧</kbd> <kbd>K</kbd> inserts an inline image
* <kbd>⌘</kbd> <kbd>⌥</kbd> <kbd>B</kbd> and <kbd>⌘</kbd> <kbd>⌥</kbd> <kbd>I</kbd> are bound to bold and italics (Markdown).
* <kbd>~</kbd> surrounds selected text with `~~` (strikethrough).
* Typing `#` when there's a selection will surround it with `#` to make it a headline. Multiple presses add additional hashes, increasing the level of the header. Once you hit 6 hashes, it will reset to 0 on the next press. The `match_header_hashes` will determine if the `#` are mirrored on both sides or just at the beginning of the line.
* Typing return at the end of a line that begins with hashmarks will insert closing hashmarks on the headline. They're not required for Markdown, it's just aesthetics, and you can change the `match_header_hashes` option in your settings to disable.
* <kbd>⌘</kbd> <kbd>^</kbd> <kbd>1</kbd>  through <kbd>⌘</kbd> <kbd>^</kbd> <kbd>6</kbd>  will add the corresponding number of hashmarks for headlines. Works on blank lines and selected text in tandem with the above headline tools. If you select an entire existing headline, the current hashmarks will be removed and replaced with the header level you requested. This command now respects the `match_header_hashes` preference setting.
* <kbd>⌘</kbd> <kbd>⇧</kbd> <kbd>6</kbd> will insert a footnote and jump to its definition. If your cursor is in a definition, it will jump back to the marker.
* <kbd>⌥</kbd> <kbd>⇧</kbd> <kbd>F</kbd> will locate footnote markers without definitions and insert the marker for the definition
* <kbd>⌥</kbd> <kbd>⇧</kbd> <kbd>G</kbd> will do the same for missing reference links

Keymap for Windows and Linux. Most of them are similar with the keymap on Mac OS X.

* <kbd>Ctrl</kbd> <kbd>Win</kbd> <kbd>V</kbd> will paste the contents of the clipboard as an inline link on selected text
* <kbd>Ctrl</kbd> <kbd>Win</kbd> <kbd>R</kbd> will paste the contents of the clipboard as a reference link
* <kbd>Ctrl</kbd> <kbd>Win</kbd> <kbd>K</kbd> inserts a standard inline link, <kbd>Shift</kbd> <kbd>Win</kbd> <kbd>K</kbd> inserts an inline image
* <kbd>Alt</kbd> <kbd>Win</kbd> <kbd>B</kbd> and <kbd>Alt</kbd> <kbd>Win</kbd> <kbd>I</kbd> are bound to bold and italics (Markdown).
* <kbd>Ctrl</kbd> <kbd>1</kbd> through <kbd>Ctrl</kbd> <kbd>6</kbd> will add the corresponding number of hashmarks for headlines. Works on blank lines and selected text in tandem with the above headline tools. If you select an entire existing headline, the current hashmarks will be removed and replaced with the header level you requested. This command now respects the `match_header_hashes` preference setting.
* <kbd>Ctrl</kbd> <kbd>⇧</kbd> <kbd>6</kbd> will insert a footnote and jump to its definition. If your cursor is in a definition, it will jump back to the marker.

Footnote commands submitted by [J. Nicholas Geist](https://github.com/jngeist) and originated at [geekabouttown](http://geekabouttown.com/posts/sublime-text-2-markdown-footnote-goodness)

There's a long way to go and I have a lot of Python to learn.

## Commands

#### Fix Underlined Markdown Headers

[TODO]

## Installation

#### [Package Control](http://wbond.net/sublime_packages/package_control)

The preferred method of installation is via [Sublime Package Control](http://wbond.net/sublime_packages/package_control).

1. [Install Sublime Package Control](http://wbond.net/sublime_packages/package_control/installation)
2. From inside Sublime Text 2, open Package Control's Command Pallet: <kbd>CTRL</kbd> <kbd>SHIFT</kbd> <kbd>P</kbd> (Windows, Linux) or <kbd>CMD</kbd> <kbd>SHIFT</kbd> <kbd>P</kbd> on Mac.
3. Type `install package` and hit Return. A list of available packages will be displayed.
4. Type `MarkdownEditing` and hit Return. The package will be downloaded to the appropriate directory.
5. Restart Sublime Text 2 to complete installation. Open a Markdown file and this custom theme. The features listed above should now be available.

#### Manual Installation

1. Download or clone this repository to a directory `MarkdownEditing` in the Sublime Text 2 Packages directory for your platform:
    * Mac: `git clone https://github.com/ttscoff/MarkdownEditing.git ~/Library/Application\ Support/Sublime\ Text\ 2/Packages/MarkdownEditing`
    * Windows: `git clone https://github.com/ttscoff/MarkdownEditing.git %APPDATA%\Sublime/ Text/ 2/\MarkdownEditing`
    * Linux: `git clone https://github.com/ttscoff/MarkdownEditing.git ~/.Sublime\ Text\ 2/Packages/MarkdownEditing`
2. Restart Sublime Text 2 to complete installation. Open a Markdown file and this custom theme. The features listed above should now be available.

## Configuration

The plugin contains 3 different Markdown flavors: Markdown, MultiMarkdown, GitHub flavored Markdown. Default is Markdown. If you want to set another one as default, open a Markdown file and select your flavor from the menu: `View > Syntax > Open all with current extension as`. You're done.

You may want to have a look at the default settings files. They are located at:

    Packages/MarkdownEditing/MultiMarkdown.sublime-settings
    Packages/MarkdownEditing/Markdown GFM.sublime-settings
    Packages/MarkdownEditing/Markdown.sublime-settings

In order to activate the dark theme, put this line to your user settings file of the flavor:

    "color_scheme": "Packages/MarkdownEditing/MarkdownEditor-Dark.tmTheme",

If you want to go with your already existing theme, you can reenable it with the same method as dark theme. Keep in mind that, that theme may not cover all the parts of the Markdown syntax that this plugin defines.

When you decide to live with MarkdownEditing plugin, you may want to disable the native Markdown plugin. It's not a requirement but will remove the clutter in your language selection list at bottom right of Sublime Text. To do that, add `Markdown` to your `ignored_packages` list in ST user settings:

    "ignored_packages": [..., "Markdown"],

A simple reminder: Sublime Text has a _Distraction Free_ mode that's great with Markdown writing. Key binding for it: <kbd>Shift</kbd> <kbd>F11</kbd>.

## License

MarkdownEditing is released under the [MIT License](http://www.opensource.org/licenses/MIT).
