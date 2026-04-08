---
{"dg-publish":true,"permalink":"/260407-obsidian-como-fazer-buscas-pesquisas-searches/","dg-note-properties":{}}
---

Search operators enable more fine-grained search terms to filter your results even more.

Some operators even allow you to add a nested search term within parentheses, for example: `task:(call OR email)`.

|Search operator|Description|
|---|---|
|`file:`|Find text in filename. Matches any file in the vault.<br><br>Example: `file:.jpg` or `file:202209`.|
|`path:`|Find text in file path. Matches any file in the vault.<br><br>Example: `path:"Daily notes/2022-07"`.|
|`content:`|Find text in file content.<br><br>Example: `content:"happy cat"`.|
|`match-case:`|Case-sensitive match.<br><br>Example: `match-case:HappyCat`.|
|`ignore-case:`|Case-insensitive match.<br><br>Example: `ignore-case:ikea`.|
|`tag:`|Find tag in file.<br><br>Example: `tag:#work`.<br><br>Keep in mind that searching for `tag:#work` will not return results for `#myjob/work`.  <br>  <br>**Note**: Since `tag:` ignores matches in code blocks and in non-Markdown content, it's often faster and more accurate than a normal full-text search for `#work`.|
|`line:`|Find files that contain at least one line matching `x`.<br><br>Example: `line:(mix flour)`.<br><br>  <br>**Note:** Using `-line` negates the search, meaning it will find files where no line matches `x`.|
|`block:`|Find matches in the same block.<br><br>Example: `block:(dog cat)`.<br><br>**Note**: Since `block:` requires Search to parse the Markdown content in every file, it can cause your search term to take longer time to finish.|
|`section:`|Find matches in the same section (text between two headings).<br><br>Example: `section:(dog cat)`.|
|`task:`|Find matches in a [task](https://obsidian.md/help/syntax#Task%20lists) on a block-by-block basis.<br><br>Example: `task:call`.|
|`task-todo:`|Find matches in an _uncompleted_ [task](https://obsidian.md/help/syntax#Task%20lists) on a block-by-block basis.<br><br>Example: `task-todo:call`.|
|`task-done:`|Find matches in a _completed_ [task](https://obsidian.md/help/syntax#Task%20lists) on a block-by-block basis.<br><br>Example: `task-done:call`.|

## Search properties 

You can use data stored in [Properties](https://obsidian.md/help/properties) in your search terms.

Use brackets around a property name `[property]` to return files with that property:

- `[aliases]` returns files that contain the `aliases` property

Use brackets and a colon `[property:value]` to return files with that property and value:

- `[aliases:Name]` returns files where the `aliases` property value is `Name`

Use `null` as a value to find properties that have no value:

- `[aliases:null]` returns files where the `aliases` property exists but has no value

Empty values

The `null` operator works when a property is empty (e.g., `aliases:` ), but not when the property contains empty quotes (`""`) or empty brackets (`[]`).

Both property and value allow sub-queries, such as parentheses for grouping, the `OR` operator, double-quotes for exact matching, and regex.

- `[status:Draft OR Published]` returns files where the `status` property value is `Draft` or `Published`