# Signed Distance Functions in Unreal Editor
A library providing Signed Distance Functions you can use with your custom raymarcher in Unreal Engine's Material Editor's custom nodes. 

## How to use:
To use with Unreal Engine, place this file in [UE_4.24]\Engine\Shaders\Private\, then #include it in Common.ush (Common.ush is located in that same folder).

First time you do this you'll trigger Unreal shaders recompilation (it'll take a little while to start up the editor).
You can then use any function described here in your Material Editor's Custom Nodes.

You will probably need to write your own ray marcher for that. This blog post is a good starting point for that: https://sainarayan.me/2017/12/16/raymarching-using-signed-distance-fields-in-ue4/
It also features a plethora of links if you want to delve deeper in the subject.

Here's a quick demo of this library at work: https://www.instagram.com/tv/B_tRy7BhgJT/

### Worthy Notes
* All Signed Distance Functions are prefixed with "SDF"
* Generalized Distance Functions are prefixed with "GDF"
* All operators are prefixed with either "op" or "p"
  * operators prefixes with "p" change the value of their input (p is an inout parameter, treated as a reference)
* Code includes a set of helpers functions, in particular GLmod(x, y) it's a MOD operator working as MOD works in GLSL (https://stackoverflow.com/questions/7610631/glsl-mod-vs-hlsl-fmod)

## Feel free to contribute!
This has mostly been translating Inigo Quilez and Mercury work on SDFs from openGL to HLSL. There are still many functions and operators yet to be integrated within the library, as well as new ideas as they come by. Please feel free to contribute!
