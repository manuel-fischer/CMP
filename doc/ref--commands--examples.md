[&#8592; Name Lookup](ref--commands--name-lookup.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[&#8593; commands](ref--commands.md)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;||&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<small>[\* xdoc](../xdoc/ref.xmd#L87)</small>
***

# Examples
<small>*Topic*</small>  

# Parametric inclusion
**`debug.hm`**
```
#def ASSERT(cond)
    #if DEBUG
        if(cond)
        {
            printf("Assertion error: %s\n", #"cond");
        }            
    #endif
#enddef
```

**`test.cm`**
```
#import "debug.hm" { DEBUG = true } as DEBUG::
#import "debug.hm" { DEBUG = false } as NODEBUG::
// alternatively
#use DEBUG:: = #import "debug.hm" { DEBUG = true }

int main()
{
    DEBUG::ASSERT(false); // prints error
    NODEBUG::ASSERT(false); // does nothing
}
```


# Template Types
```
#def VEC3<type TYPE>
    #globalby TYPE
        typedef struct {
            TYPE x, y, z;
        } vec3;
    #endglobal
    #return array
#enddef

int main()
{
    VEC3<int> pos1 = { 1, 2, 3 };
    VEC3<int> pos2 = pos1; // same type, because of globalby
}

```

# Include
```
#include <stdio.h> as IO::
#include <stddef.h> as DEF$
#include <stdlib.h> as LIB.

int main()
{
    IO::FILE* file = IO::NULL;
    if(file == DEF$NULL)
        IO::printf("file is NULL\n");

    return LIB.EXIT_SUCCESS;
}
```

# Modules
**`algo.hm`**
```
#param MALLOC
#param FREE = void #(void* p) {}

void do_sth()
{
    void* buf = MALLOC(100);
    if(!buf) return;
    // ...
    FREE(buf);
}
```

**`main.hm`**
```
#include <stdlib.h> as STD::
#include <stdio.h> as STD:: // ok: merged with previous
#def algo = "algo.hm" {
    MALLOC = STD::malloc,
    FREE = STD::free
}

#import algo as normal_algo::

void* noisy_malloc(STD::size_t size)
{
    STD::printf("allocating %zu bytes", size);
    return STD::malloc(size);
}


#import algo { MALLOC = noisy_malloc } as noisy_algo::

int main()
{
    STD::printf("normal");
    normal_algo::do_sth();

    STD::printf("noisy");
    noisy_algo::do_sth();
}
```

Note that here multiple `{}` are written after each other.
Those get merged like strings, when they appear after each other.

