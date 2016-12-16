# On Mac OSX

## `lsof` - list open files

Simple way:

`lsof -i :8080 -P`

Only listen type:

`lsof -P -i4TCP:8080 -sTCP:LISTEN`


On Mac, `netstat` doesn't support -p option.

# On Linux

`netstat -anp tcp | grep 8080`

Likewise, we can use above `lsof`.
