# File

`upcore:filesystem.file` represents a file on the disk.

## `path string`

`file.path` is the complete path to the file, from the root folder, including the root folder.

The path separator should ALWAYS be `/`, even on Windows - never `\`.

### Examples

Linux: `/home/user/Documents/very_important_file.txt`

MacOS: `/Users/user/Documents/very_important_file.txt`

Windows: `C:/Users/user/Documents/very_important_file.txt`

## `name string`

`file.name` is the name of the file, without the extension.

### Example

`very_important_file`

## `fullname string`

`file.fullname` is the name of the file, with the extension.

### Example

`very_important_file.txt`

## `extension string`

`file.extension` is the extension of the file.

### Example

`txt`

## `parent directory`

`file.parent` is the directory which contains the file.