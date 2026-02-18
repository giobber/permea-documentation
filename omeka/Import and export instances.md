# How to import and export omeka instances

Official documentation: [link](https://omeka.org/s/docs/user-manual/importexport/)

## Backup and restore between two omeka instances 
Omeka don't allow for a complete backup and restore routine, some steps are intended to be handled by the site administrator
- Additional modules and specific settings must be set before importing 
- Sites, Pages, Custom Vocab must be recreated manually
- Resource templates must be exported separately (see [this guide](https://omeka.org/s/docs/user-manual/content/resource-template/#import-a-resource-template))
- Item and Item sets can be moved via the [Item Importer module](https://omeka.org/s/docs/user-manual/modules/ositemimporter/)

### Prepare your new instance
WIP
- You want to reinstall all modules
- ...

### Restore Resource Templates
- You need to export each Resource Template individually (I use .json format)
- You need to import each Resource Template individually

### Restore Items and Item Sets
- Use Omeka S Item Importer module
- Insert api link (like in case of permea: https://permea.afor.dev/omeka/api)
- Go to ...
- During importing map resource templates to corresponding ones
- During importing map field types
- Remember to click submit in the top right corner after making changes
- Do the last step and you should find the contents imported

## YuNoHost strategy
TBD

## Docker Strategy
TBD
