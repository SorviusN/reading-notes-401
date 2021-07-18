# File Manip / System.IO

## FIle and Stream I/O
- File and stream I/O refers to the transfer of data either to or from a storage medium.
- A file is an ordered and named collection of bytes with persistent storage. When working with files, you work with directory paths, disk storage and file / directory names.
- A stream is a sequence of bytes which you can read from and write to a backing store (disks or memory)
- Other kinds of streams besides file streams are network, memory and pipe streams.

Commonly used file and directory classes:
- File: provides static methods for creating/copying/deleting/moving/opening files
- Fileinfo - provides instance methods for creating/copying/deleting/moving/opening files.
- Directory - provides static methods for creating, moving, and enumerating through directories and subdirectories

## Streams
- Abstract base class Stream supports reading and writing bytes. All classes that represent streams inherit from the Stream class. 
- You may Read, Write and Seek from a stream. Reading is transferring data from a stream into data structure (such as array of bytes). Writing means transferring data to a stream from a data source. Seeking is querying and modifying the current pos within a stream. <br>

### Compression
Compression means reducing the size of a file for storage. Decompression is the process of extracting the contents of a compressed file so they are in a usable format.<br>
 The System.IO.Compression namespace has types for compressing/decompressing files and streams
## Write/Read to a file
Use a Program named StreamWriter to write to a file inside of a program.
``` cs
class Program {
    static void Main(string[] args) {
        // Create string array with lines of text.
        string[] lines = { "First line", "Second line" };

        // specifying where we want the document path to be.
        string docPath = Environment.GetFolderPath(Environment.SelectedFoler.Mydoc);

        //Write the string array to a new file named "Writelines.txt".
        using (StreamWriter sw = new StreamWriter(Path.Combine(docPath, "WriteLines.txt")))
        {
            for each line in the lines array, write it to the sw.
            foreach (string line in lines)
                sw.WriteLine(line);
        }
    }
}
```
for Writing (using FileStream (fs): https://docs.microsoft.com/en-us/dotnet/standard/io/how-to-read-and-write-to-a-newly-created-data-file
