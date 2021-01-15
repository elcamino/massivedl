# massivedl
Download a large list of files in parallel.

![](screenshots/output.gif)

## Usage

Create a file with the downloads, one URL per line
```bash
https://placehold.it/100x100
https://placehold.it/100x101
https://placehold.it/100x102
...
```

Assuming the file was named `urls.txt` we can download the files using
```bash
massivedl -workers 10 -urlfile urls.txt -outdir downloads
```


### Command line parameters
```
-workers <int> (default=10)          : Maximum number of parallel requests
-urlfile <str>                       : Input csv file with the list of urls
-outdir <str> (default='downloads')  : Directory to place the downloads
-skip-existing (default=true)        : Don't download files that already exist locally
-useragent <str>                     : Use this useragent      
-delay <duration>                    : Sleep this long between requests (e.g. 100ms or 2s)
-retries <int>                       : Retry loading a URL this often
```

### Stop and continue later
You can stop and continue downloading later.  
Press `Ctrl+C` then you will have the following dialog.

```bash
...
Do you want to save progress? [Y/n]: yes

Progress has been saved!
Use the following command to continue downloading

	massivedl -load /path/to/savedfile.save
```

