[&#8592; `return`](ref--commands--return.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[&#8593; commands](ref--commands.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[&#8594; Name Lookup](ref--commands--name-lookup.md)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<small>[\* xdoc](../xdoc/ref.xmd#L70)</small>
***

# `import`
<small>*Command*</small>  
**Synopsis**

```cpp
#import <filename or module>[{<arguments...>}] [as <group>]

```


Import a file, a JSON like object after the filename to configure arguments.
The file will only be included once.
No macros or other declarations will be visible in the imported file.
If the file accepts arguments, only includes with the same parameters are
merged. If the parameters are not empty





