# wyre
Low-impact tool for transferring files and program execution for forensic purposes. It excuslively uses statically-linked libraries to provide a single-executable client that requires no external dependencies. 

## Usage
Run wyre-server on the workstation you wish to receive the output on. Output is saved to the current directory, so copying wyre-server to an empty folder is recommended. Once you have started the server, you'll need to get the client onto your target system. You can do this via ISO/CD-R, shared network folder, USB stick, etc. wyre does not create any temporary files - nor does it have any external dependencies or require any DLL files.

### Starting wyre-server

To start wyre-server, open a Command Prompt and run ```wyre-server localhost[:port]```, where port is an optional specified port number. wyre-server will then listen for a connection and save its output to the current directory.

### Using the client
From your target system, open a command prompt and change to the directory where wyre is located. wyre can be used to run commands and send output to the server, or it can be used to send a binary file to the server. To run a command and send its output to the server: ```wyre <server>[:port] run <command to execute>```. To transmit a file: ``wyre <server>[:port] push <filename>

## Compiling from Source
wyre has been written to allow compatibility with Windows XP. As such, one must install the optional Visual Studio feature for "Windows XP support for C++". If this dependency is not met, Visual Studio will complain about missing build dependencies.

Google's protobuf must also be installed. Instructions for installing protobuf can be found at https://github.com/google/protobuf/blob/master/src/README.md. It is important to note that installing the protobuf libraries necessatate installing Microsoft's experimental vcpkg tool (https://github.com/Microsoft/vcpkg).
