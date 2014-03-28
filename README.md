rc-car
======

need to design declcam to actually process these files
also need to fix up cxxcam to do feeds and speeds.

declcam
{{{
#!/bin/sh
jscam declcam.js $@
}}}

main job is translation - process input document into gcode + models + images (blueprints)

decl document converted to
 - for each part
   - gcode of each operation
   - model of part


