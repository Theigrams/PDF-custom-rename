# Zotero PDF Rename

[![Using Zotero Plugin Template](https://img.shields.io/badge/Using-Zotero%20Plugin%20Template-blue?style=flat-round&logo=github)](https://github.com/windingwind/zotero-plugin-template)
[![Latest release](https://img.shields.io/github/v/release/Theigrams/zotero-pdf-custom-rename)](https://github.com/Theigrams/zotero-pdf-custom-rename/releases)
![Release Date](https://img.shields.io/github/release-date/Theigrams/zotero-pdf-custom-rename?color=9cf)
[![License](https://img.shields.io/github/license/Theigrams/zotero-pdf-custom-rename)](https://github.com/Theigrams/zotero-pdf-custom-rename/blob/main/LICENSE)
![Downloads latest release](https://img.shields.io/github/downloads/Theigrams/zotero-pdf-custom-rename/latest/total?color=yellow)

This is a Zotero plugin that allows you to rename PDF files in your Zotero library using custom rules.

**Note**: *This plugin only works on **Zotero 7.0** and above*.

## Usage

Select one or more items in your Zotero library and right click to open the context menu. Select `Rename PDF attachments` from the menu.

<img width="638" alt="image" src="https://github.com/Theigrams/zotero-pdf-custom-rename/assets/26341831/01f7ac99-0898-4a33-8377-a5ab2ed05eb8">


Then the PDF files will be renamed according to the custom rules you set in the plugin preferences(not implemented yet).

### Default rules

This plugin will read the journal name and year from the metadata of the item and rename the PDF file as follows:

```
{short journal name}_{year}_{short title}.pdf
```

For example, the PDF file of the item below will be renamed as `TPAMI_2016_Go-ICP.pdf`.

The `short title` is read from the `Short Title` field of the item. If the `Short Title` field is empty, the plugin will use the `Title` field instead.

### Journal tags

The `short journal name` is generated by selecting the first capital letter of each word in the journal name. For example, `IEEE Transactions on Pattern Analysis and Machine Intelligence` will be converted to `TPAMI`, while `IEEE` will be ignored.

However, `ACM Transactions on Graphics` will be converted to `TG` rather than `TOG` in current version. This is because the word `on` is ignored in the conversion.
A better method is manually adding the short name of the journal in the `Tags` of the item. 

For example, you can add `Jab/#TOG` to the `Tags` of the item, and the plugin will use `TOG` as the short name of the journal.

**Note**: the plugin will first read the `Jab/#` tag in the `Tags` as the short name. If there is no `Jab/#` tag, the plugin will automatically extract the short name from the full name of the journal.

PS: It is recommended to install the plugin [MuiseDestiny/zotero-reference: PDF references add-on for Zotero](https://github.com/MuiseDestiny/zotero-reference) for a better experience.

<img width="1510" alt="Xnip2023-06-22_21-14-44" src="https://github.com/Theigrams/zotero-pdf-custom-rename/assets/26341831/3ad15e33-a6dd-4429-a550-d3f58d9fddc1">


## Future work

- [ ] Add a short cut for the renaming function.
- [ ] Preferences panel to allow users to customize the rules.
- [ ] Better way to extract the short name of the journal.
