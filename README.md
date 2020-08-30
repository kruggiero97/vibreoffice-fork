# vibreoffice

Vim modal editing/keybindings and more for LibreOffice/OpenOffice **Calc**/Writer/Impress/Drawing
This is a fork of [seanyeh](https://www.github.com/seanyeh/vibreoffice) original extension with major updates from [JMagers](https://www.github.com/JMagers/vibreoffice) and [fedorov-ao](https://www.github.com/fedorov-ao/vibreoffice).  Nice work guys! *However, there was no Calc support.*

The primary focus of this fork is to provide **vim keybindings for calc**.

As mentioned, the original extension for Libreoffice/OpenOffice didn't support Calc, but provided support for Writer/Impress/Drawing. IMO a spreadsheet is a perfect example where vim's modal editing is a great way to work. There is already an extension for Excel, [ExcelLikeVim](https://github.com/kjnh10/ExcelLikeVim), Google Sheets has a good extension for chrome/firefox [sheetkey](https://github.com/philc/sheetkeys). But there was none that I could find for calc! and hence I added the functionality to vibreoffice.

*But please note this fork is also at an experimental stage.*

Presently, the following vim like features are supported in Calc, while this and more are supported in writer.
- Insert (`i`, `I`, `A`), Visual (`v`), Normal modes
- Movement keys: `hjkl`, `w`, `b`, `e`, `$`, `0`, `gg`, `G`,`C-d`, `C-u`
    - Plus movement and number modifiers: e.g. `5w`, `4j`
- Number modifiers: e.g. `5w`
- Deletion: `x`, `d`, `c`, `s`, `D`, `C`, `dd`, `cc`
- Undo/redo: `u`, `C-r`
- Copy/paste: `y`, `p`, `P` (using system clipboard, not vim-like registers)
- Calc Specific
    - Sheet Motion: `J`, `K`
    - Insert Row: `o`, `O`

### Installation/Usage

The easiest way to install is to download the
[latest extension file](https://raw.github.com/yamsu/vibreoffice/master/dist/vibreoffice-0.4.2.oxt)
and open it with LibreOffice/OpenOffice.

To enable/disable vibreoffice, simply select Tools -> Add-Ons -> vibreoffice. You may find it more useful to add a keyboard shortcut such as Alt-v to the above menu item.




### Readme from original 

*(Unfortunately, vibreoffice is still in an experimental stage, and I no longer have much time to work on it. Hope you enjoy it anyway!)*

vibreoffice is an extension for Libreoffice and OpenOffice that brings some of
your favorite key bindings from vi/vim to your favorite office suite. It is
obviously not meant to be feature-complete, but hopefully will be useful to
both vi/vim neophytes and experts alike.

### Installation/Usage Old

The easiest way to install is to download the [latest extension file]() and open it with LibreOffice/OpenOffice.

To enable vibreoffice for current window, select `Tools` -> `Add-Ons` -> `vibreoffice - start`; to disable - `vibreoffice - stop`; to toggle - `vibreoffice - toggle` or press `Shift-ESC`.  

If you really want to, you can build the .oxt file yourself by running
```shell
# replace 0.0.0 with your desired version number
VIBREOFFICE_VERSION="0.0.0" make extension
```
This will simply build the extension file from the template files in
`extension/template`. These template files were auto-generated using
[Extension Compiler](https://wiki.openoffice.org/wiki/Extensions_Packager#Download).


### Features

vibreoffice currently supports:
- Insert (`i`, `I`, `a`, `A`, `o`, `O`), Visual (`v`), Normal modes
- Movement keys: `hjkl`, `w`, `W`, `b`, `B`, `e`, `$`, `^`, `{}`, `()`, `C-d`, `C-u`
    - Search movement: `f`, `F`, `t`, `T`
- Number modifiers: e.g. `5w`, `4fa`
- Replace: `r`
- Deletion: `x`, `d`, `c`, `s`, `D`, `C`, `S`, `dd`, `cc`
    - Plus movement and number modifiers: e.g. `5dw`, `c3j`, `2dfe`
    - Delete a/inner block: e.g. `di(`, `da{`, `ci[`, `ci"`, `ca'`, `dit`
- Undo/redo: `u`, `C-r`
- Copy/paste: `y`, `p`, `P` (using system clipboard, not vim-like registers)

### Known differences/issues

If you are familiar with vi/vim, then vibreoffice should give very few
surprises. However, there are some differences, primarily due to word
processor-text editor differences or limitations of the LibreOffice API and/or
my patience.
- Currently, I am using LibreOffice's built-in word/sentence movement which
  differs from vi's. It's sort of broken now but I plan to fix it eventually.
- The concept of lines in a text editor is not quite analogous to that of a
  word processor. I made my best effort to incorporate the line analogy while keeping
  the spirit of word processing.
    - Unlike vi/vim, movement keys will wrap to the next line
    - Due to line wrapping, you may find your cursor move up/down a line for
      commands that would otherwise leave you in the same position (such as `dd`)
- vibreoffice does not have contextual awareness. What I mean by that is that
  it does not keep track of which parentheses/braces match. Hence, you may have
  unexpected behavior (using commands such as `di(`) if your document has
  syntatically uneven parentheses/braces or nesting of such symbols. I don't
  intend to fix this for now, as I don't believe this is a critical feature for
  word processing.
- Using `d`, `c` (or any of their variants) will temporarily bring you into
  Visual mode. This is intentional and should not have any noticeable effects.

### License
vibreoffice is released under the MIT License.
