# Grpc

## Protocol buffer

- [Protocol Buffers  |  Google Developers](https://developers.google.com/protocol-buffers/)
- [JavaScript Generated Code  |  Protocol Buffers  |  Google Developers](https://developers.google.com/protocol-buffers/docs/reference/javascript-generated)

## Dynamic vs Static generated file differences

[node.js - What is the difference between dynamically and statically generated grpc code? - Stack Overflow](https://stackoverflow.com/questions/43216248/what-is-the-difference-between-dynamically-and-statically-generated-grpc-code?rq=1)

- The dynamic code generation : simpler to use, potentially easier to debug, and generates code that accepts regular JavaScript objects.
- The static code generation : (using protoc) requires the user to create protobuf objects, which means that input validation will be done earlier. 
	- It is also a workflow that is more consistent with other languages.