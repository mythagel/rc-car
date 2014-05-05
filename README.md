rc-car
======

need to design declcam to actually process these files
also need to fix up cxxcam to do feeds and speeds.

declcam

```
#!/bin/sh
jscam declcam.js $@
```

main job is translation - process input document into gcode + models + images (blueprints)

decl document converted to
 - for each part
   - gcode of each operation
   - model of part

Implemented in two parts

1. Part compiler
    - Takes part definition and compiles part to gcode, model, etc.
    - Can be run standalone on a part def
    - REFACTOR - scrap nested machine defs - part must reference machine, tool-table, stock, & material defs.
    - Machine, material, tools, etc. identified by name.
2. Project part manager
    - Input is project file
    - loops over each part and executes part compiler
    - Manages which machine def will be used for each part.


Notes from code moved here.
    Referring to machine and tool references in part defs:
    // May be reference to object by string ID, or (if object) an inline decl.

    Referring to operations on stock within a single part:
    /* Each operation modifies the stock of the last operation.*/

    Referring to path to cut in profile operation:
    // ref path node in external SVG file....
