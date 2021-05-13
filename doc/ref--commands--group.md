[&#8592; `define`](ref--commands--define.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[&#8593; commands](ref--commands.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[&#8594; `use`](ref--commands--use.md)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<small>[\* xdoc](../xdoc/ref.xmd#L16)</small>
***

# `group`
<small>*Command*</small>  
**Synopsis**

```cpp
#group <grp>
...
#endgroup
```
```cpp
#usegroup <grp>
...
#endgroup
```
```cpp
#nogroup
...
#endgroup
```


Begins a namespace/group, all declared identifiers start with `grp`. It also activates
the group on the inside.
Note that `grp` can be empty, then it works as scope barriers. No definition will escape
the scope. Under the hood, a unique group name is generated, this is called an unnamed group.

`#usegroup` will also activate the group in the parent group.

`#nogroup` will generate the introduced names as they appear without any prefix.

Note that nested groups are possible, the names are created from the outside to the inside.


