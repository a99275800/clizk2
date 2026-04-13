---
{"dg-publish":true,"permalink":"/45-g52r-config-do-keys-json-em-casa/","dg-note-properties":{}}
---

tags: #internas #admin #tech #proj_zetteltex #caretstuff
parent: [[20180227205711\|20180227205711]] caret stuff, o index

## 20180227205622 config do keys json em casa

Isto é um config para o app Caret

{

  // To disable Caret's key-capture behavior, set a value to null or false

  // for example: "Ctrl-Space": null will defer that combo to the ChromeOS language switcher

  //basic navigation/application keys

  "Ctrl-O": "session:open-file",

  "Ctrl-W": "session:close-tab",

  "Ctrl-S": "session:save-file",

  "Ctrl-Shift-S": "session:save-file-as",

  "Ctrl-Alt-S": "session:save-all",

  "Ctrl-N": "session:new-file",

  "Ctrl-Tab": "session:change-tab",

  "Shift-F3": { "ace": "tolowercase" },

  "Ctrl-Shift-F3": { "ace": "touppercase" },

  "Ctrl-Alt-Shift-S": { "command": "project:generate"},

  "Ctrl-Shift-Tab": { "command": "session:change-tab", "argument": -1 },

  //Chromebook fixes

  "Ctrl-Up": { "ace": "addCursorAbove" },

  "Ctrl-Down": { "ace": "addCursorBelow" },

  "Ctrl-Home": { "ace": "gotostart" },

  "Ctrl-End": { "ace": "gotoend" },

  "Ctrl-PageUp": { "ace": "gotostart" },

  "Ctrl-PageDown": { "ace": "gotoend" },

  "Alt-PageDown": { "ace": "gotopagedown" },

  "PageDown": { "ace": "gotopagedown" },

  "Alt-PageUp": { "ace": "gotopageup" },

  "PageUp": {"ace": "gotopageup" },

  "Alt-Home": { "ace": "gotolinestart" },

  "Home": { "ace": "gotolinestart" },

  "Alt-End": { "ace": "gotolineend" },

  "End": { "ace": "gotolineend" },

  "Ctrl-Space": { "ace": "startAutocomplete" },

  //Sublime compatibility

  "Ctrl-L": { "ace": "expandtoline" },

  "Alt-Q": "sublime:wrap",

  "Ctrl-D": "sublime:select-or-more-after",

  "Ctrl-P": { "command": "palette:open" },

  "Ctrl-Shift-P": { "command": "palette:open", "argument": "command" },

  "Ctrl-R": { "command": "palette:open", "argument": "reference" },

  "Ctrl-G": { "command": "palette:open", "argument": "line" },

  "Ctrl-Shift-F": { "command": "searchbar:show-project-search" },

  "Ctrl-M": { "ace": "jumptomatching" },

  "Ctrl-Shift-M": { "command": "sublime:expand-to-matching" },

  "Ctrl-Q": { "command": "ace:togglemacro" },

  "Ctrl-Shift-Q": { "ace": "replaymacro" },

  "Ctrl--": { "command": "editor:adjust-zoom", "argument": -1 },

  "Ctrl-=": { "command": "editor:adjust-zoom", "argument": 1 },

  "Ctrl-0": { "command": "editor:default-zoom" },

  "Ctrl-J": { "ace": "joinlines" },

  "Ctrl-Shift-K": { "ace": "removeline" },

  "Ctrl-Shift-Up": { "ace": "movelinesup" },

  "Ctrl-Shift-Down": { "ace": "movelinesdown" },

  //dev mode

  "Ctrl-Shift-M": "sequence:test",

  "Ctrl-.": { "command": "app:show-prompt" }

}

