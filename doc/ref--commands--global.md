[&#8592; `def`](ref--commands--def.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[&#8593; commands](ref--commands.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[&#8594; `return`](ref--commands--return.md)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<small>[\* xdoc](../xdoc/ref.xmd#L53)</small>
***

# `global`
<small>*Command*</small>  
**Synopsis**

```cpp
#global[by <key>]
...
#endglobal

```


Allows to embed definitions anywhere in the code, they will be moved to the root level directly before.
It will create an unnamed group on the inside. The group will also be active after `#endglobal`.

If `key` and the contents are repeated, the repetitions are merged


