# EplPrinter App - elpprinter-releases

### Description

The app is using for transmit request from browser to thermal printer queue.
Supported file formats:  zpl, epl, epl2

### App modes:

Application works in several modes:

- **WebServer**
	- Webserver GET link: [http://localhost:33777/?urls={url1},{url2},{...},{urlN}](http://localhost:33777/?urls={url1},{url2},{...},{urlN})
	- Examples:
		- [http://localhost:33777/?urls=zprn://url|example.com|/url_path,url|domain|/url_path2,url|domain|/url_path3](http://localhost:33777/?urls=zprn://url|example.com|/url_path,url|domain|/url_path2,url|domain|/url_path3)
		- [http://localhost:33777/?urls=zprn://url|example.com|/url_path,zprn://url|domain|/url_path2,zprn://url|domain|/url_path3](http://localhost:33777/?urls=zprn://url|example.com|/url_path,zprn://url|domain|/url_path2,zprn://url|domain|/url_path3)
		- [http://localhost:33777/?urls=https://example.com/url_path,http://example.com/url_path2,https://domain/url_path3](http://localhost:33777/?urls=https://example.com/url_path,http://example.com/url_path2,https://domain/url_path3)

- **Print from file**

User might choose print from file option.

- **Support of zprn:// protocol**
	 - [zprn://url|example.com|/url_path,url|domain|/url_path2,url|domain|/url_path3](zprn://url|example.com|/url_path,url|domain|/url_path2,url|domain|/url_path3)
	 - [zprn://https://example.com/url_path,http://example.com/url_path2](zprn://https://example.com/url_path,http://example.com/url_path2)

- **Listener of Downloads folder** (available in advanced config)

If this mode enabled and folder has been defined - application will print all zpl, epl and epl2 files right after they downloaded/pasted there.

- **Support multi-printer**
	-   [http://localhost:33777/?urls=zprn://url|example.com|/url_path,url|domain|/url_path2#print_secondary](http://localhost:33777/?urls=zprn://url%7Cexample.com%7C/url_path,url%7Cdomain%7C/url_path2#print_secondary)
	- [http://localhost:33777/?urls=https://example.com/url_path,http://example.com/url_path2#print_secondary](http://localhost:33777/?urls=https://example.com/url_path,http://example.com/url_path2#print_secondary)

If there was set up 2 printers will be enough to add in URL number of printer, or named number: (#printer2|#print_secondary). If no definition of expected printer for URL - default printer will be used, the first one in UI.
