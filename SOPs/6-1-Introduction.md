# 6 SOPs
### *6.1 Introduction*

The Surface Operators, or SOPs, family of Operators are used for any and all 3D operations. This includes working with simple 3D geometry, particle systems, architectural models, 3D characters, and more. SOPs are the oft ignored operators by many beginners because of their steep learning curve, but rest assured that a firm knowledge over the SOP family of operators will open up many incredibly interesting opportunities, project-wise, as well as offer many extremely efficient ways of solving problems.

Many projects involving projection mapping, real-time 3D motion capture, architectural LED facade installations, and layered video players, would either be impossible or extremely difficult without the SOP family of operators.

TouchDesigner 088 currently supports the following 3D file types:

* .fbx

* .obj

* .3ds

* .dxf

* .dae


Keeping Operators from cooking needlessly is essential to smooth performance, which will be discussed further in the 'Optimization' section of the book. This is even more important when it comes to SOPs. Always try to apply transform animation data to a Geometry COMP instead directly of to a SOP. This is because SOP transformations happen on the CPU, and the transformation must be performed for every vertex that is present in the geometry. Component level transformations are applied to the 3D geometry, or object, as a whole, and are performed on the GPU as a single operation. A single operation performed on the GPU is much preferred when compared to what could amount hundreds or thousands of operations performed on the CPU. 

The number of total points, primitives, vertices, and meshes will vary depending on what kind of model is being processed, but the basic principle is that the more polygons/vertices in a model, the more processing power and GPU RAM are needed to process operations. There are tools inside of TouchDesigner to reduce polygon counts in complex models, but optimizing geometry in dedicated modelling suites can provide more flexibility.