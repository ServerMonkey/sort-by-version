sort-by-version(1) -- Sorts a list of strings by version number
=============================================

## SYNOPSIS

`<list> | sort-by-version <flags>`

## DESCRIPTION

Sorts a list of strings by version number from stdin.  
For example a list of applications.  
The last version will be the furthest down the list.
Automatically excludes folders and strips the folder name from each line.
The format of each line should be like this: `<NAME>_<VERSION>.<EXT>`  
There can be multiple dots in the version number. The extension must end in `.<EXT>` and can not have multiple dots. Only one underscore is allowed.

## OPTIONS

* `-a`, `--all` :
  Sort and list all versions.

## EXAMPLES

Let's say there is a folder with the following files inside:

```
helloworld_1.0.2.exe
helloworld_1.exe
helloworld_1.1.exe
cowsay_alpha.0.2.exe
cowsay_beta.1.exe
```

To get only the latest version of each file:

    $ find . | sort-by-version

This will return:

```
cowsay_beta.1.exe
helloworld_1.1.exe
```

To get every file but sorted by version:

    $ find . | sort-by-version -a

This will return:

```
cowsay_alpha.0.2.exe
cowsay_beta.1.exe
helloworld_1.exe
helloworld_1.0.2.exe
helloworld_1.1.exe
```

## COPYRIGHT

See license file
