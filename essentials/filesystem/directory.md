# Directory

`upcore:filesystem.directory` represents a directory on the disk.

## `path string`

`directory.path` is the complete path to the directory, from the root folder, including the root folder.

The path separator should ALWAYS be `/`, even on Windows - never `\`.

### Examples

Linux: `/home/user/Documents`

MacOS: `/Users/user/Documents`

Windows: `C:/Users/user/Documents`

## `name string`

`directory.name` is the name of the directory.

### Example

`Documents`

## `parent directory`

`file.parent` is the directory which contains the file.

## `get_fsobjects() primitivearray<fsobject>`

`get_fsobjects()` gets all of the FS objects in the directory, in a read only `primitivearray`.

## `get_files() primitivearray<file>`

`get_files()` gets all of the files in the directory, in a read only `primitivearray`.

## `get_subdirs() primitivearray<directory>`

`get_subdirs()` gets all of the subdirectories in the directory, in a read only `primitivearray`.
