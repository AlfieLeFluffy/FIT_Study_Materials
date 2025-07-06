A **file** is a basic organizational unit for **storing data** on external [[Memory]] devices.
## Types of Files
- **Normal File (-)**
- **Directory (d)** contains a double of **filename** and **file number**, which is usually a [[File Systems#I-node|I-node]]. A directory always points at links to itself and to its parent. They are implemented as their [[File Systems#B+ Trees|B+ Trees]] or [[Searching|Hash Tables]]. 
- **Special Block (b)** 
- **Special Sign/Character (c)**
- **Symbolic/Symlink (l)** contains a **filename** of file to which this file is point to. Each time this file is open the path to the original file has to resolved. The information about this file is usually kept in the i-node.  
- **Pipe (p)** allows communication between processes that have to descriptors (writing and reading). In the terminal they are created through **|** when chaining program calls. They are implemented through a circular buffer with a limited capacity. We can divide them into named and unnamed pipes.
- **Socket (s)** allow for network or local communication between processes. They are named and saved in the file system. Communication can be blocking and or not.
- **Terminal** are physical or virtual interfaces that allow primarily text based output, editing on the output line and special characters. In UNIX they are represented through files such as `/dev/tty`, `/dev/tty1`, etc. They have multiple way of working with characters such as raw, cbreak, cooked, etc. 