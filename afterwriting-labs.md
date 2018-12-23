## Install Afterwriting labs for Fountain

~~~
yay -S nodejs-afterwriting
~~~

Usage
-----

**Basics:**

> node awc.js --source my_draft.fountain --pdf screenplay.pdf


This command will convert a script in *my_draft.fountain* file into a PDF and (and save it as *screenplay.pdf*).

If the only difference in file names is the extension, you can simply write:

> node awc.js --source screenplay.fountain --pdf

**Force overwriting:**

The script will prompt you for confirmation if the PDF file already exists. If you want to always overwrite existing files, pass --overwrite option:

> node awc.js --source screenplay.fountain --pdf --overwrite

**Configuration:**

If you need to customize your PDF you can pass a config file:

> node awc.js --source screenplay.fountain --pdf --config config.json

Config File
-----------

The output can be customized using a configuration file as --config parameter.

	{
		"embolden_scene_headers": false,
		"show_page_numbers": true,
		"split_dialogue": true,
		"print_title_page": true,
		"print_profile": "usletter",
		"double_space_between_scenes": false,
		"print_sections": false,
		"print_synopsis": false,
		"print_actions": true,
		"print_headers": true,
		"print_dialogues": true,
		"number_sections": false,
		"use_dual_dialogue": true,
		"print_notes": false,
		"print_header": "",
		"print_footer": "",
		"print_watermark": "",
		"scenes_numbers": "right",
		"each_scene_on_new_page": false
	}


## TODO

Upload configs for script, shooting script, dialogue... whatever I can come up
with.

## Changes

AUR install did not work.  Install from git @ https://github.com/ifrost/afterwriting-labs
