# UNR Libraries ArchivesSpace Public User Interface

The UNR Libraries ArchivesSpace PUI customization files and documentation can be found in this repo. 

## Version
These configurations are currently running on version 2.7.1.

## Customizations for this PUI are achieved by two types of edits:
1. Configurations to the core code configuration file config.rb, found at /path/to/aspace/config/config.rb. These configurations are described below.
2. Customizations to the built-in "local" plugin, specifically its "public" directory, found at /path/to/aspace/plugins/local/public/. These customized files are located in this repo's/public/ directory, and are also described below.

## 1. Config.rb
1. Logo: uploaded image file to the "public" plugin (see the file in this repo) and updated the path in config.rb
```
AppConfig[:pui_branding_img] = '/assets/images/logo.png'
```

2. Updated tabs that appear in the main menu. Initially, all lines are commented out and marked as false. The uncommented lines that equal true are edits.
```
## The following determine which 'tabs' are on the main horizontal menu
#AppConfig[:pui_hide] = {}
#AppConfig[:pui_hide][:repositories] = false
#AppConfig[:pui_hide][:resources] = false
#AppConfig[:pui_hide][:digital_objects] = false
AppConfig[:pui_hide][:accessions] = false
#AppConfig[:pui_hide][:subjects] = false
#AppConfig[:pui_hide][:agents] = false
AppConfig[:pui_hide][:classifications] = true
#AppConfig[:pui_hide][:search_tab] = false
```

3. The request button was removed by uncommenting the line below and leaving it with a null value.
```
## the following determine when the request button is displayed
AppConfig[:pui_requests_permitted_for_types] = []
#AppConfig[:pui_requests_permitted_for_types] = []
```

## 2. Local plugin
UNR uses the built-in "local" plugin to customize the public portal of ArchivesSpace. All of the files that we added to this plugin are in this repo, and described below.
* /assets/custom.css - custom CSS file, which overwrites the default styling. Explanations for each overwrite are in the custom.css file itself.
* /assets/images/logo.png - logo image file, to replace the default ArchivesSpace logo; remember, it has to be updated in the config.rb file as well (see above).
* /locales/en.yml - Ruby on Rails vocabulary file, where we set the header title, welcome text on home page, and other standard vocabulary terms throughout the site. Having this file in the plugin overwrites the equivalent file in the core code. 
* /views/shared/_footer.html.erb - customized footer, which is based on and overwrites the equivalent file in the core code.
* /views/shared/_skipnav.html.erb - Adds ARIA landmark to the existing core code
* /views/layout_head.html.erb - this file is used to "activate" the custom css file

Further documentation on theming ArchivesSpace can be found at:
https://github.com/archivesspace/archivesspace/blob/master/CUSTOMIZING_THEMING.md
https://github.com/archivesspace/archivesspace/blob/master/plugins/PLUGINS_README.md
