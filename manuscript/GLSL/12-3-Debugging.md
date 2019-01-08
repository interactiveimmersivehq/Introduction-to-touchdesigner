
## *12.3 Debugging*

Before getting too deep into the world of GLSL, it is important to know how to debug compiling issues. There are two signs that denote a compiling error.

The first is a blue and red checker pattern. When working with the GLSL MAT, this check pattern will be on the geometry itself. When using GLSL with TOPs, this checker pattern will fill up the Operator's viewer and be output from the TOP.

The second sign of a compile error is a yellow triangle warning flag on the Operator. Upon clicking and holding the left mouse button on the flag, the error will read:

    Warning: The GLSL Shader has compile error

To diagnose these issues, an Info DAT is required. Create an Info DAT, and set the 'Operator' Parameter to reference the GLSL operator with the error. In the Info DAT, if there are no errors, there will be only a few lines and of them will read 'Compiled Successfully' or 'Linked Successfully'. If there are errors however, they will read more like:

    Pixel Shader Compile Results:
    0(3) : error C0000: syntax error, unexpected '=', expecting '::' at token '='

To quickly break this down, the first thing is the line number. In this case, '0(3)' means the compiler is encountering errors at line 3. In many situations, this may mean that the actual mistake happens a line or two earlier, but the compiler doesn't halt until the next line when things stop making sense for it.

The next section highlights that this is a syntax error, and then there is more information about the error.

For beginners, the majority of these errors will be because of forgotten semi-colons at the end of lines, or errors trying to cast one data type into another incompatible data type.

{pagebreak}