# Vivaldi-Thumbs-Replacer
Replaces the thumbnails of Vivaldi browser's speed dial with your own.

> **Note**  
> As of [version 1.10](https://vivaldi.com/blog/vivaldi-powers-up-the-start-page-and-adds-docked-dev-tools/) Vivaldi provides the possiblity to change the speed dial thumbnails via its interface. However you can still use this script to automate this process.

## Description
This scripts automates the replacement of the Vivaldi browser's bookmark thumbnails in the speed dial. The user needs to provide the custom thumbnails for the script himself.

This script was tested in **Windows** and **OS X** but should also work with **Linux** or any other operating system supporting Python and Vivaldi.


## Dependencies
This Python script was tested with **Python 3.5**. It should work with all Python 3.x versions but if you want to be sure just use this version.

The script depends on the Python packages `os`, `shutil`, `json` and `sqlite3` which are all included in the standard library of Python 3.5.

## Using the script

### Step 1
Download the file *vivaldiThumbsReplacer.py* and open it with a text editor. You must replace 4 path variables inside the script itself. Look for the lines:

```
topSites_path = "Path to 'Top Sites' file"
bookmark_path = "Path to 'Bookmarks' file"

backup_path = "Path to Backup directory"
customThumbs_path = "Path to directory with thumbnails"
```

The names are pretty self explanatory.

| Name | Description | Path |
|------|-------------|---------|
| `topSites_path` | Stores the path to the "Top Sites" file of Vivaldi which stores the thumbnails. | Windows: `C:/Users/<User>/AppData/Local/Vivaldi/User Data/Default/Top Sites` <br/> OS X: `/Users/<User>/Library/Application Support/Vivaldi/Default/Top Sites` |
| `bookmark_path` | Stores the path to the "Bookmark" file of Vivaldi which stores among other things the bookmark id and its name. | Windows: `C:/Users/<User>/AppData/Local/Vivaldi/User Data/Default/Bookmarks` <br/> OS X: `/Users/<User>/Library/Application Support/Vivaldi/Default/Bookmarks` |
| `backup_path` | Specifies where (directory) a backup of "Top Sites" is stored. | Windows E.g. `C:/Users/<User>/Desktop/` |
| `customThumbs_path` | Specifies the directory where the custom thumbnails can be found. | Windows E.g. `C:/Users/<User>/Pictures/Custom Thumbnails/` |

**Important:**

* You need to replace `<User>` with your own user name.
* When modifying or replacing the paths make sure you only use `/`. You need to replace all backslashes when copying a Windows path from the explorer!

### Step 2
Make sure every entry in your speed dial has a descriptive name. This is not required but helps later.

### Step 3
Execute the Python script `vivaldiThumbsReplacer.py`. If everything went right it should look like this:

![1st execution](https://raw.githubusercontent.com/larsgru/Vivaldi-Thumbs-Replacer/master/pics/first_exec.png)

### Step 4
Create and save your own thumbnail to be used. An optimal thumbnail has the dimensions **440 x 360 Pixels**. Tipp: The smaller the picture size is, the faster Vivaldi should load it.

The name of your thumbnail must be predated with the bookmark id of the respective thumbnail. You can get the id by simply running the script which lists all ids it found on the speed dial. In the example in Step 3 we can see that we need to name our thumbnail `216_github.png`. (What you write after the `_` doesn't matter.)

### Step 5
Close Vivaldi and execute the script again. If you have done everything right it should look like this:

![2nd execution](https://raw.githubusercontent.com/larsgru/Vivaldi-Thumbs-Replacer/master/pics/second_exec.png)

Vivaldi should now display the new thumbnail.

## Contact
If you have any problems, questions or improvements feel free to create an issue regarding the topic.

## References

[1] Vivaldi-Forum: https://vivaldi.net/en-US/forum/all/7257-customising-your-speed-dial-thumbs
