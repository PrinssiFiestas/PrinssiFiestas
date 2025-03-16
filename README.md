<h3 align="center"><strong>Heyy, you found me!😃</strong></h3>

So welcome. Currently studying software engineering at [Hive Helsinki](https://www.hive.fi/en/), but on my free time, you probably find me coding (usually in C) or building something out of electronics.

Some of my notable projects:

- [libGPC](https://github.com/PrinssiFiestas/libGPC): General purpose C library with polymorphic allocators that can be encapsulated to dynamic data structures like UTF8 strings and stuff
- [minirt](https://github.com/susikohmelo/minirt): Real-time interactive ray tracer
- [DSP](https://github.com/PrinssiFiestas/DSP): Audio processing filters
- [Shaders!](https://www.shadertoy.com/profile/LorenzoFiestas)

Sometimes, I do weird things like writing x86_64 machine code by hand. It's a complete waste of time (just use an assembler or C!🙃), but that's fine. Just for fun and games, here's C callable `factorial()`: (Linux only)
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
    [ 0x1C ] = 0xC3, 0x90, 0x90, 0x90,                   // ret
};
uint64_t(*const factorial)(uint64_t) = (uint64_t(*)(uint64_t))factorial_code;
```

<!--
**PrinssiFiestas/PrinssiFiestas** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
