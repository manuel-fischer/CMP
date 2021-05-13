[&#8592; `global`](ref--commands--global.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[&#8593; commands](ref--commands.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[&#8594; `import`](ref--commands--import.md)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<small>[\* xdoc](../xdoc/ref.xmd#L63)</small>
***

# `return`
<small>*Command*</small>  
**Synopsis**

```cpp
#return ...

```


In a macro replacement, this will let the rest of the macro expand before the enclosing statement.
The expression after `#return` is embedded where the macro call was. Names are looked up before
embedded into the target code.


