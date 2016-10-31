# rm

## NAME
rm - remove files or directories

## SYNOPSIS
rm [OPTION] ... FILE ...

## DESCRIPTION
This manual page documents the GNU version of `rm`.`rm` removes each specified file. By default, it does not remove directories.

If a file is unwritable, the standard input is a tty(telepewriter), and the -f or --force option is not given, `rm` prompts the user for whether to remove the file. If the response does not begin with 'y' or 'Y', the file is skipped.

## OPTIONS
Remove (unlink) the FILE(s)

-d, --directory
> unlink FILE, even if it is a non-empty direcory(super-user only; this works only if your system
> supports 'unlink' for nonempty directories)

-f, --force 
> ignore nonexistent files, never prompt

-i, --interactive
> prompt before any removal

--no-preserve-root 
> do not treat '/' specially(the default)

--preserve-root
> fail to operate recursively on '/'

-r, -R, --recursive
> remove the contents of directories recursively

-v, --verbose
> explain what is being done

--help 
> display this help and exit

--version
> output version information and exit

To remove a file whose name starts with a '-', for example '-foo', use one of these commands:

  rm -- -foo
  rm ./-foo

Note that if you use rm to remove a file, it is usually possible to recover the contents of that file. If you want more assurance that the contents are truly unrecoverable, consider using shred.
