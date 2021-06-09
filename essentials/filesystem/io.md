# IO

The `upcore:filesystem.io` class provides utility methods for reading and writing bytes to & from the disk.

## `get(path string) fs_object`

Gets the filesystem object at that path.

## `read(file file) primitivearray<byte>`

Reads all the data in a file as a `primitivearray` of bytes.

## `beginwrite(file file, firstByte byte, append bit)`

Starts writing to the specified file with the first byte to add, and whether to append.

Beginning a new write is not allowed until the write is finished.

## `write(byte byte)`

Continues writing to the file.

## `finishwrite(lastByte byte)`

Writes a final to the file and finished the write.