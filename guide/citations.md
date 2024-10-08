# Citation Management

## Zotero

[Zotero](https://www.zotero.org/) is a free and open-source program that makes it easy to keep all of your references organized, store full-text PDFs, and generate citation entries. It's available for Windows, Mac, and Linux.

Zotero has [connectors](https://www.zotero.org/download/connectors), which are browser plugins that give you a button to click when viewing a journal article, and will import the reference into your Zotero library, and (usually) download and attach the full PDF if available.

[Better BibTeX](https://retorque.re/zotero-better-bibtex) is a useful plugin for Zotero that provides better handling of citation keys and more customization for exporting to BibTeX.

In the Better BibTeX settings you can customize the generated citation keys to suit your style.
For example, to produce citation keys that contain the first author's last name, year of publication, and a single letter identifier at the end to avoid clashes:
```
auth.lower + year + infix(format="%(a)s", start=1)
```
This will result in a citation key like `jones2022a` or `jones2022b` when there are two articles by Jones in the year 2022.

You may also want to trim down some of the extraneous information that Better BibTeX adds to the BibTeX and BibLaTeX citation entires by default. Having the extra data doesn't cause a problem because it won't show up in your compiled document if the bibliography style doesn't use it, but it can be cumbersome scrolling through unneeded information like abstracts.
In the setting "Fields to omit from export" you may want to include something like:
```
rank, keywords, file, abstract, urldate
```

### Syncing Zotero data

There is an optional free account to sync your library and files, with limited storage. If you need more space for attached files (full text) PDFs, you can purchase a storage plan, or with a little bit of setup you can use your favorite file sync program.

The Zotero developers [explain](https://www.zotero.org/support/kb/data_directory_in_cloud_storage_folder) why syncing the library database itself is dangerous.
The easiest workaround is to use the free account to sync the library only, and move/symlink your attachment folder to a sync folder (using [Syncthing](https://syncthing.net/) or [Dropbox](https://www.dropbox.com/) for example).
I found it easiest to keep my entire Zotero folder in sync with Syncthing and simply exclude `*.sqlite` files from syncing.
With this method, the Zotero account sync handles the actual library database, but does not sync the PDFs, which is handled by Syncthing or Dropbox etc.
This also allows for things like custom styles to be kept in sync, and avoids the danger of corrupting the Zotero database.

## EZproxy

[EZproxy](https://en.wikipedia.org/wiki/EZproxy) makes it easier to access subscription items from off campus directly from journal websites, rather than searching through the university library website.

There are browser extensions for [Firefox](https://addons.mozilla.org/en-US/firefox/addon/firefox-ezproxy-redirect/) and [Chrome](https://chromewebstore.google.com/detail/ezproxy-redirect/gfhnhcbpnnnlefhobdnmhenofhfnnfhi?hl=en&pli=1) that add a button to your browser which will take you to your university library's EZproxy redirect straight from a journal's web page.

## [Next - Working with Git](working-with-git.md)
