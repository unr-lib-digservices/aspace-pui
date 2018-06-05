# GW Libraries ArchivesSpace Public User Interface

The GW Libraries ArchivesSpace PUI customizations are fully documented in this repo.

## Customizations for this PUI are achieved by two types of edits:
1. Configurations to the configuration file: config/config.rb. These configurations are described below.
2. Customizations to the built-in "public" plugin-in in plugins/local. These customizations are documented in the files in this repo's public/ directory.

## Config.rb
1. Logo: uploaded image file to the "public" plugin (see the file in this repo) and updated the path in config.rb
```
AppConfig[:pui_branding_img] = '/assets/images/gw_iddol_libraries_wht_rev.png'
```

2. Updated tabs that appear in the main menu. Initially, all lines are commented out and marked as false. The uncommented lines that equal true are edits.
```
## The following determine which 'tabs' are on the main horizontal menu
#AppConfig[:pui_hide] = {}
AppConfig[:pui_hide][:repositories] = true
#AppConfig[:pui_hide][:resources] = false
AppConfig[:pui_hide][:digital_objects] = true
AppConfig[:pui_hide][:accessions] = true
#AppConfig[:pui_hide][:subjects] = false
#AppConfig[:pui_hide][:agents] = false
AppConfig[:pui_hide][:classifications] = true
#AppConfig[:pui_hide][:search_tab] = false
```

3. The citation button and request button were removed by uncommenting two lines below and marking as false.
```
## Enable / disable PUI resource/archival object page actions
AppConfig[:pui_page_actions_cite] = false
#AppConfig[:pui_page_actions_bookmark] = true
AppConfig[:pui_page_actions_request] = false
#AppConfig[:pui_page_actions_print] = true
```