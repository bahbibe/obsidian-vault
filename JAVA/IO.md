
### Java I/O System Overview

1. **Main Classes**:
    - **Byte Streams**: Handle raw binary data. Key classes include:
        - `InputStream` (e.g., `FileInputStream`, `ByteArrayInputStream`)
        - `OutputStream` (e.g., `FileOutputStream`, `ByteArrayOutputStream`)
    - **Character Streams**: Handle human-readable text data. Key classes include:
        - `Reader` (e.g., `FileReader`, `BufferedReader`)
        - `Writer` (e.g., `FileWriter`, `BufferedWriter`)
    - **Utility Classes**: Such as `PrintWriter` and `DataInputStream` for formatted output and reading primitive data types.
    - **File Management**: The `File` class for file and directory operations.
    - **summary of main classes

|Category|Class Name|Description|
|---|---|---|
|**InputStream**|`InputStream`|Abstract class for reading byte data.|
||`FileInputStream`|Reads bytes from a file.|
||`ByteArrayInputStream`|Reads bytes from a byte array.|
||`ObjectInputStream`|Deserializes objects from an input stream.|
|**OutputStream**|`OutputStream`|Abstract class for writing byte data.|
||`FileOutputStream`|Writes bytes to a file.|
||`ByteArrayOutputStream`|Writes bytes to a byte array (in memory).|
||`ObjectOutputStream`|Serializes objects to an output stream.|
|**Reader**|`Reader`|Abstract class for reading character data.|
||`FileReader`|Reads characters from a file.|
||`BufferedReader`|Buffers characters for efficient reading.|
||`InputStreamReader`|Bridges byte streams to character streams.|
|**Writer**|`Writer`|Abstract class for writing character data.|
||`FileWriter`|Writes characters to a file.|
||`BufferedWriter`|Buffers characters for efficient writing.|
||`PrintWriter`|Provides formatted text output.|
|**Utility**|`PrintStream`|Similar to `PrintWriter`, but for output streams.|
||`DataInputStream`|Reads primitive data types from an input stream.|
||`DataOutputStream`|Writes primitive data types to an output stream.|
|**File Management**|`File`|Represents file and directory pathnames.|
    
1. **Scanner Class (not a IO class)**:
    - Part of the `java.util` package, `Scanner` is used for parsing and tokenizing input, allowing easy reading of text from various sources (e.g., console, files). It simplifies input handling but is not a stream class.
    
1. **Byte Data vs. Character Data**:
    - **Byte Data**:
        - Raw binary data, represented using the `byte` type.
        - Handled with byte stream classes (e.g., `InputStream`, `OutputStream`).
        - Used for binary files (like images and audio).
    - **Character Data**:
        - Textual data, represented using the `char` type.
        - Handled with character stream classes (e.g., `Reader`, `Writer`).
        - Used for text files (like plain text, XML).
	- **Key Differences**

|Feature|Byte Data|Character Data|
|---|---|---|
|**Data Type**|Raw binary data (bytes)|Textual data (characters)|
|**Java Representation**|`byte` type|`char` type|
|**I/O Classes**|`InputStream` / `OutputStream`|`Reader` / `Writer`|
|**Encoding**|No encoding (raw bytes)|Encoded using character encoding (e.g., UTF-8)|
|**Use Cases**|Binary files (images, audio, etc.)|Text files (plain text, XML, JSON, etc.)|
|**Human Readability**|Not human-readable|Human-readable|

