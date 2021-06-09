# FS Object

`upcore:filesystem.fs_object` represents an object on the filesystem of unknown type - it is either a directory or a file.

## `is_file bit`

If the fsobject is a file or not.

## `is_directory bit`

If the fsobject is a directory or not.

## `file ?file`

The file object. Null if not a file.

## `directory ?directory`

The directory object. Null if not a directory.