# Citation Management

## Zotero

[Zotero](https://www.zotero.org/) is a free and open-source program that makes it easy to keep all of your references organized, store full-text PDFs, and generate citation entries. It's available for Windows, Mac, and Linux.

There is an optional free account to sync your library and files, with limited storage. If you need more space for attached files (full text) PDFs, you can purchase a storage plan, or with a little bit of setup you can use your favorite file sync program.

The Zotero developers explain why syncing the library database itself is dangerous.
The easiest workaround is to use the free account to sync the library only, and move/symlink your attachment folder to a sync folder (using [Syncthing](https://syncthing.net/) or [Dropbox](https://www.dropbox.com/) for example).
I found it easiest to keep my entire Zotero folder in sync with Syncthing and simply exclude `*.sqlite` files from syncing.
With this method, the Zotero account sync handles the actual library database, but does not sync the PDFs, which is handled by Syncthing or Dropbox etc.
This also allows for things like custom styles to be kept in sync, and avoids the danger of corrupting the Zotero database.

[Better BibTeX](https://retorque.re/zotero-better-bibtex) is a useful plugin for Zotero that provides better handling of citation keys and more customization for exporting to BibTeX.

## EZproxy

[EZproxy](https://en.wikipedia.org/wiki/EZproxy) makes it easier to access subscription items from off campus directly from journal websites, rather than searching through the university library website.

There are browser extensions for [Firefox](https://addons.mozilla.org/en-US/firefox/addon/firefox-ezproxy-redirect/) and [Chrome](https://chromewebstore.google.com/detail/ezproxy-redirect/gfhnhcbpnnnlefhobdnmhenofhfnnfhi?hl=en&pli=1) that add a button to your browser which will take you to your university library's EZproxy redirect.
