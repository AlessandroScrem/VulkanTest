## Vulkan Tutorial

### Compiling GLSL to SPIR-V

1. Add the shaders to your project.
2. In the property page of each shader file set Item Type to Custom Build Tool
3. In the newly appeared Custom Build Tool tree set for each shader file:

   1. Set Command Line to $(VULKAN_SDK)\Bin32\glslangValidator -V -o $(OutDir)\%(Identity).spv %(Identity) (for x32, otherwise Bin for x64 host)
   2. Set Description to something nice, e.g. Compiling vertex shader
   3. Set Outputs to e.g. $(OutDir)\%(Identity).spv
   4. Set Link Objects to No

[Stack Overflow ref:](https://stackoverflow.com/questions/39072485/compiling-glsl-to-spir-v-using-premake-5-and-visual-studio-2015)