<h3 align="center"><strong>Heyy, you found me!😃</strong></h3>

So welcome! Currently studying software engineering at [Hive Helsinki](https://www.hive.fi/en/), but on my free time, you probably find me coding (usually in C) or building something out of electronics.

Some notable projects:
<img align="right" width="450" height="450" src="https://github.com/PrinssiFiestas/PrinssiFiestas/blob/main/candy.gif">
- [libGPC](https://github.com/PrinssiFiestas/libGPC): General purpose C library with polymorphic allocators that can be encapsulated to dynamic data structures like UTF8 strings and stuff
- [minirt](https://github.com/susikohmelo/minirt): Real-time interactive ray tracer
- [DSP](https://github.com/PrinssiFiestas/DSP): Audio processing filters
- [Shaders](https://www.shadertoy.com/user/LorenzoFiestas): including the gifs you see here
<img src="https://github.com/PrinssiFiestas/PrinssiFiestas/blob/main/lines.gif"/>

Sometimes, I get sucked into rabbit holes and end up doing weird things for fun. For example, here's C callable `factorial()` written by hand in raw x86-64 Linux machine code:
```c
__attribute__((section(".text")))
static const uint8_t factorial_code[] = {
    // factorial:
    [ 0x00 ] = 0x48, 0x83, 0xFF, 0x00,                   // cmp  rdi, 0
    [ 0x04 ] = 0x74, 0x0F,                               // je .base_case
    [ 0x06 ] = 0x57,                                     // push rdi
    [ 0x07 ] = 0x48, 0xFF, 0xCF,                         // dec  rdi
    [ 0x0A ] = 0xE8, 0xF1, 0xFF, 0xFF, 0xFF,             // call fact
    [ 0x0F ] = 0x5F,                                     // pop  rdi
    [ 0x10 ] = 0x48, 0x0F, 0xAF, 0xC7,                   // imul rax, rdi
    [ 0x14 ] = 0xC3,                                     // ret
    // .base_case:
    [ 0x15 ] = 0x48, 0xC7, 0xC0, 0x01, 0x00, 0x00, 0x00, // mov  rax, 1
    [ 0x1C ] = 0xC3                                      // ret
};
uint64_t(*const factorial)(uint64_t) = (uint64_t(*)(uint64_t))factorial_code;
```
>[!NOTE]
>You are better off just using an assembler. 🙃<br/><br/>

I'm avaliable for work! 🔨 Feel free to contact me via [email](mailto:lorenzo.fiestas@lorenzofiestas.dev) or [LinkedIn](https://fi.linkedin.com/in/lauri-lorenzo-fiestas-74719432b).

<img src="https://github.com/PrinssiFiestas/PrinssiFiestas/blob/main/redblue.jpg"/> 
<sup> Ray tracing! <sup/>
