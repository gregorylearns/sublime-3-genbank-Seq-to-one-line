# GenBank Sequence to one line - Sublime 3 config file 

A Sublime 3 config file for the Plugin - RegReplace that converts GenBank sequences into one line text.
This is done by using regular expressions to remove all occurrences of newlines (\n), spaces ( ) and numbers (\d)

# Usage

* Copy and paste a sequence file from GenBank and paste it to a new sublime window
Press `Ctrl` + `Shift` + `P` to open the command palette.
* Type `Reg Replace: Genbank Sequence to One Line` and press `Enter`.

# Installation

* Open the command palette on Sublime Text 3 by Pressing `Ctrl` + `Shift` + `P`
* Type `Package control install` and select `Package Control: Install Package`. Wait for a bit for it to load.
* Search for `RegReplace`, press `Enter`.

* Click the `Preferences` menu > `Package settings` > `RegReplace` > `Rules - User`.
* Paste the code below. This adds the following text to the `reg_replace_rules.sublime-settings` file in your `Packages/User` folder
```
{
	"replacements":
	{
		"remove_digits":
		{
			"find": "\\d",
			"name": "remove_digits",
			"replace": ""
		},
		"remove_newlines":
		{
			"find": "\\n",
			"name": "remove_newlines",
			"replace": ""
		},
		"remove_spaces":
		{
			"find": " ",
			"name": "remove_spaces",
			"replace": ""
		}
	}
}

```
* Next step is to add the option to the `Default.sublime-commands` file.
* Click the `Preferences` menu > `Package settings` > `RegReplace` > `Commands - User` in your `Packages/User` folder.
* Paste the code below.
```
[
{
    "caption": "Reg Replace: Genbank Sequence to One Line",
    "command": "reg_replace",
    "args": {"replacements": ["remove_spaces", "remove_digits", "remove_newlines"]}
}
]
```

