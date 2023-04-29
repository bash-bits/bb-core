# [📑 API](README.md)

## ✨`Including BB-Import`

There are 2 ways to make use of `BB-Import`;

The first is to install it to a directory that is on your `$PATH` (defaults to `/usr/local/bin/bb-import`) and include it as part of the Shebang at the top of each file:

```shell
#!/usr/bin/env bb-import

or 

bb-import <opt>
```

Or, you can install it under your home directory and `source` it wherever you want to use it:

```shell
source /home/user/.bb/bb-import.sh
```

Most API functions, therefore, can be called 2 different ways and each is identified hereafter like so:

🔹= shebanged / executed

🔸= sourced


## 🔹 `bb-import '$url'`
## 🔸 `bb::import '$url'`

The core `bb-import` function, downloads the script defined by the `$url` argument and caches it to the local file system.  Finally, it sources the downloaded script, making it instantly available to you.

```shell
#!/usr/bin/env bb-import

bb-import bb-functions/string


echo "$string" | string::toUpper
# STRING
```

<br />


## 🔹 `bb-importFile '$url'`
## 🔸 `bb::importFile '$url'`

Uses the same download and caching infrastructure as `bb-import`, but prints the local file path instead of sourcing the file.  This gives you the ability to work with arbitrary files such as scripts from other languages, simple data files, binary files, etc.

```shell
#!/usr/bin/env bb-import

php "$(bb-importFile https://raw.githubusercontent.com/organisation/repo-name/branch/path/file.php)"
```

[`^ Top`](#-api)
