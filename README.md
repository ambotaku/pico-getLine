# pico-getLine
The Raspberry Pi Pico SDK doesn't offer a stdio getline function. 
This one allows entering lines of any length via USB or UART terminals, since its linebuffer is growing automatically.

It needs C++ a C++ compiler but is using the C standard libraries for memory and string handling to be more compatible to C programs and small memory footprint (e.g. by avoiding STL classes).

The function getLine has following prototype:

```
char * getLine(bool fullDuplex=false, char lineBreak='\n') 
```

set **fullDuplex** to **true** to evoid echoing each entered character (as needed for most terminals)
set **lineBreak** for another line end character than LF, e.g. CR ('\r') for most terminals

Of course you can also read multiple lines by using another end character, eg. to get a complete configuration or source file in one pass. The limit is just the available heap.

