## I/O, Files and Directories
- Input/Output (I/O) is a core feature that allows application to read and write data. Java provides rich set of classes and interfaces for handling I/O operations efficiently
- Java also offers the File class for file and directory management, which provides methods to create, delete, rename, and manipulate files and directories

- [Java I/O Overview](#java-io-overview)
- [Java I/O InputStream and OutputStream](#java-io-inputstream-and-outputstream)
- [Java I/O Reader and Writer](#java-io-reader-and-writer)
- [Files and Directories in Java](#files-and-directories-in-java)
- [Java Paths and File System](#java-paths-and-file-system)

### Java I/O Overview
- Java I/O (Input/Output) is a part of java.io package, a mechanism to read and write data into a file, network connection, or console
- This package provides classes to manage input and output streams, readers, writers, and files
- THere are two types of streams in Java: Byte Streams and Character Streams
- Byte Streams: handle I/O of raw binary data, used for reading and writing binary data
- Character Streams: handle I/O of character data, automatically handle character encoding and decoding

ChatGPT Prompt:
```
Can you elaborate on the differences between Byte Streams and Character Streams in Java I/O?
```

### Java I/O InputStream and OutputStream
- InputStream and OutputStream are the abstract classes that provide methods to read and write data in byte-oriented manner, respectively
- InputStream has methods like `read()` is used to read data from a source, while OutputStream has `write()` is used to write data to a destination
- There are many subclasses of these, like FileInputStream, FileOutputStream, for reading and writing files.

ChatGPT Prompt:
```markdown
1. Can you explain in more detail how InputStream and OutputStream work in Java I/O?
2. Provide a more detailed example of how FileInputStream could be used to read customer account data in a banking application in Java Programming Language.
```

### Java I/O Reader and Writer
- Reader and Writer are the base classes for reading from and writing to character streams
- Reader has methods like `read()` to read characters from a source, while Writer has `write()` to write characters to a destination
- There are many subclasses of these, like FileReader, FileWriter, for reading and writing files.
- Subclasses like FIleReader and FileWrite allow reading from and writing to files in a character-oriented manner.

ChatGPT Prompt:
```markdown
1. Could you explain more about how the Reader and Writer classes work in Java?
2. Provide a more detailed example of reading a bank statement text file using FileReader in Java Programming Language.
```

### Files and Directories in Java
- Java provides the File class in java.io package to work with files and directories
- The File class provides methods to create, delete, rename, and manipulate files and directories
- It can be used to check file properties, such as file size, file type, and last modified date
- It has methods like `createNewFile()`, `delete()`, `renameTo()`, `exists()`, `canRead()`, `canWrite()`, `getName()`, `length()`, etc.

ChatGPT Prompt:
```markdown
1. How do methods like exists(), canRead(), canWrite(), and getName() work in the File class in Java?
2. Provide a more detailed example of how a banking application could use the File class to manage customer account data in Java Programming Language.
```

### Java Paths and File System
- Java also has a Path interface in java.nio.file package to represent the path of a file or directory. Paths are more modern and have better methods for working with files and directories
- You can use Paths to get an instance of a Path, which can be used with many methods in the Files class for file operations
- The Files class provides methods for file operations like copy, move, delete, read, and write files

ChatGPT Prompt:
```markdown
1. Can you explain the differences between File and Path in Java?
2. Provide a more detailed example of how a banking application could use the Path interface and Files class to manage customer account data in Java Programming Language.
```

---