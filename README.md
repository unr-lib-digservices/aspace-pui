# GW Libraries ArchivesSpace Public User Interface

The GW Libraries ArchivesSpace PUI customization files and documentation can be found in this repo.

## Customizations for this PUI are achieved by two types of edits:
1. Configurations to the configuration file: config/config.rb. These configurations are described below.
2. Customizations to the built-in "local" plugin located in plugins/local/public. These customized files are located in this repo's public/ directory, and described below.

## 2. Local plugin
GW uses the built-in "local" plugin to customize the public portal of ArchivesSpace. 
* /assets/fonts/[fontfile.otf] - font file used by GW is excluded from this repo due to copyright, but would be located here
* /assets/images/gw_iddol_libraries_wht_rev.png - logo image file
* /locales/en.yml - vocabulary file, where we set the header title, welcome text on home page, and other standard vocabulary terms throughout the site. 
* /views/shared/_footer.html.erb - customized footer, which is based on and overwrites what's in the core code
* /views/shared/_header.html.erb - customized header, which is based on and overwrites what's in the core code
* /views/layout_head.html.erb - this file is used to "activate" the header and footer files in views/shared
	

## 1. Config.rb
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