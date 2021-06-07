# Windows-internals

## PE Header main components and basic structure



| Component name  | Description   |
| --------------- | ------------- |
| MZ Header  | Defines the file as an executable binary  |
| DOS Stub (Program cannot run in DOS mode) | Prints a message when run in DOS (mainly exists for compatibility reasons)  |
| PE File Header (Signature)  | Defines the file as an executable binary  |
| Image Optional Header  | Stores important information about the executable |  
| Sections Table | Instructions on how to load the executable into memory |
| Sections | Executable sections of code and data used by the executable |
