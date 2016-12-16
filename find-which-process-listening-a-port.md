# On Mac OSX

## `lsof` - List Open Files

Simple way:

`lsof -i :8080 -P`

Only listen type:

`lsof -P -i4TCP:8080 -sTCP:LISTEN`
