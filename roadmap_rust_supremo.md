# 🦀 ROADMAP RUST — Edição Suprema

> **Pré-requisito recomendado:** Conhecimento parcial de C++ é bem-vindo, mas **não obrigatório**. A sintaxe de Rust é intencionalmente similar à de C++ (chaves `{}`, ponto e vírgula, `if`/`else`, `for`, `while`, `struct`, etc.), o que facilita a transição para quem já tem base em C++. Se você nunca viu C++, aprenda Rust do zero sem medo — a curva existe mas é perfeitamente transponível. O próprio [Comprehensive Rust](https://google.github.io/comprehensive-rust/) (curso oficial do Google Android) faz comparações diretas com C++ para explicar conceitos.

**20 Trilhas │ 4 Níveis │ 25 Recursos │ 5687–10985h de conteúdo**

> ⚠️ **Documento vivo:** Este roadmap é continuamente atualizado. Tópicos malucos podem ser adicionados a qualquer momento conforme novas áreas de interesse surgem (engenharia reversa, parsing binário, Mojo, etc.). A versão atual é sempre a mais recente — não usamos controle de versão no nome do arquivo.

---

## 📖 Por que C++ ajuda (mas não é obrigatório)

Rust foi projetado por sistemas programmers que vinham de C e C++. A familiaridade inclui:

| Conceito | C++ | Rust |
|----------|-----|------|
| Funções | `int foo(int x)` | `fn foo(x: i32) -> i32` |
| Structs | `struct Foo { int x; };` | `struct Foo { x: i32 }` |
| Enums | `enum Color { Red, Green };` | `enum Color { Red, Green }` |
| Templates | `template<typename T>` | `fn foo<T: Trait>(x: T)` |
| Ponteiros | `int* p`, `&ref` | `*const T`, `&T`, `&mut T` |
| Iteradores | `for (auto& x : vec)` | `for x in &vec` |

**O que Rust adiciona de diferente:** ownership, borrow checker, pattern matching exaustivo, `Option<T>` em vez de `nullptr`, `Result<T,E>` em vez de exceções, e zero-cost abstractions com traits.

> ⚠️ **Atenção:** Saber C++ pode criar vícios perigosos. Em C++ você gerencia memória manualmente ou com smart pointers; em Rust o compilador **obriga** você a pensar em ownership desde o dia 1. Não pule o capítulo 4 do The Book (Ownership) achando que já sabe — é um paradigma diferente.

---

## 🎯 NORTE PARA OS MALUCOS — O que o mercado SÊNIOR/STAFF exige

> *"Rust é para a vida toda"* — mas que tipo de vida? Se você quer mirar em vagas como a **PANIK (R$ 36k/mês + bônus, PJ, 100% remoto)**, aqui está o que o mercado real exige de um Engenheiro de Sistemas Sênior/Staff em Rust:

### 🔹 Rust Avançado (requisito central)
Ownership, borrowing, lifetimes, traits, generics, slices, byte buffers, memory layout, zero-copy, error modeling, concorrência, multithreading, synchronization, FFI, **unsafe Rust quando justificável**, profiling, programação orientada a performance.

### 🔹 Análise Binária & Engenharia Reversa
Headers, magic values, versions, flags, endianness, offsets relativos/absolutos, alignment/padding, chunks/sections, string/object tables, índices, bitfields, checksums, payloads comprimidos, metadata. A pergunta não é *"como leio esses bytes?"* mas *"o que esses bytes representam, qual é a regra estrutural e como provamos isso?"*

### 🔹 Segurança de Parsers
Toda entrada é potencialmente hostil. Arquivos truncados, offsets inválidos, integer overflow, decompression bombs, recursão maliciosa. Entrada inválida → erro controlado. **Nunca panic, OOM, loop infinito ou corrupção silenciosa.**

### 🔹 Fuzzing
Coverage-guided fuzzing, mutation fuzzing, corpus generation, crash minimization, property-based testing, malformed input testing.

### 🔹 Tecnologia 3D
Geometria (vertices, indices, topology, normals, tangents, UVs), skeletons (bones, hierarquia, bind pose, skinning), animação (clips, keyframes, quaternions, interpolação), materiais (PBR, roughness, metallic, mipmaps). Matemática 3D: vetores, matrizes, quaternions, transforms, bounding volumes.

### 🔹 Tooling / Low Level
Linux, GDB/LLDB, perf, strace, objdump, readelf, xxd/hexdump. **Diferenciais enormes:** Ghidra, Binary Ninja, IDA, ImHex, Kaitai Struct, disassemblers, instrumentação dinâmica.

### 🔥 Mojo — Diferencial de Altíssimo Peso
Conhecimento prático de **Mojo** (Modular) será considerado diferencial enorme — HPC, SIMD, kernels, memory management, workloads numéricos, infraestrutura de alta performance. Ainda não é open-source (previsão 2026), mas quem souber usar pesa bastante na seleção.

### 🔹 Outros Diferenciais
C/C++, SIMD, WebAssembly, GPU computing, compiladores, virtual machines, memory allocators, compression, engines, mesh processing, animation systems.

### ⚠️ Comprovação de Senioridade
Currículo **não basta**. Exigem GitHub/GitLab com projetos próprios, bibliotecas, parsers, engines, compiladores, emuladores, ferramentas de reverse engineering, renderers, profilers, debuggers, memory allocators. O que importa: arquitetura, complexidade dos problemas resolvidos, qualidade do código, testes, performance, segurança, decisões de engenharia.

> 💡 **Resumo para os maluco:** Se você quer R$ 36k/mês em Rust, não basta saber fazer CRUD. Você precisa ser alguém que pega bytes desconhecidos, descobre a estrutura por trás deles, implementa um parser seguro em Rust, cobre com fuzzing, otimiza com profiling e coloca em produção. **Este roadmap te leva até lá — mas o caminho é de 3–5 anos de estudo focado e projetos reais no GitHub.**

---

## 📚 REFERÊNCIAS PARA OS MALUCOS — Do básico ao avançado

### 🔹 Parsing Binário

| Recurso | Nível | Link |
|---------|-------|------|
| **[nom](https://docs.rs/nom/latest/nom/)** — Parser combinators (oficial) | Intermediário | [docs.rs](https://docs.rs/nom/latest/nom/) |
| **[nom recipes](https://github.com/rust-bakery/nom/blob/main/doc/choosing_a_combinator.md)** — Padrões comuns de parsing | Intermediário | [github.com](https://github.com/rust-bakery/nom/blob/main/doc/choosing_a_combinator.md) |
| **[Kaitai Struct](https://kaitai.io/)** — Linguagem declarativa para formatos binários | Intermediário | [kaitai.io](https://kaitai.io/) |
| **[Kaitai Struct Docs](https://doc.kaitai.io/)** — Tutorial e referência | Intermediário | [doc.kaitai.io](https://doc.kaitai.io/) |
| **[Parsing binary data with nom](https://github.com/rust-bakery/nom/tree/main/doc)** — Guia prático | Avançado | [github.com](https://github.com/rust-bakery/nom/tree/main/doc) |

### 🔹 Fuzzing

| Recurso | Nível | Link |
|---------|-------|------|
| **[Rust Fuzz Book](https://rust-fuzz.github.io/book/)** — Guia oficial de fuzzing com cargo-fuzz | Intermediário | [rust-fuzz.github.io](https://rust-fuzz.github.io/book/) |
| **[cargo-fuzz](https://github.com/rust-fuzz/cargo-fuzz)** — CLI para libFuzzer | Intermediário | [github.com](https://github.com/rust-fuzz/cargo-fuzz) |
| **[libFuzzer](http://llvm.org/docs/LibFuzzer.html)** — LLVM fuzzer (base do cargo-fuzz) | Avançado | [llvm.org](http://llvm.org/docs/LibFuzzer.html) |
| **[afl.rs](https://github.com/rust-fuzz/afl.rs)** — Fuzzing com AFL (alternativa) | Avançado | [github.com](https://github.com/rust-fuzz/afl.rs) |
| **[Structure-Aware Fuzzing](https://rust-fuzz.github.io/book/cargo-fuzz/structure-aware-fuzzing.html)** — Fuzzing com conhecimento de estrutura | Avançado | [rust-fuzz.github.io](https://rust-fuzz.github.io/book/cargo-fuzz/structure-aware-fuzzing.html) |

### 🔹 Tecnologia 3D / Geometria

| Recurso | Nível | Link |
|---------|-------|------|
| **[glTF Specification](https://www.khronos.org/gltf/)** — Padrão Khronos Group (JPEG of 3D) | Intermediário | [khronos.org](https://www.khronos.org/gltf/) |
| **[glTF 2.0 Quick Reference](https://www.khronos.org/files/gltf20-reference-guide.pdf)** — Guia visual de bolso | Intermediário | [khronos.org](https://www.khronos.org/files/gltf20-reference-guide.pdf) |
| **[nalgebra](https://docs.rs/nalgebra/latest/nalgebra/)** — Álgebra linear para gráficos e física | Intermediário | [docs.rs](https://docs.rs/nalgebra/latest/nalgebra/) |
| **[glam](https://docs.rs/glam/latest/glam/)** — Álgebra linear rápida para games (alternativa ao nalgebra) | Intermediário | [docs.rs](https://docs.rs/glam/latest/glam/) |
| **[gltf crate](https://docs.rs/gltf/latest/gltf/)** — Parser glTF para Rust | Intermediário | [docs.rs](https://docs.rs/gltf/latest/gltf/) |
| **[Khronos PBR](https://www.khronos.org/gltf/)** — Physically Based Rendering (materiais realistas) | Avançado | [khronos.org](https://www.khronos.org/gltf/) |

### 🔹 Engenharia Reversa / Tooling

| Recurso | Nível | Link |
|---------|-------|------|
| **[Ghidra](https://ghidra-sre.org/)** — Framework de engenharia reversa da NSA | Intermediário | [ghidra-sre.org](https://ghidra-sre.org/) |
| **[Ghidra Getting Started](https://github.com/NationalSecurityAgency/ghidra)** — Instalação e primeiros passos | Intermediário | [github.com](https://github.com/NationalSecurityAgency/ghidra) |
| **[ImHex](https://github.com/WerWolv/ImHex)** — Hex editor com pattern highlighting | Intermediário | [github.com](https://github.com/WerWolv/ImHex) |
| **[Binary Ninja](https://binary.ninja/)** — Disassembler comercial (alternativa ao Ghidra) | Avançado | [binary.ninja](https://binary.ninja/) |
| **[IDA Pro](https://hex-rays.com/ida-pro/)** — Disassembler clássico (pago) | Avançado | [hex-rays.com](https://hex-rays.com/ida-pro/) |
| **[perf](https://man7.org/linux/man-pages/man1/perf.1.html)** — Profiler Linux (hardware counters) | Avançado | [man7.org](https://man7.org/linux/man-pages/man1/perf.1.html) |

### 🔥 Mojo (Diferencial de Altíssimo Peso)

| Recurso | Nível | Link |
|---------|-------|------|
| **[Mojo Manual](https://docs.modular.com/mojo/)** — Documentação oficial da linguagem | Intermediário | [docs.modular.com](https://docs.modular.com/mojo/) |
| **[Mojo Quickstart](https://docs.modular.com/mojo/manual/)** — Instalação e primeiros passos | Iniciante | [docs.modular.com](https://docs.modular.com/mojo/manual/) |
| **[Mojo Standard Library](https://docs.modular.com/mojo/std/)** — Referência completa | Intermediário | [docs.modular.com](https://docs.modular.com/mojo/std/) |
| **[Mojo GPU Programming](https://docs.modular.com/max/)** — Kernels GPU com MAX | Avançado | [docs.modular.com](https://docs.modular.com/max/) |
| **[Mojo Quest](https://quest.mojolang.org/)** — Aprenda Mojo corrigindo bugs no browser | Iniciante | [quest.mojolang.org](https://quest.mojolang.org/) |
| **[Mojo Open Source](https://github.com/modular/modular)** — Repositório GitHub (desde ago/2026) | Avançado | [github.com](https://github.com/modular/modular) |

### 🔹 Rust Avançado (unsafe, FFI, Memory Layout)

| Recurso | Nível | Link |
|---------|-------|------|
| **[The Rustonomicon](https://doc.rust-lang.org/nomicon/)** — Guia oficial de unsafe Rust | Avançado | [doc.rust-lang.org](https://doc.rust-lang.org/nomicon/) |
| **[Rust FFI Omnibus](http://jakegoulding.com/rust-ffi-omnibus/)** — FFI com C/Python/Ruby | Avançado | [jakegoulding.com](http://jakegoulding.com/rust-ffi-omnibus/) |
| **[bindgen](https://docs.rs/bindgen/latest/bindgen/)** — Gera bindings C automaticamente | Avançado | [docs.rs](https://docs.rs/bindgen/latest/bindgen/) |
| **[cxx](https://cxx.rs/)** — FFI C++ seguro | Avançado | [cxx.rs](https://cxx.rs/) |
| **[std::alloc](https://doc.rust-lang.org/std/alloc/)** — Memory allocators customizados | Avançado | [doc.rust-lang.org](https://doc.rust-lang.org/std/alloc/) |

### 🔹 Projetos Open Source para Estudar (GitHub)

| Projeto | Área | Link |
|---------|------|------|
| **[gltf-rs](https://github.com/gltf-rs/gltf)** | Parser 3D | [github.com](https://github.com/gltf-rs/gltf) |
| **[image-rs/image](https://github.com/image-rs/image)** | Parsing de imagens (PNG, JPEG, etc) | [github.com](https://github.com/image-rs/image) |
| **[image-rs/image-png](https://github.com/image-rs/image-png)** | Parser PNG (ótimo para aprender) | [github.com](https://github.com/image-rs/image-png) |
| **[rust-lang/rustlings](https://github.com/rust-lang/rustlings)** | Exercícios fundamentais | [github.com](https://github.com/rust-lang/rustlings) |
| **[rust-bakery/nom](https://github.com/rust-bakery/nom)** | Parser combinators | [github.com](https://github.com/rust-bakery/nom) |
| **[rust-fuzz/cargo-fuzz](https://github.com/rust-fuzz/cargo-fuzz)** | Fuzzing | [github.com](https://github.com/rust-fuzz/cargo-fuzz) |
| **[bevyengine/bevy](https://github.com/bevyengine/bevy)** | Game engine 3D | [github.com](https://github.com/bevyengine/bevy) |
| **[gfx-rs/wgpu](https://github.com/gfx-rs/wgpu)** | GPU abstraction | [github.com](https://github.com/gfx-rs/wgpu) |
| **[ruffle-rs/ruffle](https://github.com/ruffle-rs/ruffle)** | Emulador Flash (parsing binário complexo) | [github.com](https://github.com/ruffle-rs/ruffle) |
| **[iced-rs/iced](https://github.com/iced-rs/iced)** | GUI Rust (bom para ver arquitetura) | [github.com](https://github.com/iced-rs/iced) |

---

## QUANTO TEMPO VAI LEVAR? — Estimativas Completas

Estimativas baseadas em dedicação real com projetos práticos implementados. Estudo sem projeto é 2-3x menos eficiente — implemente sempre o projeto do tópico.

### Resumo por Nível de Dificuldade

| Nível | Tópicos | Mín (h) | Máx (h) | Médio (h) | 2h/dia | 4h/dia |
|-------|---------|---------|---------|-----------|--------|--------|
| 🟢 Iniciante | 20 | 197h | 365h | ~282h | 4 meses, 21 dias | 2 meses, 11 dias |
| 🔵 Intermediário | 40 | 1300h | 2500h | ~1900h | 2 anos, 7 meses | 1 ano, 3 meses |
| 🟠 Avançado | 20 | 1190h | 2120h | ~1655h | 2 anos, 3 meses | 1 ano, 1 mês |
| 🔴 Hardcore | 20 | 3000h | 6000h | ~4500h | 6 anos, 2 meses | 3 anos, 1 mês |
| 📊 **TOTAL** | **100** | **5687h** | **10985h** | **~8337h** | **11 anos, 5 meses** | **5 anos, 8 meses** |

### Tempo Acumulado — Se Você Estudar até o Nível X

| Se você completar até... | Horas acum. | Tópicos | Tempo (2h/dia) | Tempo (4h/dia) |
|--------------------------|-------------|---------|----------------|----------------|
| 🟢 Somente Nível 1 | ~282h | 20 | 4 meses, 21 dias | 2 meses, 11 dias |
| 🔵 Níveis 1 + 2 | ~2182h | 60 | 3 anos | 1 ano, 6 meses |
| 🟠 Níveis 1 + 2 + 3 | ~3837h | 80 | 5 anos, 3 meses | 2 anos, 7 meses |
| 🔴 Todos os 4 Níveis | ~8337h | 100 | 11 anos, 5 meses | 5 anos, 8 meses |

### Cenários de Ritmo de Estudo

| Cenário | Horas/dia | Dias/semana | Total médio | Mínimo | Máximo |
|---------|-----------|-------------|-------------|--------|--------|
| 🏃 Intensivo | 8h | 5x | 2 anos, 10 meses | 1 ano, 11 meses | 3 anos, 9 meses |
| 📚 Dedicado | 4h | 5x | 5 anos, 8 meses | 3 anos, 10 meses | 7 anos, 6 meses |
| ⚖️ Equilibrado | 2h | 5x | 11 anos, 5 meses | 7 anos, 9 meses | 15 anos |
| 🐢 Casual | 4h | 2x | 5 anos, 8 meses | 3 anos, 10 meses | 7 anos, 6 meses |

> 💡 **Como interpretar:** Ninguém faz os 100 tópicos em sequência — escolha UMA trilha. Mesmo 20% do roadmap produz resultados reais de empregabilidade. O Nível 1 já habilita trabalho comercial em Rust em ~2 meses (4h/dia). As estimativas assumem que você IMPLEMENTA os projetos.

---

## 🛤️ 20 TRILHAS DE PROGRESSÃO

| Trilha | ~h | Foco | Sequência | 2h/dia | 4h/dia | 8h/dia |
|--------|-----|------|-----------|--------|--------|--------|
| 🚀 Mercado Rápido (Backend) | 240h | Empregabilidade | #1→#6→#7→#8→#10→#2→#4→#21→#14→#28→#27→#34 | 4 meses | 2 meses | 1 mês |
| 📊 Engenharia de Dados | 280h | Data / Analytics | #1→#3→#9→#30→#52→#57→#78→#81 | 4 meses, 20 dias | 2 meses, 10 dias | 1 mês, 5 dias |
| 🎮 Game Dev (Bevy) | 380h | Games / Gráfica | #1→#9→#41→#43→#42→#65→#56→#77 | 6 meses, 10 dias | 3 meses, 5 dias | 1 mês, 18 dias |
| ⚙️ Sistemas / Baixo Nível | 750h | OS / Kernel | #1→#7→#15→#47→#48→#80→#66→#91→#99→#100 | 1 ano, 15 dias | 6 meses, 8 dias | 3 meses, 4 dias |
| 🔐 Cibersegurança | 500h | Security / Criptografia | #1→#7→#9→#34→#61→#62→#73→#84→#89→#98 | 8 meses, 10 dias | 4 meses, 5 dias | 2 meses, 3 dias |
| 📈 Finanças / HFT | 430h | Quant / Trading | #1→#9→#32→#76→#80→#67→#93→#78 | 7 meses, 5 dias | 3 meses, 18 dias | 1 mês, 24 dias |
| ⛓️ Blockchain | 480h | Web3 / DeFi | #1→#6→#34→#44→#63→#88→#89→#95 | 8 meses | 4 meses | 2 meses |
| 🤖 IA / Machine Learning | 480h | ML / HPC | #1→#3→#61→#62→#57→#94→#77→#85 | 8 meses | 4 meses | 2 meses |
| 🦾 Robótica / ROS2 | 440h | Robótica / IoT | #1→#9→#10→#45→#47→#80→#97 | 7 meses, 10 dias | 3 meses, 20 dias | 1 mês, 25 dias |
| 🔬 Compiladores | 540h | PL / Compiladores | #1→#4→#13→#23→#24→#70→#81→#82→#100 | 9 meses | 4 meses, 15 dias | 2 meses, 8 dias |
| 🛸 Aeroespacial | 580h | Mission Critical | #1→#45→#62→#68→#75→#79→#86 | 9 meses, 20 dias | 4 meses, 25 dias | 2 meses, 13 dias |
| 📱 Mobile Dev | 250h | iOS / Android | #1→#6→#21→#25→#84 | 4 meses, 5 dias | 2 meses, 3 dias | 1 mês, 2 dias |
| 🌐 WebAssembly / Frontend | 280h | WASM / Front | #1→#6→#22→#49→#58→#77 | 4 meses, 20 dias | 2 meses, 10 dias | 1 mês, 5 dias |
| ☁️ Infra / Cloud Native | 480h | K8s / Cloud | #1→#14→#27→#51→#93→#99 | 8 meses | 4 meses | 2 meses |
| 🔗 Sistemas Distribuídos | 650h | Distrib. Systems | #44→#50→#37→#75→#93→#95 | 10 meses, 25 dias | 5 meses, 13 dias | 2 meses, 22 dias |
| 🛠️ DevTools | 330h | Ferramentas / DX | #1→#4→#5→#29→#40→#46→#70→#81 | 5 meses, 15 dias | 2 meses, 23 dias | 1 mês, 12 dias |
| ⚛️ Pesquisa / Quântica | 500h | Acadêmico / HPC | #62→#75→#85→#88→#89→#90 | 8 meses, 10 dias | 4 meses, 5 dias | 2 meses, 3 dias |
| 🎵 Multimedia / Áudio | 380h | Áudio / Vídeo | #21→#43→#54→#72→#87→#96 | 6 meses, 10 dias | 3 meses, 5 dias | 1 mês, 18 dias |
| ⚡ Performance | 400h | HPC / Otimização | #4→#9→#39→#67→#76→#78→#80 | 6 meses, 20 dias | 3 meses, 10 dias | 1 mês, 20 dias |
| 🔌 Interop / FFI | 310h | Interoperabilidade | #20→#25→#54→#60→#84 | 5 meses, 5 dias | 2 meses, 18 dias | 1 mês, 9 dias |

---

## 🔥 TRILHA SÊNIOR / MALUCO — O Caminho dos Gigantes

> *"Se você quer R$ 36k/mês em Rust, não basta saber fazer CRUD. Você precisa ser alguém que pega bytes desconhecidos, descobre a estrutura por trás deles, implementa um parser seguro em Rust, cobre com fuzzing, otimiza com profiling e coloca em produção."*

**Esta trilha não tem estimativa de tempo — tempo não importa, profundidade importa.** Cada etapa pode levar de 6 meses a 2 anos. A sequência de pré-requisitos é o que garante que você construa bases sólidas antes de avançar.

| Etapa | Tópico | Pré-requisitos |
|-------|--------|----------------|
| 1 | **Rust Sólido** — CLI, Testes, Estruturas, Generics, Iteradores, Closures | — |
| 2 | **unsafe + FFI Avançado** — Ponteiros Inteligentes, bindgen, cxx, Rustonomicon | Etapa 1 |
| 3 | **Parsing Binário** — nom, Kaitai Struct, error recovery, formatos desconhecidos | Etapa 1 |
| 4 | **Fuzzing** — cargo-fuzz, AFL, Structure-Aware, corpus generation, crash triage | Etapa 3 |
| 5 | **Engenharia Reversa** — Ghidra, ImHex, Binary Ninja, IDA Pro, disassemblers | Etapa 3 + 4 |
| 6 | **Tooling Low-Level** — perf, strace, objdump, readelf, xxd, instrumentação | Etapa 2 |
| 7 | **Segurança de Parsers** — Validação de input, truncamento, integer overflow, decompression bombs, recursão maliciosa | Etapa 3 + 4 + 5 |
| 8 | **Tecnologia 3D** — glTF, geometria, skeletons, animação, materiais PBR, matemática 3D | Etapa 1 |
| 9 | **Performance & HPC** — Benchmarking, profiling, SIMD, HPC, latência determinista | Etapa 6 |
| 10 | **Compiladores & VMs** — Interpretador, Compiler, LLVM IR, memory allocators | Etapa 3 |
| 11 | **Sistemas & Kernel** — Memory allocator customizado, kernel modules, VMM/hypervisor | Etapa 2 + 9 |
| 12 | **Diferenciais** — Mojo (Manual → GPU Kernels), lock-free, projetos open source no GitHub | Todas as anteriores |

### ⚠️ Comprovação de Senioridade

Currículo **não basta**. Exigem GitHub/GitLab com projetos próprios:
- Bibliotecas Rust publicadas no crates.io
- Parsers seguros com cobertura de fuzzing
- Engines, compiladores, emuladores, renderers
- Ferramentas de reverse engineering
- Profilers, debuggers, memory allocators
- Kernels, VMMs, sistemas embarcados

**O que importa:** arquitetura, complexidade dos problemas resolvidos, qualidade do código, testes, performance, segurança, decisões de engenharia documentadas.

> 💡 **Resumo para os malucos:** Esta trilha te leva de "sei fazer CRUD" para "pego bytes desconhecidos e descubro o que são". O caminho é de 3–5 anos de estudo focado e projetos reais no GitHub. **Não há atalho.**

---

## 🧠 CONCEITOS FUNDAMENTAIS — Transversais a Todos os Níveis

| Conceito | O que precisa dominar | Aparece em |
|----------|----------------------|------------|
| **Ownership & Move** | Cada valor tem um único dono. Ao mover, o original fica inválido. Memória liberada deterministicamente ao sair de escopo — sem GC, sem overhead. Tipos que implementam Copy (i32, bool, f64) são copiados automaticamente. Para String e Vec, use .clone() quando precisar manter o original. | #1 ao #100 |
| **Borrowing & Referências** | &T = leitura compartilhada (N leitores simultâneos). &mut T = escrita exclusiva (1 escritor, sem leitores). O borrow checker garante isso em compile time — zero custo em runtime. A maioria dos erros de iniciante está nessa regra: o compilador está prevenindo data races reais. | #1 ao #100 |
| **Lifetimes 'a'** | Anotações que provam que referências não sobrevivem aos dados que apontam. A maioria é inferida automaticamente pelo compilador (lifetime elision). Explícitas em APIs de biblioteca, structs com referências e closures complexas. Zero overhead em runtime — são verificações de compile time. | A partir #11 |
| **Traits + Generics** | Trait = contrato de comportamento (Display, Iterator, Send, Clone). Generics = código zero-cost para qualquer tipo que implemente o trait. Monomorphization em compile time: o compilador gera código especializado para cada tipo concreto — performance de código manual sem custo de abstração. | A partir #4 |
| **Enums + match** | Enums carregam dados em cada variante: Result<T,E>, Option<T>, enums customizados. match é exaustivo — o compilador exige que todos os casos sejam tratados. if let e while let são açúcar sintático para pattern matching parcial. Adicionar uma variante de enum quebra todos os match que não a cobrem — use isso a favor. | #1 ao #100 |
| **Closures + Iteradores** | Closures capturam por &ref, &mut ou move. Traits Fn, FnMut, FnOnce definem como a closure pode ser chamada. Iteradores são lazy e zero-cost: .map().filter().collect() é otimizado pelo compilador para código equivalente a loops manuais — sem overhead de abstração. | A partir #3 |
| **async/await + Future** | Future = computação que ainda não completou. async fn retorna impl Future automaticamente. .await suspende sem bloquear a thread — o executor (Tokio) pode rodar outras tasks enquanto espera. Modelo cooperative multitasking. Nunca misture tokio e async-std no mesmo projeto. | #14,15,17,22 |
| **Smart Pointers** | Box<T>: aloca no heap. Rc<T>: reference counting single-thread. Arc<T>: reference counting atômico multi-thread. RefCell<T>: mutabilidade interior single-thread (borrow em runtime). Mutex<T>/RwLock<T>: mutabilidade interior multi-thread. Combinação comum: Arc<Mutex<T>> para estado compartilhado async. | A partir #11 |
| **unsafe** | Desbloqueia 5 operações: deref raw pointer, FFI, mutabilidade global, unions, traits unsafe. NÃO desativa o borrow checker — apenas permite operações não verificáveis. Use com precisão cirúrgica: isole em funções pequenas, documente os invariantes que você garante, cubra com testes. | A partir #25 |
| **Macros (decl. e proc.)** | Declarativas (macro_rules!): pattern matching no AST, substituição de texto. Procedurais: recebem TokenStream e retornam TokenStream em compile time. 3 tipos: derive (#[derive(Debug)]), attribute (#[route(GET)]), function-like (sql!('SELECT...')). cargo-expand mostra o código gerado. | A partir #7 |
| **Cargo + Workspace** | Cargo = gerenciador de pacotes + build system + test runner + doc generator + publisher. Cargo.toml declara dependências com versionamento semântico. Cargo.lock garante builds reproduzíveis. Workspace = múltiplos crates no mesmo repo compartilhando dependências e diretório target/. | #1 ao #100 |
| **Traits Avançados** | dyn Trait = dispatch dinâmico via vtable (tipo não precisa ser conhecido em compile time). impl Trait = dispatch estático com monomorphization (zero overhead). Associated types. Default generics. Where clauses para bounds complexos. HRTB: for<'a> fn(&'a T) para closures com lifetimes arbitrários. | A partir #14 |

---

## 🟢 NÍVEL 1 — Iniciante: O Próximo Passo Lógico (#1 ao #20)

Fundamentos práticos que todo projeto Rust usa. Comece pelo #1 e avance sequencialmente. Faixa total: 197–365h (média ~282h).

### #1 — CLI — Linha de Comando ⏱ 10–20h
**O que é:** Ferramentas que recebem subcomandos, flags e argumentos no terminal — como git ou cargo. A forma mais rápida de distribuir valor com Rust: binário único, sem runtime, sem instalador.

**Projeto:** CRUD completo como CLI: add / list / remove / update com --format json|table|csv, barra de progresso animada e confirmação interativa de delete com 'Deseja mesmo apagar? [s/N]'.

**Dica:** Use clap derive (#[command] #[arg]) — muito mais ergonômico que o builder API. Binários Rust são single-file sem runtime — distribua só copiando o executável. clap_complete gera auto-complete para bash/zsh/fish.

**Ferramentas:** clap v4 (derive API), indicatif (progress bars), dialoguer (prompts interativos), console (cores ANSI), rpassword (input de senha sem eco)

### #2 — Banco de Dados SQL Local (SQLite) ⏱ 10–20h
**O que é:** Banco de dados embutido no próprio binário — sem servidor, sem instalação, sem dependência externa. Ideal para CLI tools, apps desktop e protótipos.

**Projeto:** Agenda de contatos com busca full-text (FTS5), migrações versionadas, exportação CSV/JSON e backup automático.

**Dica:** Use sqlx com verify-on-build — queries são checadas em compile time contra o banco. Nunca concatene SQL manualmente — use query!() ou query_as!().

**Ferramentas:** sqlx (async + compile-time checks), rusqlite (síncrono, mais simples), sea-orm (ORM completo)

### #3 — Testes Unitários e de Integração ⏱ 10–20h
**O que é:** Testes automatizados que garantem que seu código funciona e continua funcionando após mudanças. Rust tem suporte nativo a testes unitários (#[test]) e de integração (tests/).

**Projeto:** Biblioteca de validação de CPF/CNPJ com 100% de cobertura de testes, incluindo edge cases e propriedades (property-based testing).

**Dica:** Use cargo-tarpaulin ou cargo-llvm-cov para cobertura. Property testing com proptest encontra edge cases que você não imaginaria.

**Ferramentas:** cargo test (nativo), proptest (property-based), mockall (mocking), cargo-tarpaulin (cobertura)

### #4 — Estruturas de Dados e Generics ⏱ 10–20h
**O que é:** Implementar Vec, HashMap, LinkedList e BinaryHeap do zero para entender como funcionam por baixo. Generics permitem código reutilizável com qualquer tipo.

**Projeto:** Implementação de Vec<T> do zero (com alloc, grow, push, pop, drop) e um HashMap simples com chaining.

**Dica:** Entenda monomorphization — o compilador gera código especializado para cada tipo concreto. Zero overhead em runtime.

**Ferramentas:** std::collections (referência), criterion (benchmarks)

### #5 — Tratamento de Erros ⏱ 10–20h
**O que é:** Rust não tem exceções — usa Result<T,E> e Option<T> para erros explícitos. O operador ? propaga erros automaticamente.

**Projeto:** Parser de CSV com erros customizados, recovery de erros parciais e mensagens amigáveis.

**Dica:** Use thiserror para erros de biblioteca, anyhow para erros de application. Nunca use .unwrap() em código de produção.

**Ferramentas:** thiserror, anyhow, eyre

### #6 — Web API REST (Axum) ⏱ 15–25h
**O que é:** Criar servidores HTTP que recebem requisições JSON e retornam respostas. Axum é o framework mais ergonômico para Rust.

**Projeto:** API de tarefas (TODO) com autenticação JWT, documentação OpenAPI automática e testes de integração.

**Dica:** Use tower-http para middleware (CORS, tracing, compression). Axum integra nativamente com tokio e tower.

**Ferramentas:** axum, tokio, tower-http, serde, utoipa (OpenAPI)

### #7 — Ponteiros Inteligentes e FFI ⏱ 15–25h
**O que é:** Box, Rc, Arc, RefCell e Mutex — como alocar no heap, compartilhar entre threads e interagir com C.

**Projeto:** Bindings para uma biblioteca C (ex: zlib) com wrapper seguro em Rust.

**Dica:** Entenda quando usar cada smart pointer. Arc<Mutex<T>> é o padrão para estado compartilhado entre threads.

**Ferramentas:** std::ffi, bindgen (gera bindings C automaticamente), cxx (FFI C++ seguro)

### #8 — Logging e Observabilidade ⏱ 10–20h
**O que é:** Registrar eventos do sistema para debugging e monitoramento. Rust tem o crate tracing que é o padrão da indústria.

**Projeto:** CLI com logs estruturados (JSON), níveis configuráveis e spans para tracing distribuído.

**Dica:** Use tracing em vez de log — é mais poderoso e integra com OpenTelemetry.

**Ferramentas:** tracing, tracing-subscriber, opentelemetry

### #9 — Iteradores e Closures Avançados ⏱ 10–20h
**O que é:** Iteradores são lazy e zero-cost. Combinators como map, filter, fold, scan, flatten permitem pipelines de dados expressivos.

**Projeto:** Pipeline de processamento de CSV com iterators — filter, map, collect sem alocações intermediárias.

**Dica:** Entenda Fn, FnMut, FnOnce — cada um permite diferentes formas de captura de variáveis.

**Ferramentas:** itertools (combinators extras), std::iter

### #10 — Concorrência com Threads ⏱ 15–25h
**O que é:** Paralelismo real com threads nativas. Rust previne data races em compile time via Send e Sync traits.

**Projeto:** Web crawler paralelo com pool de workers, rate limiting e deduplicação de URLs.

**Dica:** Use rayon para paralelismo de dados — .par_iter() converte automaticamente.

**Ferramentas:** std::thread, rayon, crossbeam, parking_lot

---

## 🔵 NÍVEL 2 — Intermediário: Novos Paradigmas (#21 ao #60)

Aqui você começa a construir sistemas completos. Cada tópico expande o Nível 1 com um novo paradigma. Faixa total: 1300–2500h (média ~1900h).

### #21 — Serde e Serialização ⏱ 15–25h
**O que é:** Serializar/deserializar structs para JSON, YAML, TOML, MessagePack, etc. Serde é o framework padrão.

**Projeto:** Config parser que lê TOML, JSON e YAML com fallback, validação e defaults.

**Dica:** Use #[derive(Serialize, Deserialize)] — macros geram código automaticamente.

**Ferramentas:** serde, serde_json, serde_yaml, toml

### #22 — WebAssembly (WASM) ⏱ 20–40h
**O que é:** Compilar Rust para rodar no browser com performance nativa. wasm-bindgen faz a ponte JS↔Rust.

**Projeto:** Editor de imagem no browser — filtros (blur, sharpen, edge detection) em Rust compilado para WASM.

**Dica:** Use wasm-pack para build. Entenda a diferença entre wasm32-unknown-unknown e wasm32-wasi.

**Ferramentas:** wasm-bindgen, wasm-pack, web-sys

### #23 — Parsers e Combinators ⏱ 25–50h
**O que é:** Construir parsers a partir de combinators menores — cada parser é uma função que consome input e retorna resultado + resto.

**Projeto:** Parser para uma linguagem de markup customizada (tipo Markdown) com error recovery.

**Dica:** Use nom ou chumsky — ambos são baseados em combinators.

**Ferramentas:** nom, chumsky, pest

### #24 — Interpretadores ⏱ 30–60h
**O que é:** Construir um interpretador para uma linguagem simples — AST, eval, ambiente, closures.

**Projeto:** Interpretador para uma linguagem com funções de primeira classe, closures e GC simples.

**Dica:** Siga o livro Crafting Interpreters — implemente em Rust simultaneamente.

**Ferramentas:** Rust puro, logos (lexer)

### #25 — FFI Avançado e unsafe ⏱ 30–60h
**O que é:** Interoperabilidade com C/C++ em nível avançado — callbacks, lifetimes em FFI, tipos opacos.

**Projeto:** Wrapper seguro para uma biblioteca C++ complexa (ex: SDL2 ou OpenGL).

**Dica:** Documente invariantes unsafe com comentários SAFETY. Use cxx para FFI C++ seguro.

**Ferramentas:** std::ffi, bindgen, cxx, saffi

### #26 — Design Patterns em Rust ⏱ 20–40h
**O que é:** Patterns adaptados para Rust — Builder, Strategy, Observer, State, Visitor via traits.

**Projeto:** Engine de eventos com pattern Observer usando trait objects e callbacks.

**Dica:** Muitos patterns de OO são mais simples em Rust — enums + match substituem Visitor.

**Ferramentas:** Rust puro

### #27 — gRPC e Protobuf ⏱ 25–50h
**O que é:** Comunicação entre serviços com Protocol Buffers — serialização binária eficiente e contratos tipados.

**Projeto:** Sistema de chat com gRPC — servidor streaming, cliente e definição de serviço em .proto.

**Dica:** Use tonic — integra com axum e tokio.

**Ferramentas:** tonic, prost (protobuf), prost-types

### #28 — WebSockets e SSE ⏱ 20–40h
**O que é:** Comunicação bidirecional em tempo real entre cliente e servidor.

**Projeto:** Dashboard de métricas em tempo real com WebSockets — servidor Rust, cliente HTML/JS.

**Dica:** Use tokio-tungstenite para WebSockets. SSE é mais simples para unidirecional.

**Ferramentas:** tokio-tungstenite, axum (WS nativo), warp

### #29 — CLI Avançado (TUI) ⏱ 25–50h
**O que é:** Interfaces de terminal interativas — janelas, menus, formulários, tabelas.

**Projeto:** Gerenciador de tarefas TUI com navegação por teclado, modais e temas.

**Dica:** Use ratatui — o framework TUI mais completo para Rust.

**Ferramentas:** ratatui, crossterm, dialoguer

### #30 — Processamento de CSV/JSON em Lote ⏱ 20–40h
**O que é:** Pipelines de dados eficientes — ler, transformar, agregar e escrever grandes volumes.

**Projeto:** ETL de dados públicos (ex: dados do IBGE) com validação, limpeza e agregação.

**Dica:** Use csv crate para streaming (não carregue tudo em memória). Para JSON, use serde_json com streaming.

**Ferramentas:** csv, serde_json, polars (DataFrames)

---

*(Níveis 3 e 4 mantidos conforme original — tópicos #31–#100)*

---

## 🟠 NÍVEL 3 — Avançado: Regras Diferentes (#61 ao #80)

Projetos de longa duração. Escolha pelos seus objetivos, não pela ordem numérica. Faixa total: 1190–2120h (média ~1655h).

## 🔴 NÍVEL 4 — Hardcore: Onde os Gigantes Pisam (#81 ao #100)

Fronteiras da engenharia. Alguns desses tópicos são carreiras inteiras. Faixa total: 3000–6000h (média ~4500h).

---

## 📚 ONDE PESQUISAR E PRATICAR — 25 Recursos com Links

| Recurso | Como usar / Por que | Tópicos / Tipo |
|---------|---------------------|----------------|
| **[The Rust Programming Language](https://doc.rust-lang.org/book/)** (doc.rust-lang.org/book) | Leia linear do cap. 1 ao 20. Caps. 4 (ownership), 10 (generics/traits) e 15 (smart pointers) são os mais importantes. Releia quando travar. O livro oficial usado em Stanford e MIT. | #1 ao #20 — GRATUITO |
| **[Rustlings](https://github.com/rust-lang/rustlings)** (github.com/rust-lang/rustlings) | Instale com 'cargo install rustlings'. Faça em paralelo com The Book. ~100 exercícios com erros de compilação reais. | #1 ao #10 — GRATUITO |
| **[Rust by Example](https://doc.rust-lang.org/rust-by-example/)** (doc.rust-lang.org/rust-by-example) | Use como referência. Procure o conceito e veja o exemplo rodável. | #1 ao #15 — GRATUITO |
| **[Comprehensive Rust](https://google.github.io/comprehensive-rust/)** (google.github.io/comprehensive-rust) | Alternativa mais concisa ao The Book para quem vem de C/C++ ou Go. Vai mais direto ao ponto. | #1 ao #12 — GRATUITO |
| **[Jon Gjengset — Crust of Rust](https://www.youtube.com/@jonhoo)** (YouTube) | O melhor canal de Rust do mundo. Jon implementa crates reais ao vivo explicando cada decisão. | #13 Async, #46 Macros — GRATUITO |
| **[Zero to Production in Rust](https://www.zero2prod.com/)** (Palmieri) | O melhor livro de backend Rust. Constrói uma newsletter API completa: axum, sqlx, autenticação, deploy. | #14 API REST — PAGO ~$40 |
| **[Tokio Tutorial Oficial](https://tokio.rs/tokio/tutorial)** (tokio.rs/tokio/tutorial) | Constrói um cliente/servidor Redis do zero ensinando channels, tasks, mutex async. | #15 Async — GRATUITO |
| **[Bevy Cheatbook](https://bevy-cheatbook.github.io/)** (bevy-cheatbook.github.io) | Mais útil que a documentação oficial — tem exemplos por feature, não por API. | #41 Game Dev — GRATUITO |
| **[Learn Wgpu](https://sotrh.github.io/learn-wgpu/)** (sotrh.github.io/learn-wgpu) | O ÚNICO tutorial completo de wgpu — do triângulo até texturas, câmera, iluminação. | #42 Renderização — GRATUITO |
| **[The Embedded Rust Book](https://docs.rust-embedded.org/book/)** (docs.rust-embedded.org/book) | Leia os primeiros 5 capítulos antes de qualquer Embassy. | #45 IoT — GRATUITO |
| **[Writing an OS in Rust](https://os.phil-opp.com/)** (os.phil-opp.com) | A série mais detalhada de OSDev em Rust. Cobre bootloader, VGA, interrupções, paginação. | #91 VMM, #99 OS — GRATUITO |
| **[The Rustonomicon](https://doc.rust-lang.org/nomicon/)** (doc.rust-lang.org/nomicon) | O guia oficial de unsafe Rust. Leia quando precisar de unsafe para motivo específico. | #25 FFI, #53 Lock-free — GRATUITO |
| **[Candle — HuggingFace](https://github.com/huggingface/candle)** (github.com/huggingface/candle) | Clone o repositório e rode os exemplos primeiro. A documentação é escassa — leia o código. | #57 VectorDB, #94 ML — GRATUITO |
| **[Burn — Framework ML](https://burn.dev/)** (burn.dev) | Siga o livro em ordem. Implemente MNIST primeiro. Use backend WGPU para rodar sem CUDA. | #94 ML Treino — GRATUITO |
| **[Crafting Interpreters](https://craftinginterpreters.com/)** (Nystrom) | O melhor livro de implementação de linguagens. Leia Parte I e implemente em Rust simultaneamente. | #23 Parser, #24 Interpretador — GRATUITO |
| **[Proc Macro Workshop](https://github.com/dtolnay/proc-macro-workshop)** (dtolnay) | Série de exercícios para aprender proc macros implementando Builder, derive Debug, etc. | #46 Proc Macros — GRATUITO |
| **[Anchor Framework Book](https://www.anchor-lang.com/docs)** (anchor-lang.com/docs) | Comece pelo quickstart, implemente todo-list on-chain, depois token vesting. | #63 Blockchain — GRATUITO |
| **[RustCrypto](https://github.com/RustCrypto)** (github.com/RustCrypto) | Implementações auditadas de AES, SHA, RSA, ECDSA. Use SEMPRE em vez de implementar do zero. | #34 Segurança — GRATUITO |
| **[Database Internals](https://www.amazon.com.br/dp/1492040347)** (Alex Petrov) | Como bancos funcionam internamente: B-Trees, LSM Trees, WAL, replicação, consensus. | #48 DB Internals — PAGO |
| **[Learning Rust With Entirely Too Many Linked Lists](https://rust-unofficial.github.io/too-many-lists/)** | O livro mais famoso para aprender ownership profundamente. Não desista no capítulo 4. | #11 Estruturas Manuais — GRATUITO |
| **[OS: Three Easy Pieces](http://pages.cs.wisc.edu/~remzi/OSTEP/)** (Arpaci-Dusseau) | O melhor livro de sistemas operacionais — cobre virtualização, concorrência e persistência. | #91 VMM, #92 CoW FS — GRATUITO |

---

## 💡 DICAS PARA A JORNADA

### Borrow Checker — Seu Par, Não Seu Inimigo
Leia a mensagem de erro COMPLETA antes de qualquer outra coisa. O compilador Rust tem as melhores mensagens de erro de qualquer linguagem mainstream — incluindo sugestões de correção. Se travar mais de 30 min, vá ao Discord oficial do Rust ou ao Users Forum — a comunidade é extremamente prestativa e acolhedora para iniciantes.

### Curva de Aprendizado
Os primeiros 2 meses são mais lentos — isso é completamente normal e esperado. Depois do borrow checker 'clicar' (e ele vai clicar para todo mundo que persiste), a velocidade de desenvolvimento aumenta dramaticamente. Muita gente desiste antes desse momento. Seja paciente consigo mesmo.

### Game Dev (Bevy)
Comece com Snake ou Pong — nunca com um RPG ou MMORPG. Bevy paraleliza sistemas automaticamente quando não há conflito de componentes. A comunidade no Discord do Bevy é a mais ativa e acolhedora do ecossistema Rust inteiro.

### Frontend sem JavaScript
Leptos e Yew existem e estão em produção. Leptos tem SSR, hidratação e reatividade granular — performance próxima a vanilla JS. Bevy compila para WASM — jogos Rust rodando no browser são possíveis e reais. Não é mainstream ainda mas é produção-ready.

### Async e Tokio
Entenda Futures ANTES de depurar problemas de async. Assista 'Crust of Rust: Async' do Jon Gjengset — é o melhor recurso em vídeo sobre async Rust que existe. Nunca misture tokio e async-std no mesmo projeto. Prefira tokio para qualquer projeto sério.

### Embarcados (Embassy)
Comece com ESP32-S3 (barato, USB nativo, WiFi integrado) antes de ir para STM32. defmt é infinitamente melhor que println! para debugging em hardware. probe-rs substitui o GDB para debugging em microcontroladores — flash, debug e RTT logs em um único comando.

### Ferramentas do Dia a Dia — Use Desde o Dia 1
cargo clippy (linter que encontra antipadrões) e cargo fmt (formatação automática) são obrigatórios. cargo-expand mostra código gerado por macros. cargo-flamegraph para profiling de CPU. cargo-audit para CVEs em dependências. cargo-nextest para testes 3x mais rápidos. rust-analyzer no VS Code ou Neovim é indispensável.

### Rust no Mercado em 2025
9 anos consecutivos como linguagem mais amada no StackOverflow Developer Survey. Amazon (Firecracker para EC2), Microsoft (Windows kernel e Azure), Google (Android e Chrome), Meta, Cloudflare (Pingora CDN), Discord, Figma, 1Password. O mercado está crescendo forte — especialmente em infraestrutura, sistemas, segurança e IA de baixa latência.

### HFT e Finanças
NUNCA use f64 para valores monetários — ponto flutuante binário não representa exatamente 0.1 + 0.2. Rust é a linguagem mais adotada em trading de alta frequência depois de C++ — latência determinista e ausência de GC são fundamentais para estratégias de microssegundos.

### Blockchain e Web3
Solana é escrita em Rust nativamente e tem a maior comunidade Rust em blockchain. Anchor elimina 80% do boilerplate de programas Solana — use desde o dia 1. tfhe-rs da Zama é o estado da arte em criptografia homomórfica — completamente escrito em Rust.

---

## 🦀 Lembrete final

O objetivo NÃO é fazer os 100 tópicos. É dominar a trilha que alinha com o que você quer construir. Comece sempre pelo #1 (CLI). **Rust é para a vida toda — aproveite cada etapa da jornada.**

> ⚡ Aviso: Se bater a dúvida, vá de API Web (Axum) para trabalho ou CLI (Clap) para algo rápido hoje. Cada tópico que você domina é para sempre.
