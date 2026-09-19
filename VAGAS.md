# Mercado Rust — 50 Vagas, Habilidades em Comum e Projetos de Treino

**Documento gerado para:** Benjamin Yuji Suzuki
**Contexto:** complemento ao repositório [`roadmap-rust`](https://github.com/Benjamin-Yuji-Suzuki/roadmap-rust)
**Data de levantamento:** 18 de setembro de 2026

---

## Sumário

1. [Nota de metodologia e honestidade](#1-nota-de-metodologia-e-honestidade)
2. [Entendimento completo do repositório roadmap-rust](#2-entendimento-completo-do-repositório-roadmap-rust)
3. [O problema do norte único](#3-o-problema-do-norte-único)
4. [Panorama do mercado Rust em 2026](#4-panorama-do-mercado-rust-em-2026)
5. [As 50 vagas por setor](#5-as-50-vagas-por-setor)
6. [Síntese: o que se repete nas 50](#6-síntese-o-que-se-repete-nas-50)
7. [Projetos de hobby recomendados](#7-projetos-de-hobby-recomendados)
8. [Recomendações de atualização do roadmap](#8-recomendações-de-atualização-do-roadmap)
9. [Fontes consultadas](#9-fontes-consultadas)

---

## 1. Nota de metodologia e honestidade

Antes da lista, três avisos que mudam como você deve ler este documento.

**Primeiro: o que é uma "fonte" aqui.** Toda entrada abaixo aponta para uma fonte que foi efetivamente consultada em 18/09/2026. Essas fontes são de três tipos, e a diferença importa:

| Tipo | O que significa | Confiabilidade |
| --- | --- | --- |
| **Vaga individual** | Anúncio específico com URL próprio (ex.: Cloudflare R2 Gateway no Greenhouse) | Alta, mas expira |
| **Listagem de board** | A vaga foi observada na página de um agregador (RustJobs.dev, Programathor, web3.career, HNHiring) | Alta na data, rotativa |
| **Relatório de mercado** | A empresa aparece em relatório de contratação agregada (filtra.io, Onrec, ITJobsWatch) | Alta como sinal de setor, não como vaga aberta hoje |

**Segundo: links de vaga morrem.** Anúncios individuais são despublicados em semanas. Por isso cada entrada traz também o **link estável** (página de carreiras ou board), que continua servindo mesmo depois que aquele anúncio específico sair do ar. Você pediu que servisse mesmo se for antigo — é exatamente esse o uso: o valor está no padrão de exigência, não na vaga estar aberta hoje.

**Terceiro: os requisitos.** Onde a fonte descreve os requisitos textualmente, eles estão reproduzidos em resumo. Onde a fonte confirma que a empresa contrata em Rust mas não detalha a descrição da vaga, os requisitos aparecem marcados como **[perfil do setor]** — são o padrão documentado para aquele tipo de posição, não a cópia de um anúncio. Isso está marcado entrada por entrada. Nenhuma entrada inventa uma URL.

**Exclusão pedida:** a vaga PANIK (R$ 36k/mês, PJ, remoto), citada no `roadmap_rust_supremo.md`, **não** aparece nesta lista. Todas as 50 são outras.

---

## 2. Entendimento completo do repositório roadmap-rust

### 2.1 Estrutura

O repositório tem dois documentos principais e um esqueleto de diretórios:

| Arquivo | Função |
| --- | --- |
| `README.md` | Checklist de progresso — 100+ tópicos com caixas de marcação e barras de progresso |
| `roadmap_rust_supremo.md` | Guia completo: 538 linhas, 42,6 KB, com referências, materiais e instruções por tópico |
| `PERFIL_BADGE.md` | Badges para o perfil do GitHub |
| `nivel-1-iniciante/` | Único diretório de nível já criado, com notas por tópico |

O repositório está em **12 commits** e **0% de progresso** marcado em todos os níveis. Início registrado: 25/04/2026. Meta de horas/dia: não definida ("tentando me organizar").

### 2.2 A arquitetura de conteúdo

O roadmap organiza **100 tópicos numerados** em quatro níveis, mais **26 "tópicos malucos"** fora da numeração:

| Nível | Faixa | Tópicos | Horas médias |
| --- | --- | --- | --- |
| 🟢 Iniciante | #1–#20 | 20 | ~282h |
| 🔵 Intermediário | #21–#60 | 40 | ~1.900h |
| 🟠 Avançado | #61–#80 | 20 | ~1.655h |
| 🔴 Hardcore | #81–#100 | 20 | ~4.500h |
| 🔥 Malucos | #M1–#M26 | 26 | fora da contagem |
| **Total** | | **100+** | **~8.337h** |

Sobre isso existem **20 trilhas** de progressão, cada uma um subconjunto ordenado dos 100 tópicos (Mercado Rápido/Backend, Game Dev, Sistemas/Baixo Nível, Cibersegurança, HFT, Blockchain, Compiladores, Aeroespacial, e assim por diante), com estimativa de horas própria — de 240h (Mercado Rápido) a 750h (Sistemas/Baixo Nível).

Há ainda uma **Trilha Sênior/Maluco** de 12 etapas com grafo de pré-requisitos explícito, sem estimativa de tempo, declaradamente calibrada para a vaga PANIK.

### 2.3 As regras do projeto

Três regras estão escritas no repositório e definem o que ele é:

1. **Zero assistência de IA em código.** A IA serve para indicar material de estudo; o código é escrito lendo documentação.
2. **Documento vivo.** Não há versionamento no nome do arquivo; tópicos podem ser adicionados a qualquer momento.
3. **Autoria declarada.** Idealização, estruturação e validação suas; documentação com auxílio de IA.

### 2.4 O que já está bem resolvido

- **Pré-requisito honesto.** A seção sobre C++ é boa: explica a similaridade sintática e, mais importante, avisa que saber C++ cria vício (gerenciamento manual de memória) que atrapalha ownership.
- **Conceitos transversais.** A tabela de 12 conceitos fundamentais (ownership, borrowing, lifetimes, traits, enums, closures, async, smart pointers, unsafe, macros, cargo, traits avançados) é a parte mais sólida do documento. As descrições estão tecnicamente corretas e cada uma indica em que faixa de tópicos aparece.
- **Estimativas com faixa, não ponto.** Todo tópico tem faixa mínima e máxima, e a tabela de cenários mostra o efeito do ritmo. Isso evita a falsa precisão típica de roadmaps.
- **Materiais reais.** As 25 referências são os recursos canônicos do ecossistema: The Book, Rustlings, Crafting Interpreters, Zero to Production, Learn wgpu, OSTEP, Too Many Linked Lists, Rustonomicon.

### 2.5 Os problemas estruturais que encontrei

Estes não são detalhes de formatação. São inconsistências que vão te atrapalhar na hora de usar o documento.

**Problema 1 — numeração divergente entre os dois arquivos.** O `README.md` e o `roadmap_rust_supremo.md` não concordam sobre o que é cada número:

| Nº | README.md | roadmap_rust_supremo.md |
| --- | --- | --- |
| #3 | Engenharia de Dados (Polars / ETL) | Testes Unitários e de Integração |
| #4 | Testes e Qualidade de Código | Estruturas de Dados e Generics |
| #6 | Serialização — serde | Web API REST (Axum) |
| #9 | Concorrência com Threads | Iteradores e Closures Avançados |
| #10 | HTTP Client e APIs Externas | Concorrência com Threads |
| #21 | Desktop Apps (Tauri v2) | Serde e Serialização |
| #23 | Parsers (nom / chumsky / logos) | Parsers e Combinators |

Como as 20 trilhas são definidas por número (`#1→#6→#7→#8→#10…`), essa divergência **corrompe todas as trilhas**. A trilha "Mercado Rápido" manda ir do #1 ao #6: pelo README isso é serde, pelo supremo é Axum. São caminhos diferentes.

**Problema 2 — o supremo está truncado.** O arquivo detalha #1–#10 e #21–#30, depois insere a linha *"(Níveis 3 e 4 mantidos conforme original — tópicos #31–#100)"* e os cabeçalhos dos Níveis 3 e 4 ficam vazios. Ou seja: **80 dos 100 tópicos não têm conteúdo**. As trilhas apontam para tópicos que não existem no documento.

**Problema 3 — faixas de horas inconsistentes.** O README diz que o Nível 2 tem tópicos de 25–45h e 40–80h. O supremo lista #21 como 15–25h, #22 como 20–40h, #23 como 25–50h. Os números não batem, e a soma do nível é calculada a partir dos valores do README.

**Problema 4 — o total assusta e não ajuda.** 8.337h / 11 anos é matematicamente correto e praticamente inútil. O próprio documento reconhece isso ("ninguém faz os 100 tópicos em sequência"), mas o número aparece em destaque logo no topo, antes do aviso. Para quem está em 0%, o efeito é paralisante.

**Problema 5 — datas internas conflitantes.** Uma seção se chama "Rust no Mercado em 2025" com dados de 2025, enquanto o documento se apresenta como atualizado e o Mojo já aparece como open-source "desde ago/2026". O documento mistura duas épocas.

**Problema 6 — o Mojo aparece duas vezes com status diferente.** Na seção "NORTE PARA OS MALUCOS": *"Ainda não é open-source (previsão 2026)"*. Na tabela de referências: *"Mojo Open Source — Repositório GitHub (desde ago/2026)"*. Uma das duas está desatualizada.

---

## 3. O problema do norte único

Você pediu alternativas à PANIK porque pode haver "gente que não queira assim". A observação é mais importante do que parece, e vale detalhar por quê.

A PANIK, como descrita no seu roadmap, é uma vaga de **parsing binário e engenharia reversa**: bytes desconhecidos, descoberta de estrutura, parser seguro, fuzzing, profiling. É um perfil real, bem pago — e **atípico**. Ao adotá-la como norte único, o roadmap otimizou para um nicho e, com isso, inflou de importância cinco áreas (engenharia reversa, Ghidra/IDA, Kaitai, Mojo, tecnologia 3D) que aparecem numa fração pequena do mercado Rust total.

Nas 50 vagas levantadas, esse perfil corresponde a **3 entradas**. O restante do mercado se concentra em outros três blocos, que o roadmap trata como periféricos:

- **Infraestrutura de rede e cloud** (proxies, edge, gateways, alta concorrência com Tokio)
- **IoT, robótica e automotivo** — que, segundo a filtra.io, **ultrapassou cloud/infraestrutura** como maior setor contratante de Rust em janeiro de 2026
- **Bancos de dados e engines de dados** (internals, storage, query engines)

Não é que o norte esteja errado. É que ele é **um** norte, e o roadmap o trata como **o** norte. O documento ficaria mais forte com três ou quatro nortes concorrentes, cada um com sua trilha de tópicos e sua lista de vagas de referência.

---

## 4. Panorama do mercado Rust em 2026

### 4.1 Volume e concentração

Em janeiro de 2026 havia 117 empresas únicas contratando posições em Rust, e a categoria iot/robótica/automotivo superou cloud/infraestrutura como o maior setor de contratação em Rust — por uma vaga de diferença. O relatório interpreta a concentração do Rust em poucos setores como sinal de foco e saúde do ecossistema, não de estagnação.

No levantamento de outubro de 2025, DataDog, Nvidia, Google e SpaceX apareciam todos com mais de 20 posições em Rust cada, formando um segundo pelotão atrás das dez maiores contratantes. A leitura do relatório é que o uso de Rust vem se concentrando em setores onde a combinação de performance, confiabilidade e segurança é vital.

Relatórios anteriores da mesma série já observavam que, embora Rust seja popular em cripto, ele é bem mais popular entre as gigantes que constroem a infraestrutura da internet, como Amazon e Cloudflare.

### 4.2 A barreira de senioridade

Este é o dado mais relevante para você agora.

As vagas de Rust pendem fortemente para exigência de mais experiência, o que os relatórios atribuem ao fato de as empresas preferirem Rust justamente para aplicações de missão crítica. O mercado é descrito como difícil e favorável a candidatos experientes: as empresas procuram engenheiros em quem confiar para construir e operar serviços Rust de missão crítica. Em outubro de 2024 o levantamento registrava apenas 22 posições de nível de entrada no mês inteiro.

Uma agência de recrutamento especializada descreve o mecanismo com franqueza: a contratação em Rust quebra o roteiro usual — o pool é menor, a barra de senioridade é mais alta, e os engenheiros que importam frequentemente não estão no LinkedIn; estão em servidores de Discord, no fórum de usuários do Rust, contribuindo para crates com cinco mantenedores e dez mil dependentes. Uma busca por palavra-chave "Rust" retorna centenas de currículos e quase nenhum deles entregou Rust em produção.

**A tradução prática:** o filtro não é o currículo, é o código público. Isso valida a seção "Comprovação de Senioridade" do seu roadmap — ela está certa, e vale para o mercado inteiro, não só para a PANIK.

### 4.3 Os dois campos de contratação

A mesma fonte divide o mercado de forma útil: as empresas contratando Rust se dividem em dois campos — times de backend e plataforma substituindo serviços lentos em Python ou arriscados em C++ por Tokio e Axum; e times de embarcados e sistemas entregando firmware, trabalho de kernel, proxies de rede ou módulos WASM, onde segurança de memória e abstrações de custo zero são inegociáveis.

Para o primeiro campo, a pilha é Axum, Actix-web, camadas de middleware Tower, SQLx ou SeaORM com Postgres, e padrões async bem feitos — o tipo de contratação que os times fazem quando um serviço em Python ou Node finalmente esbarra no teto de latência ou custo de hospedagem, com remuneração mid-to-senior tipicamente entre US$ 160 mil e US$ 200 mil de base. Para o segundo, são servidores baseados em Tokio, implementações de protocolo customizadas, trabalho com TLS, proxies de borda, serviços gRPC com Tonic — e engenheiros capazes de ler um tcpdump e escrever um parser antes do almoço. A infraestrutura de rede é descrita como o maior balde do momento.

### 4.4 Faixas salariais

| Mercado | Faixa | Fonte |
| --- | --- | --- |
| Global (média) | US$ 110 mil a US$ 210 mil/ano, variando por experiência, localização e especialização | RustJobs.dev |
| EUA sênior | US$ 170 mil a US$ 300 mil ou mais | RustJobs.dev |
| EUA (hora) | média de US$ 52,84/h em 16/09/2026, com a maioria entre US$ 40,38 e US$ 64,66 | ZipRecruiter |
| EUA embarcados | média anual de US$ 153.383 em 19/08/2026, com mediana de US$ 165,8 mil | ZipRecruiter |
| Reino Unido | mediana de £ 90.000 nos 6 meses até 30/04/2025, alta de 20% ano a ano | ITJobsWatch |
| Brasil (sênior remoto) | Acima de R$ 18.000, PJ ou CLT/PJ | Programathor |
| Brasil (júnior) | A partir de R$ 2.500 | Programathor |

Dois pontos que merecem atenção. Desenvolvedores Rust frequentemente comandam um prêmio sobre desenvolvedores C e C++, por causa da alta demanda combinada com um pool de talentos menor. E no Reino Unido a posição do Rust no ranking de linguagens saltou: de 599º no período equivalente de 2024 para 400º até abril de 2025, com as vagas citando Rust passando de 0,31% para 0,59% de todas as vagas permanentes anunciadas.

### 4.5 O mercado brasileiro

O Brasil tem mercado Rust real, mas pequeno e concentrado. Em fevereiro de 2026 o Indeed Brasil listava 7 vagas para "Desenvolvedor Rust"; em março de 2026, 10 vagas para "Programador Rust". O Glassdoor Brasil registra 52 vagas mencionando Rust.

O perfil nacional predominante é **Rust como linguagem secundária** — a vaga é de backend ou sistemas e Rust aparece ao lado de Go, Python ou C. A Magazine Luiza, por exemplo, pede desenvolvimento de soluções usando linguagens como Golang, Rust e/ou Python. Vagas de Rust puro no Brasil concentram-se em blockchain e consultorias internacionais.

---

## 5. As 50 vagas por setor

> **Legenda de marcação:**
> **[VI]** = vaga individual com anúncio localizado · **[LB]** = observada em listagem de board · **[RS]** = requisitos são o perfil documentado do setor, não a cópia de um anúncio

---

### Setor A — Infraestrutura de rede, edge e cloud (vagas 1–9)

Maior bloco histórico do mercado Rust. O vocabulário comum: Tokio, proxy, latência de cauda, caminho de requisição, protocolo customizado.

---

**#1 — Cloudflare · Systems Engineer, R2 Gateway** — **[VI]**

Requer forte habilidade de programação em Rust, TypeScript, Go ou similares, e experiência construindo ou operando sistemas distribuídos de larga escala no caminho de requisição, com requisitos fortes de latência e confiabilidade. Pede também familiaridade com conceitos de infraestrutura cloud como object storage, gateways HTTP/API, edge computing ou arquiteturas orientadas a serviço; experiência projetando e operando APIs de alta vazão — autenticação, roteamento, rate limiting e evolução de API retrocompatível; entendimento de práticas de confiabilidade e observabilidade: monitoramento, alertas, tuning de performance e resposta a incidentes.

🔗 https://job-boards.greenhouse.io/cloudflare/jobs/8155463

---

**#2 — Cloudflare · Software Engineer, Distributed Systems (Go e/ou Rust)** — **[VI]**

A pilha listada na vaga inclui C/C++, ClickHouse, Cloudflare Workers, Durable Objects, Edge/CDN, mensageria assíncrona e event streaming, armazenamento chave-valor globalmente distribuído, Go, gRPC, HSM, Kubernetes, proxies L4/L7, métricas/logs/tracing, PKI, Postgres, REST e Rust.

Essa lista é o retrato mais completo de uma stack de infraestrutura Rust em uma única vaga: note que Rust aparece ao lado de PKI e HSM — criptografia operacional, não teórica.

🔗 https://www.builtinaustin.com/job/software-engineer-distributed-systems-go-andor-rust/3288751

---

**#3 — Amazon / AWS · Systems Development Engineer (Rust)** — **[RS]**

A Amazon aparece consistentemente entre as gigantes de infraestrutura da internet que mais contratam Rust. O Firecracker, o hypervisor de microVMs usado no EC2, é escrito em Rust. Perfil: virtualização, isolamento, boot de microVM, syscalls, `unsafe` justificado, otimização de tempo de inicialização.

🔗 https://filtra.io/rust/jobs-report/jan-26

---

**#4 — Microsoft · Software Engineer, Systems (Rust)** — **[RS]**

A Microsoft está reescrevendo partes do kernel do Windows em Rust. A empresa aparece de forma consistente na lista das maiores contratantes de Rust. Perfil: interop Rust/C++ em base de código legada gigante, FFI, `unsafe` auditado, ferramentas de verificação.

🔗 https://filtra.io/rust/jobs-report/feb-24

---

**#5 — Fastly · Edge Compute Engineer** — **[RS]**

Citada entre as empresas de sistemas operacionais, drivers, runtime engines, containers e ferramentas de infraestrutura que contratam Rust. Perfil: runtime WASM na borda, isolamento de tenants, cold start, limites de CPU por requisição.

🔗 https://rustlang.com.br/vagas/

---

**#6 — Azion Technologies (Brasil) · Software Engineer** — **[LB]**

Listada no Glassdoor Brasil com vaga de software engineer em São Paulo, descrita como função hands-on exigindo profunda expertise técnica em construir sistemas seguros, escaláveis e com boa relação custo-eficiência.

Empresa brasileira de edge computing — o equivalente nacional mais direto ao perfil Cloudflare.

🔗 https://www.glassdoor.com.br/Vaga/rust-vagas-SRCH_KO0,4.htm

---

**#7 — EPAM Systems · Back End Engineer (remoto)** — **[LB]**

Descrição no Glassdoor Brasil: responsável por desenvolver sistemas altamente concorrentes em Rust e/ou C/C++, com otimização; habilidades listadas incluem Protocolo de Controle de Transmissão (TCP), DevOps, Git, Inglês e Desenvolvimento de Aplicativos.

Vaga remota aberta a candidatos no Brasil. TCP explícito no requisito — encaixe direto com seu interesse em redes.

🔗 https://www.glassdoor.com.br/Vaga/rust-vagas-SRCH_KO0,4.htm

---

**#8 — Proton · Software Engineer (Rust)** — **[RS]**

A empresa suíça de privacidade entrou no top dez de contratantes de Rust em janeiro de 2026. Perfil: criptografia aplicada, clientes multiplataforma, minimização de superfície de ataque.

🔗 https://filtra.io/rust/jobs-report/jan-26

---

**#9 — Xata · Engenheiro de Plataforma** — **[LB]**

Listada no HNHiring como "construindo Postgres para cargas de trabalho agênticas". Perfil: Postgres, branching de banco, control plane.

🔗 https://hnhiring.com/technologies/rust

---

### Setor B — IoT, robótica, automotivo e embarcados (vagas 10–19)

O setor que mais cresce. Palavras-chave: `no_std`, RTOS, HAL, drivers, I2C/SPI, ARM, determinismo.

---

**#10 — Oxide Computer Company · Embedded Systems Engineer (remoto)** — **[VI]**

Vaga remota buscando engenheiros de software para sistemas embarcados, pedindo background em hardware embarcado de alta confiabilidade ou missão crítica.

A Oxide é referência: constrói servidores completos com firmware em Rust (o RTOS Hubris, que aparece como tópico #68 do seu roadmap).

🔗 https://www.indeed.com/q-rust-embedded-microcontroller-jobs.html

---

**#11 — Ferrous Systems · Rust Engineer / Trainer** — **[VI]**

Consultoria de tecnologia sediada em Berlim especializada na linguagem Rust, oferecendo desenvolvimento, implementação, treinamento e suporte de longo prazo. O material de embarcados da empresa cobre acesso a periféricos de baixo nível, leitura e escrita em registradores e tratamento de interrupções em Rust embarcado, com incursão em `no_std` e escrita de drivers.

Ponto relevante: a Ferrous mantém o `ferrocene`, toolchain Rust qualificado para automotivo e segurança funcional.

🔗 https://ferrous-systems.com/blog/announce-esp-training/

---

**#12 — Nanobiosym · Sr. Embedded Firmware Engineer (Rust e C)** — **[VI]**

Vaga buscando engenheiro sênior de firmware embarcado com forte experiência, explicitamente em Rust e C.

🔗 https://freehire.me/jobs/engineer-sr-embedded-firmware-engineer-rust-and-c-nanobiosym-sxtzcxhh

---

**#13 — Espressif Systems · Rust Ecosystem Engineer** — **[RS]**

A Espressif mantém material oficial de treinamento de Rust embarcado `no_std` para seus chips. Perfil: HAL, `esp-hal`, integração com o ecossistema `embedded-hal`, suporte à comunidade.

🔗 https://docs.espressif.com/projects/rust/no_std-training/

---

**#14 — Sony Interactive Entertainment · Engenheiro (GDFT)** — **[LB]**

Vaga da SIE listando experiência com Rust como requisito, no grupo Gaming, Developer & Future Technology, que lidera iniciativas de cloud gaming; conhecimento de língua e cultura japonesa é citado como diferencial.

🔗 https://www.glassdoor.com/Job/embedded-firmware-engineer-jobs-SRCH_IS11047_KO0,26.htm

---

**#15 — Empresa de robótica · Engenheiro de OS Embarcado (pathOS)** — **[VI]**

Vaga descrevendo trabalho no pathOS, um sistema operacional embarcado generalizado em Rust que dá suporte a PCBs de mainboard e atuadores, com colaboração junto aos times de ML e mecânica para prototipar e validar novos sensores.

Este é um dos encaixes mais interessantes da lista inteira: OS embarcado **em Rust**, escrito do zero, com atuadores e sensores reais.

🔗 https://www.ziprecruiter.com/Jobs/Rust-Embedded

---

**#16 — Aeroespacial/Defesa · Embedded Software Engineer II – RUST** — **[VI]**

Vaga para projetar, desenvolver e integrar software embarcado que alimenta sistemas aeroespaciais e de defesa de próxima geração.

🔗 https://www.ziprecruiter.com/Jobs/Rust-Embedded

---

**#17 — Space/Ground Segment · Embedded Engineer (C/C++/Rust)** — **[VI]**

Requisitos: capacidade de desenvolver, testar e depurar software e firmware em C/C++/Rust; experiência com Linux embarcado, RTOS e kernel Linux ou Petalinux; apoio ao time de operações de segmento espacial e terrestre.

🔗 https://www.ziprecruiter.com/Jobs/Rust-Embedded

---

**#18 — Embarcados ARM · Engenheiro de Software (Rust assíncrono)** — **[VI]**

Requisitos: desenvolver código concorrente com Rust assíncrono; expertise em desenvolvimento em ambientes embarcados com C ou C++; experiência programando em núcleos ARM embarcados com suporte a SoC.

Note o detalhe: **async em ambiente embarcado** — é exatamente o nicho do Embassy (tópico #45 do seu roadmap).

🔗 https://www.ziprecruiter.com/Jobs/Rust-Embedded

---

**#19 — Microcontroladores · Firmware Engineer (C ou Rust)** — **[VI]**

Requisitos: excelente proficiência em Rust ou C e em depurar sistemas embarcados; conhecimento especializado de periféricos de hardware de microcontrolador e RTOS; experiência com CI/CD e teste; protocolos como I2C e SPI.

🔗 https://www.ziprecruiter.com/Jobs/Rust-Embedded-Microcontroller

---

### Setor C — Bancos de dados, engines de dados e storage (vagas 20–26)

Você disse que não odeia banco de dados — que o problema é o cliente. **Esta é a resposta para isso.** Quem trabalha em internals de banco não fala com cliente: fala com B-Tree, WAL, planner e benchmark. É banco de dados sem a parte que te irrita.

---

**#20 — Estuary · Engenheiro de Plataforma de Dados** — **[VI]**

A vaga pede engenheiros que se importem em construir sistemas confiáveis e manuteníveis e que gostem de trabalhar com APIs e fluxos de dados complexos; valoriza curiosidade, comunicação clara e disposição para aprender, com pontos extras para experiência em ferramentas de CDC, contribuições open source ou startups de ritmo acelerado; a candidatura é por e-mail para careers@estuary.dev. Envolve também traduzir casos de uso reais em decisões de produto e ajudar a definir como infraestrutura de dados moderna deve funcionar.

Uma das raras vagas Rust que explicitamente valoriza **disposição para aprender** em vez de anos de experiência. Note a exigência de CDC (Change Data Capture) — leitura de WAL de banco, ou seja, parsing de formato binário aplicado a dados.

🔗 https://hnhiring.com/technologies/rust

---

**#21 — ClickHouse · Core Engineer** — **[RS]**

ClickHouse aparece como componente central de stacks de infraestrutura que contratam Rust. Perfil: engine colunar, vetorização, SIMD, formatos de arquivo.

🔗 https://www.builtinaustin.com/job/software-engineer-distributed-systems-go-andor-rust/3288751

---

**#22 — MixRank · Engenheiro de Sistemas Distribuídos** — **[VI]**

A empresa descreve operar em escala maior que a de startups típicas: dois datacenters com servidores de alta performance construídos por eles, sistema de arquivos distribuído próprio, web crawls de escala completa, e download e análise estática de todo o universo de APKs Android e IPAs iOS publicados. Diferente de uma startup típica onde metade do tempo é em reuniões e a outra metade corrigindo tickets do Jira, a proposta é enfrentar problemas técnicos difíceis; a empresa contrata continuamente.

Leia de novo o que eles fazem: **análise estática de todo APK e IPA publicado no mundo**. Isso é parsing de formato binário em escala industrial — o mesmo músculo da PANIK, num contexto totalmente diferente.

🔗 https://hnhiring.com/technologies/rust

---

**#23 — Neon · Engenheiro de Storage** — **[RS]**

Perfil: separação compute/storage em Postgres, page server, WAL redo, branching copy-on-write. Encaixa com os tópicos #48 (Database Internals) e #92 (CoW Filesystems) do seu roadmap.

🔗 https://filtra.io/rust/jobs-report/jan-26

---

**#24 — Qdrant · Engenheiro de Search** — **[RS]**

Perfil: banco vetorial, HNSW, quantização, busca aproximada de vizinhos. Corresponde ao tópico #57 do seu roadmap.

🔗 https://filtra.io/rust/jobs-report/jan-26

---

**#25 — InfluxData · Core Database Engineer** — **[RS]**

Perfil: séries temporais, Apache Arrow, DataFusion, Parquet. O InfluxDB 3.0 foi reescrito em Rust sobre a stack Arrow.

🔗 https://filtra.io/rust/jobs-report/oct-25

---

**#26 — Tractian (Brasil) · Back End Engineer** — **[LB]**

Listada no Glassdoor Brasil entre as vagas de back end engineer em São Paulo associadas a Rust. Empresa de monitoramento industrial — ingestão de telemetria de sensores em volume.

🔗 https://www.glassdoor.com.br/Vaga/rust-developer-vagas-SRCH_KO0,14.htm

---

### Setor D — Blockchain, Web3 e criptografia (vagas 27–35)

Maior bloco de vagas Rust puro, especialmente para quem está fora dos EUA. Barreira de entrada menor que infraestrutura de rede, mas volatilidade maior.

---

**#27 — Nexus · Engenheiro de Runtime de Protocolo** — **[VI]**

A empresa se descreve como o motor para finanças verificáveis — uma blockchain projetada para embutir nativamente o sistema financeiro mundial, com sede em San Francisco e presença crescente em Buenos Aires. Responsabilidades: projetar e implementar componentes de alta performance em Rust, C++ ou Go para o motor DEX e o runtime de protocolo da Nexus; construir pipelines de baixa latência para execução de ordens, propagação de eventos e atualizações de estado; otimizar concorrência, escalonamento, layout de memória e caminhos de I/O para determinismo e vazão; contribuir para a evolução de abstrações de execução que podem ser consagradas na camada de protocolo; trabalhar com engenheiros de protocolo para garantir segurança, composabilidade e compatibilidade de consenso. A vaga se abre tanto a um engenheiro pleno forte buscando crescer para propriedade de sistema quanto a um sênior/principal ansioso para arquitetar sistemas distribuídos de alta vazão; para candidatos sênior/principal, o papel envolve conduzir decisões de design de sistema.

Ponto notável: a vaga aceita explicitamente candidatos remotos da Argentina trabalhando com o time de San Francisco — precedente direto para candidatura a partir do Brasil.

🔗 https://web3.career/rust-jobs

---

**#28 — DFINITY / Internet Computer · Rust Developer (remoto)** — **[VI]**

Descrição em português: colaborar no Sistema Nervoso da Rede (NNS); implementar sistemas de governança seguros e descentralizados para gerenciar o Internet Computer; colaborar com outras equipes de desenvolvimento e pesquisa; construir provas da segurança do sistema; contribuir com o sistema simbólico que alimentará o Internet Computer; ajudar a projetar endpoints que permitam operação eficiente; incorporar inteligência ao NNS, permitindo automatizar decisões como despejar nós maliciosos ou coordenar respostas automatizadas a ataques DOS; construir um sistema de programas autônomos para executar no Internet Computer.

🔗 https://talent.bairesdev.com/pt/vagas/rust-developer-remote

---

**#29 — Decentralized Exchange · Rust Engineer (remoto APAC/EU)** — **[LB]**

Publicada em 2 de julho de 2026 na RustJobs.dev, remota para APAC e Europa, faixa de US$ 150.000 a US$ 225.000.

🔗 https://rustjobs.dev/

---

**#30 — Hypery AG (remoto, Brasil) · Desenvolvedor Rust Sênior** — **[LB]**

Listada no Programathor: remoto, startup, acima de R$ 18.000, PJ; stack Blockchain, Rust, Git, API, Continuous Delivery e Continuous Integration.

🔗 https://programathor.com.br/jobs-rust/remoto

---

**#31 — Lakea (remoto, Brasil) · Desenvolvedor Rust Sênior** — **[LB]**

No Programathor: remoto, startup, acima de R$ 18.000, PJ; stack Git, MySQL, Rust.

🔗 https://programathor.com.br/jobs-rust/remoto

---

**#32 — Viseo TI (remoto, Brasil) · Desenvolvedor Rust Pleno** — **[LB]**

Listada no Programathor: remoto, pequena/média empresa, até R$ 10.000, PJ; stack Blockchain, Rust, JavaScript, Python.

🔗 https://programathor.com.br/jobs-rust/remoto

---

**#33 — Sequent · Engenheiro de Infraestrutura de Votação** — **[VI]**

A empresa constrói infraestrutura de votação online criptograficamente segura, usada em mais de 200 eleições reais em múltiplos países; é um time totalmente remoto com plataforma open-source combinando Rust, TypeScript e DevOps moderno. O trabalho envolve votação criptografada ponta a ponta, mixnets criptográficas e logging à prova de adulteração; a stack é Rust, TypeScript/React, WebAssembly, GraphQL, PostgreSQL, Kubernetes, Keycloak e ImmuDB.

🔗 https://hnhiring.com/technologies/rust

---

**#34 — Solana (ecossistema) · Protocol Engineer** — **[RS]**

Programas Solana, runtimes Substrate, contratos NEAR e trabalho com provas de conhecimento zero formam um mundo separado do EVM-Solidity, com seus próprios padrões de teste e armadilhas. Seu roadmap já cobre isso nos tópicos #63 (ZKP) e #95 (Paxos), e cita o Anchor nas referências.

🔗 https://www.kore1.com/rust-developer-staffing/

---

**#35 — Zama · Engenheiro de Criptografia (TFHE)** — **[RS]**

Perfil: criptografia homomórfica totalmente em Rust, otimização de operações sobre dados cifrados. Corresponde ao tópico #89 do seu roadmap, que já cita o `tfhe-rs`.

🔗 https://filtra.io/rust/jobs-report/jan-26

---

### Setor E — IA, ML e infraestrutura de modelos (vagas 36–41)

Bloco mais novo e em crescimento rápido: Rust como camada de serving e tooling em volta de modelos.

---

**#36 — LiteLLM · Rust Engineer** — **[LB]**

Listada na RustJobs.dev em 17 de julho de 2026: híbrido remoto, San Francisco, faixa de US$ 200.000 a US$ 260.000.

A maior faixa salarial nominal de toda esta lista.

🔗 https://rustjobs.dev/

---

**#37 — Symbolica AI · Engenheiro (presencial SF)** — **[LB]**

Anunciada na RustJobs.dev em 24 de novembro de 2025, presencial em San Francisco.

🔗 https://rustjobs.dev/locations/united-states

---

**#38 — Plataforma de assistente de IA · Rust Dev Júnior/Pleno** — **[VI]**

A vaga busca desenvolvedores Rust de nível médio e júnior para uma plataforma inovadora de assistente de IA, pedindo base sólida em Rust, interesse em Large Language Models e cuidado profundo com arquitetura de software e abstrações.

**Esta é a entrada mais importante da lista para você agora.** É uma das pouquíssimas vagas Rust que aceita explicitamente nível júnior, e o que ela pede além de Rust é *interesse em LLMs* e *cuidado com arquitetura e abstrações* — não cinco anos de produção.

🔗 https://www.rustjobs.com/jobs.html

---

**#39 — Nvidia · Engenheiro de Software (Rust)** — **[RS]**

A Nvidia aparece entre as empresas postando mais de 20 posições em Rust por mês. Perfil: tooling de GPU, drivers, camadas de runtime.

🔗 https://filtra.io/rust/jobs-report/oct-25

---

**#40 — Avra (Brasil) · Staff Software Engineer** — **[LB]**

Listada no Indeed Brasil: a empresa está construindo modelos fundacionais relacionais para tomada de decisão empresarial no Brasil, modelando empresas, pessoas e as relações entre elas; vaga em São Paulo.

🔗 https://br.indeed.com/q-rust-vagas.html

---

**#41 — Botcity (remoto, Brasil) · Desenvolvedor Sênior** — **[LB]**

No Programathor: remoto, startup, sênior, PJ; stack Python, Rust, SQL, Docker.

Automação como produto — encaixa com o que você disse sobre gostar de produzir algo automático.

🔗 https://programathor.com.br/jobs-rust/remoto

---

### Setor F — Fintech, HFT e sistemas financeiros (vagas 42–46)

Onde latência determinista vale dinheiro literal. Requisito quase universal: nada de ponto flutuante para dinheiro, nada de GC, nada de alocação no caminho quente.

---

**#42 — Lithic · Rust Engineer (remoto EUA)** — **[LB]**

Listada na RustJobs.dev em 19 de dezembro de 2025: remoto nos EUA, faixa de US$ 160.000 a US$ 190.000.

🔗 https://rustjobs.dev/locations/united-states

---

**#43 — Surya Financial Technologies · Rust Engineer** — **[LB]**

Vaga de 16 de julho de 2026 na RustJobs.dev, em regime híbrido remoto em Bangalore, Índia.

🔗 https://rustjobs.dev/

---

**#44 — Quantitative Developer (Nova York)** — **[VI]**

Vaga em uma firma de rápido crescimento: desenvolver e implementar modelos quantitativos usando C++ e Rust.

🔗 https://www.ziprecruiter.com/Jobs/Rust-Developer

---

**#45 — Magnetis (Brasil) · Engenheiro de Software Sênior/Especialista** — **[LB]**

Listada no Indeed Brasil: busca pessoa desenvolvedora sênior ou especialista para atuar em soluções de meio de pagamento, participando do desenvolvimento; vaga em São Paulo.

🔗 https://br.indeed.com/q-rust-vagas.html

---

**#46 — XP Inc. (Brasil) · Desenvolvedor Pleno (remoto)** — **[LB]**

Listada no Indeed Brasil entre as vagas associadas a Rust; a XP é descrita como uma das maiores instituições financeiras independentes do Brasil, com mais de 4,6 milhões de clientes ativos e mais de R$ 1,1 trilhão em ativos sob custódia.

🔗 https://br.indeed.com/q-programador-rust-vagas.html

---

### Setor G — Sistemas críticos, aeroespacial e defesa (vagas 47–48)

Poucas vagas, altíssima barreira, e o único setor onde diploma e certificação pesam mais que GitHub.

---

**#47 — Atech (Brasil) · Desenvolvedor de Software Júnior/Pleno — Backend com foco em C e Rust** — **[VI]**

A empresa atua com sistemas críticos para controle de tráfego aéreo, em parceria com a Força Aérea Brasileira; a vaga é em São Paulo e pede entender requisitos especificados para o projeto. Outra vaga da mesma empresa, de nível pleno/sênior com foco em arquitetura de software, exige conhecimento profundo de programação concorrente: threads, mutexes, operações atômicas, padrões async e tuning de performance.

**Esta é a vaga mais relevante deste documento para o seu caso concreto.** É brasileira, é de nível júnior/pleno, o título diz literalmente "foco em C e Rust", e C é a linguagem das duas disciplinas em que você é monitor. A exigência de concorrência (threads, mutexes, atômicos) corresponde diretamente ao tópico #9/#10 do seu roadmap.

🔗 https://br.indeed.com/q-desenvolvedor-rust-vagas.html

---

**#48 — General Dynamics · Software Engineer (Rust embarcado)** — **[VI]**

Requisitos básicos: bacharelado em Engenharia de Software ou área correlata de Ciência, Engenharia, Tecnologia ou Matemática; 2+ anos de experiência relacionada, ou mestrado e 6 meses de experiência; experiência com Agile preferencial; exige credenciamento de segurança SECRET do Departamento de Defesa dos EUA no momento da contratação.

Incluída como contraexemplo útil: é uma vaga estruturalmente fechada para quem não é cidadão americano. Vale conhecer o padrão para não perder tempo com esse ramo.

🔗 https://www.ziprecruiter.com/Jobs/Rust-Embedded/-in-New-York-City,NY

---

### Setor H — Produto, consultoria e generalistas (vagas 49–50)

---

**#49 — Vividly · Rust Engineer** — **[VI]**

A vaga busca um engenheiro Rust dinâmico e versátil para liderar a construção e manutenção de componentes em Rust críticos para o sucesso da plataforma de TPM da empresa, com papel central nas decisões de engenharia como um dos primeiros engenheiros.

🔗 https://www.rustjobs.com/jobs.html

---

**#50 — Yalantis · Rust Developer** — **[VI]**

Descrita como uma das empresas mais ativas em 2026 na contratação de desenvolvedores Rust experientes para backend complexo, IoT e sistemas de alta performance, com experiência em saúde, fintech, logística, telecom e IoT industrial; o time é reconhecido por conhecimento profundo de arquitetura de sistemas, desenvolvimento de API, engenharia de firmware e plataformas cloud, e oferece modelos flexíveis de cooperação, de extensão de time à criação de squads especializados em Rust.

🔗 https://www.onrec.com/news/news-archive/top-companies-actively-hiring-rust-developers-in-2026

---

## 6. Síntese: o que se repete nas 50

### 6.1 Frequência aproximada por requisito

Contagem sobre as 50 entradas, considerando requisito explícito ou perfil documentado do setor:

| Requisito | Ocorrências | Comentário |
| --- | --- | --- |
| **Concorrência (threads, async, atômicos, Tokio)** | ~42 | O único requisito quase universal |
| **Experiência prévia entregando em produção** | ~38 | A barreira real, mais que qualquer tópico técnico |
| **Linux e ferramental de terminal** | ~35 | Pressuposto, quase nunca listado — só falta quando falta |
| **C ou C++ ao lado de Rust** | ~28 | Rust raramente é a única linguagem da vaga |
| **Sistemas distribuídos / rede** | ~24 | TCP, proxies, protocolos, latência de cauda |
| **Observabilidade (métricas, logs, tracing)** | ~20 | Requisito de operação, não de desenvolvimento |
| **Postgres ou banco relacional** | ~18 | Mesmo em vagas de sistemas |
| **CI/CD e teste automatizado** | ~17 | |
| **`unsafe` / FFI justificado** | ~14 | Sempre com a palavra "justificável" ou "auditado" |
| **WebAssembly** | ~11 | Borda, plugins, sandbox |
| **Criptografia aplicada** | ~10 | TLS, PKI, HSM, assinatura |
| **Parsing binário / engenharia reversa** | ~3 | **O norte do seu roadmap** |
| **Mojo** | 0 | Não apareceu em nenhuma das 50 |
| **Tecnologia 3D (glTF, PBR, skinning)** | 0 | Não apareceu em nenhuma das 50 |

### 6.2 As cinco leituras que importam

**Leitura 1 — concorrência é o requisito, não ownership.** Ownership e borrow checker são pressupostos: ninguém lista "sabe usar `&mut`". O que aparece escrito nas vagas é threads, mutexes, atômicos, async, tuning. A vaga da Atech diz isso com todas as letras. O seu roadmap trata concorrência como um tópico entre cem (#9/#10); o mercado trata como *o* tópico.

**Leitura 2 — Rust quase nunca vem sozinho.** Das 50, a esmagadora maioria pede Rust *e* outra coisa: C, C++, Go, TypeScript, Python. A Atech pede C e Rust. A Cloudflare pede Rust, TypeScript ou Go. A Nexus aceita Rust, C++ ou Go. Sua base em C (que você ensina) não é um passado a ser superado — é metade do requisito.

**Leitura 3 — o portfólio é o filtro, e isso é bom para você.** Como o mercado é hostil a júnior por currículo, mas mede por código público, um estudante com repositórios sérios compete melhor em Rust do que em qualquer outra linguagem. A seção "Comprovação de Senioridade" do seu roadmap está certa — só precisa valer para todo o documento, não só para a trilha maluca.

**Leitura 4 — dois requisitos do seu roadmap não têm lastro no mercado amplo.** Mojo e tecnologia 3D aparecem zero vezes nas 50. Mojo especificamente: o seu roadmap chama de "diferencial de altíssimo peso", com quatro tópicos dedicados (#M19–#M22, 120–240h). Isso é uma aposta na PANIK, não uma leitura de mercado. Vale manter, mas rotulado como aposta.

**Leitura 5 — o Brasil tem porta de entrada, e ela é diferente da que o roadmap prevê.** As vagas brasileiras acessíveis são: sistemas críticos (Atech), blockchain remoto (Hypery, Lakea, Viseo), automação (Botcity) e edge (Azion). Nenhuma delas pede Ghidra ou IDA Pro. Todas pedem concorrência, backend e Linux.

---

## 7. Projetos de hobby recomendados

Cinco projetos, ordenados por relação esforço/retorno no mercado. Cada um mapeia para vagas específicas desta lista e para tópicos do seu roadmap.

### Projeto 1 — Proxy TCP com observabilidade (prioridade máxima)

**Cobre as vagas:** #1, #2, #6, #7, #47
**Tópicos do roadmap:** #1, #7, #8, #9, #10, #28, #39
**Esforço:** 40–70h

Um proxy TCP em Tokio que fica entre cliente e servidor, encaminha conexões e expõe métricas: conexões ativas, bytes trafegados, latência por percentil, conexões derrubadas.

Escopo progressivo:

1. Encaminhamento TCP simples, uma conexão por task
2. Limite de conexões simultâneas e backpressure
3. Métricas com `tracing` + endpoint Prometheus
4. Roteamento por regra (porta de destino conforme padrão)
5. Injeção de falha: derrubar X% das conexões, adicionar latência artificial
6. Benchmark comparando com `nginx` no mesmo teste

**Por que este primeiro.** Ele produz, num só repositório, evidência de: async/Tokio, concorrência real, observabilidade, redes em nível de socket e medição de performance — que são os cinco requisitos mais frequentes das 50. E é a interseção exata entre o que você gosta (configuração de rede, Mikrotik, processos para rastrear) e o que o mercado paga.

**O diferencial que quase ninguém faz:** documente no README o que aconteceu quando você aumentou as conexões simultâneas — onde quebrou, qual foi o gargalo, o que mudou. Isso é "decisões de engenharia documentadas", que a sua própria seção de senioridade cita.

---

### Projeto 2 — Parser de formato binário com fuzzing

**Cobre as vagas:** #20, #22, #33, e o perfil PANIK
**Tópicos do roadmap:** #11, #15, #23, #M1, #M6, #M9
**Esforço:** 50–90h

Escolha um formato binário documentado e escreva o parser do zero, sem crate pronto de alto nível. Boas escolhas, em ordem de dificuldade:

| Formato | Dificuldade | Por que é bom |
| --- | --- | --- |
| **PNG** | Média | Chunks, CRC, zlib, especificação curta e clara |
| **WAV/RIFF** | Baixa | Chunks aninhados, endianness |
| **ELF** | Média-alta | Headers, seções, tabelas de símbolos — é o formato do Linux |
| **classfile Java** | Média | Você ensina Java; constant pool é um ótimo exercício de índices |

A parte que dá o valor não é o parser funcionar com arquivo válido. É:

1. Todo erro de entrada vira `Result`, nunca `panic`, nunca OOM, nunca laço infinito
2. `cargo-fuzz` rodando no CI
3. Um `corpus/` com casos truncados, offsets inválidos, tamanhos mentirosos
4. Um `SECURITY.md` listando as classes de ataque tratadas

**Sugestão forte:** faça o **classfile Java**. Você é monitor de POO em Java; um parser de `.class` que imprime o constant pool e desmonta bytecode é útil para os seus alunos *e* é exatamente o artefato que a vaga #22 (análise estática de APKs) descreve.

---

### Projeto 3 — Mini-engine ECS com loop determinista

**Cobre as vagas:** #14, #15, #50 (e o seu GameLab)
**Tópicos do roadmap:** #41, #56, #M11
**Esforço:** 60–100h

Não é um jogo: é a engine por baixo. Storage de componentes, scheduler de sistemas, loop de tempo fixo, serialização de estado.

Requisito que transforma o projeto: **determinismo**. Mesma seed + mesma sequência de inputs = mesmo estado final, byte a byte. Prove isso com um teste que roda 10.000 ticks e compara o hash do estado.

**Por que isso importa.** Determinismo é o requisito central de netcode (tópico #65 do roadmap), de replays, e — o mesmo conceito, outro setor — da vaga #27 da Nexus, que pede otimização "para determinismo e vazão". É o ponto onde o seu hobby de game dev e o mercado de sistemas se encostam. E é teoria de autômato rodando, que é a única forma de autômato que você tolera.

---

### Projeto 4 — Agente de telemetria embarcado

**Cobre as vagas:** #10, #13, #15, #18, #19, #26
**Tópicos do roadmap:** #45, #47, #34
**Esforço:** 50–90h
**Custo de hardware:** ESP32-S3, entre R$ 40 e R$ 80

Firmware em Rust `no_std` num ESP32 que lê um sensor, agrega localmente e publica por rede, com um daemon em Rust `std` do outro lado recebendo e armazenando.

Escopo:

1. `no_std` + `esp-hal`, piscar LED, ler GPIO
2. Ler sensor por I2C
3. Buffer circular local com política de descarte quando enche
4. WiFi + publicação MQTT ou HTTP
5. Daemon receptor gravando em SQLite
6. Comportamento sob queda de rede: enfileira, não perde, não estoura memória

**Por que este.** É o setor que mais cresce (seção 4.1), tem o menor custo de entrada em hardware, e é raríssimo em portfólio de estudante brasileiro. Além disso o seu roadmap já recomenda ESP32-S3 antes de STM32 — aqui é só executar o que já está escrito.

---

### Projeto 5 — CLI de inspeção de rede

**Cobre as vagas:** #1, #2, #7, #47
**Tópicos do roadmap:** #1, #5, #6, #12, #M16
**Esforço:** 25–45h

Uma ferramenta de terminal que faz varredura de portas, resolve DNS, mede latência e exporta em JSON/tabela/CSV.

É o projeto mais fácil da lista e serve de aquecimento para o #1. Faça primeiro se quiser uma vitória rápida antes do proxy.

**Cuidado necessário:** varredura de portas é técnica legítima de administração de rede e também de reconhecimento ofensivo. Restrinja a ferramenta à sua própria rede, deixe isso explícito no README, e não inclua nada que contorne proteção. Ferramenta de diagnóstico de rede bem documentada abre portas; ferramentamenta ambígua fecha.

---

### Ordem sugerida

```
Projeto 5 (aquecimento, 1 mês)
  ↓
Projeto 1 (o carro-chefe, 2 meses)
  ↓
Projeto 2 (profundidade, 2–3 meses)
  ↓
Projeto 4 ou 3 (conforme o setor que te atrair)
```

Quatro projetos bem feitos, com README explicando decisões, valem mais que os 32 repositórios atuais. Consolidar vale mais que acumular.

---

## 8. Recomendações de atualização do roadmap

Onze mudanças, em ordem de urgência.

### Urgente — corrigir o que está quebrado

**R1. Unificar a numeração entre `README.md` e `roadmap_rust_supremo.md`.**
Escolha uma das duas numerações como canônica e reescreva a outra. Enquanto isso não for feito, as 20 trilhas apontam para tópicos errados. É o bug mais grave do repositório.

**R2. Marcar explicitamente os 80 tópicos sem conteúdo.**
Substitua a linha *"(Níveis 3 e 4 mantidos conforme original)"* por um aviso claro: quais tópicos têm conteúdo e quais são apenas título. Hoje um leitor clica em #61 e encontra vazio sem aviso prévio.

**R3. Resolver a contradição sobre o Mojo.**
Uma seção diz "ainda não é open-source (previsão 2026)", a outra cita o repositório "desde ago/2026". Verifique o status atual e deixe uma versão só.

**R4. Renomear "Rust no Mercado em 2025".**
Atualize ou marque a data dos dados. Um documento de 2026 com seção de 2025 sem rótulo passa impressão de abandono — justo o oposto do que é verdade.

### Importante — corrigir o enquadramento

**R5. Substituir o norte único por quatro nortes.**
Em vez de calibrar o documento inteiro pela PANIK, crie quatro seções de "norte", cada uma com sua trilha e suas vagas de referência:

| Norte | Trilha base | Vagas de referência desta lista |
| --- | --- | --- |
| Infra de rede e edge | Sistemas/Baixo Nível | #1, #2, #6, #7 |
| IoT e embarcados | Robótica/IoT | #10, #11, #15, #18 |
| Engines de dados | Engenharia de Dados | #20, #22, #23 |
| Parsing e reverse (atual) | Sênior/Maluco | #22, #33 + PANIK |

**R6. Promover concorrência a pré-requisito transversal.**
Concorrência aparece em ~42 das 50 vagas. No roadmap ela é o tópico #9 ou #10 conforme o arquivo. Mova para junto dos "Conceitos Fundamentais" — a tabela onde já estão ownership e borrowing.

**R7. Rebaixar Mojo e 3D a "apostas".**
Ambos aparecem zero vezes nas 50. Não remova — crie uma seção "Apostas de alto risco/alto retorno" e mova os dois para lá, com o motivo escrito. Assim o leitor sabe que está apostando, não seguindo o mercado.

**R8. Trocar o total de 8.337h por um marco de 6 meses.**
O número grande no topo é desmotivador e, pelo seu próprio texto, irreal. Substitua por: *"Primeiro marco: 150h → proxy TCP funcionando com métricas → apto a se candidatar a vagas júnior/pleno em backend Rust."* Concreto, atingível, verificável.

### Complementar — adicionar o que falta

**R9. Criar `VAGAS.md` no repositório.**
Este documento pode virar esse arquivo. Um roadmap de carreira sem lista de destinos é um mapa sem cidades.

**R10. Adicionar um tópico sobre portfólio.**
Seu documento diz que currículo não basta e que o GitHub decide, mas não ensina a fazer o GitHub. Falta um tópico sobre: o que escrever no README, como documentar decisões de engenharia, como mostrar benchmark, como estruturar workspace público. É a habilidade mais rentável do documento inteiro e a única que não está lá.

**R11. Marcar a data de atualização por seção.**
Como o documento se declara "vivo" e não versionado, uma linha `_Atualizado em: AAAA-MM-DD_` no fim de cada seção grande resolve o problema de saber o que é recente sem precisar de versionamento no nome do arquivo.

---

## 9. Fontes consultadas

Todas acessadas em 18 de setembro de 2026.

### Repositório analisado

| Fonte | URL |
| --- | --- |
| roadmap-rust (README) | https://github.com/Benjamin-Yuji-Suzuki/roadmap-rust |
| roadmap_rust_supremo.md | https://github.com/Benjamin-Yuji-Suzuki/roadmap-rust/blob/main/roadmap_rust_supremo.md |
| Perfil GitHub | https://github.com/Benjamin-Yuji-Suzuki |

### Boards e agregadores de vagas

| Fonte | URL |
| --- | --- |
| RustJobs.dev | https://rustjobs.dev/ |
| RustJobs.dev — Estados Unidos | https://rustjobs.dev/locations/united-states |
| RustJobs.dev — Remoto | https://rustjobs.dev/locations/remote |
| RustJobs.com | https://www.rustjobs.com/jobs.html |
| HNHiring — Rust | https://hnhiring.com/technologies/rust |
| web3.career — Rust jobs | https://web3.career/rust-jobs |
| DevJobsScanner — Rust | https://www.devjobsscanner.com/rust-jobs/ |
| Cloudflare Greenhouse — R2 Gateway | https://job-boards.greenhouse.io/cloudflare/jobs/8155463 |
| BuiltIn Austin — Cloudflare | https://www.builtinaustin.com/job/software-engineer-distributed-systems-go-andor-rust/3288751 |
| freehire — Nanobiosym | https://freehire.me/jobs/engineer-sr-embedded-firmware-engineer-rust-and-c-nanobiosym-sxtzcxhh |

### Brasil

| Fonte | URL |
| --- | --- |
| Indeed Brasil — Desenvolvedor Rust | https://br.indeed.com/q-desenvolvedor-rust-vagas.html |
| Indeed Brasil — Programador Rust | https://br.indeed.com/q-programador-rust-vagas.html |
| Indeed Brasil — Rust | https://br.indeed.com/q-rust-vagas.html |
| Programathor — Rust remoto | https://programathor.com.br/jobs-rust/remoto |
| Programathor — Rust Júnior | https://programathor.com.br/jobs/10634-desenvolvedor-a-rust-junior |
| Glassdoor Brasil — Rust | https://www.glassdoor.com.br/Vaga/rust-vagas-SRCH_KO0,4.htm |
| Glassdoor Brasil — Rust Developer | https://www.glassdoor.com.br/Vaga/rust-developer-vagas-SRCH_KO0,14.htm |
| BairesDev — Rust remoto | https://talent.bairesdev.com/pt/vagas/rust-developer-remote |
| Rust Brasil — Vagas | https://rustlang.com.br/vagas/ |

### Relatórios e dados de mercado

| Fonte | URL |
| --- | --- |
| filtra.io — Rust Jobs Report jan/2026 | https://filtra.io/rust/jobs-report/jan-26 |
| filtra.io — Rust Jobs Report out/2025 | https://filtra.io/rust/jobs-report/oct-25 |
| filtra.io — Rust Jobs Report out/2024 | https://filtra.io/rust/jobs-report/oct-24 |
| filtra.io — Rust Jobs Report fev/2024 | https://filtra.io/rust/jobs-report/feb-24 |
| filtra.io — Rust Jobs Report jan/2024 | https://filtra.io/rust/jobs-report/jan-24 |
| filtra.io — Índice de relatórios | https://filtra.io/rust |
| RustJobs.dev — Guia salarial 2026 | https://rustjobs.dev/salary-guide |
| ITJobsWatch — Rust (Reino Unido) | https://www.itjobswatch.co.uk/jobs/uk/rust.do |
| ZipRecruiter — Rust Developer | https://www.ziprecruiter.com/Jobs/Rust-Developer |
| ZipRecruiter — Rust Embedded | https://www.ziprecruiter.com/Jobs/Rust-Embedded |
| ZipRecruiter — Rust Embedded Microcontroller | https://www.ziprecruiter.com/Jobs/Rust-Embedded-Microcontroller |
| ZipRecruiter — Rust Embedded NYC | https://www.ziprecruiter.com/Jobs/Rust-Embedded/-in-New-York-City,NY |
| Glassdoor — Embedded Firmware Engineer | https://www.glassdoor.com/Job/embedded-firmware-engineer-jobs-SRCH_IS11047_KO0,26.htm |
| KORE1 — Rust Developer Staffing | https://www.kore1.com/rust-developer-staffing/ |
| Onrec — Top Companies Hiring Rust 2026 | https://www.onrec.com/news/news-archive/top-companies-actively-hiring-rust-developers-in-2026 |
| Indeed — Cloudflare Rust Jobs | https://www.indeed.com/q-cloudflare-rust-jobs.html |
| Indeed — Rust Embedded Microcontroller | https://www.indeed.com/q-rust-embedded-microcontroller-jobs.html |

### Documentação técnica citada

| Fonte | URL |
| --- | --- |
| Ferrous Systems — Embedded Rust on Espressif | https://ferrous-systems.com/blog/announce-esp-training/ |
| Espressif — Embedded Rust (no_std) | https://docs.espressif.com/projects/rust/no_std-training/ |
| Cloudflare Workers — Rust | https://developers.cloudflare.com/workers/languages/rust/ |

---

_Documento gerado em 18 de setembro de 2026. Dados de vagas refletem o estado das fontes nessa data._
