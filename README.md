# Build Your Own Lab

![License: MIT](https://img.shields.io/badge/license-MIT-2f6f9f.svg)
![Learning by building](https://img.shields.io/badge/format-hands--on%20learning-6a8f6e.svg)

**A practical field guide to understanding software by rebuilding its essential parts.**

Build Your Own Lab turns big systems into approachable projects. Pick a track, make a small version that works, and grow it one deliberate step at a time. The goal is understanding how the pieces fit together—not shipping a production replacement.

[Browse the projects](#project-map) · [Choose a path](#learning-paths) · [Contribute a resource](#contributing)

---

## Start with a path

| If you want to… | Start here | Then try |
| --- | --- | --- |
| Get comfortable building from a spec | JSON parser | Markdown renderer → expression interpreter |
| Learn how everyday developer tools work | CLI utility | shell → Git object store |
| Understand the web below the framework layer | HTTP server | DNS resolver → reverse proxy |
| Explore how data is stored and found | key-value store | SQL query engine → search index |
| See machine learning from the inside | scalar autodiff | tiny neural network → tokenizer |
| Build something visual | ray tracer | rasterizer → small game engine |
| Learn low-level systems | CHIP-8 emulator | memory allocator → toy kernel |
| Study coordination across machines | message queue | replicated log → Raft consensus |

**New to the topic?** Keep the first version deliberately small. One request, one file format, one instruction, or one query is enough to make the core idea visible.

## Project map

Each brief describes a useful first milestone. The linked material is a starting point; adapt the scope to your language and experience.

### Foundations and language tools

- **JSON parser** · *Starter* — Read a string, recognize JSON values, and report where malformed input fails. Begin with the [JSON specification (RFC 8259)](https://www.rfc-editor.org/rfc/rfc8259).
- **Markdown renderer** · *Starter* — Convert a small, clearly defined subset of Markdown into HTML. Use the [CommonMark specification](https://spec.commonmark.org/) to understand the edge cases.
- **Regular expression engine** · *Intermediate* — Match literals and concatenation first, then add alternation and repetition. [Russ Cox's implementation notes](https://swtch.com/~rsc/regexp/regexp1.html) explain a compact approach.
- **Expression interpreter** · *Intermediate* — Turn source text into tokens, parse expressions, and evaluate them. [Crafting Interpreters](https://craftinginterpreters.com/) walks through the stages.
- **Bytecode virtual machine** · *Advanced* — Compile expressions to instructions and execute them on a stack. Continue with [Crafting Interpreters' VM chapter](https://craftinginterpreters.com/a-virtual-machine.html).

### Developer tools

- **Command-line utility** · *Starter* — Build one focused tool with arguments, helpful errors, and predictable output. The [Rust CLI book](https://rust-cli.github.io/book/) covers a complete command-line workflow.
- **Shell** · *Intermediate* — Parse commands, launch processes, and connect their input and output with pipes. The [POSIX shell language reference](https://pubs.opengroup.org/onlinepubs/9799919799/utilities/V3_chap02.html) defines the behavior to study.
- **Git object store** · *Intermediate* — Store content by hash, create trees and commits, and inspect a short history. The [Git book](https://git-scm.com/book/en/v2) and [Git reference](https://git-scm.com/docs) provide the format and command details.
- **Terminal text editor** · *Intermediate* — Add cursor movement, insertion, deletion, and save/load behavior. [Build Your Own Text Editor](https://viewsourcecode.org/snaptoken/kilo/) is a hands-on guide.
- **Container sandbox** · *Advanced* — Run a process with an isolated view of resources and files. Learn the building blocks from the Linux documentation on [namespaces](https://man7.org/linux/man-pages/man7/namespaces.7.html) and [cgroup v2](https://docs.kernel.org/admin-guide/cgroup-v2.html).
- **Build tool** · *Intermediate* — Track dependencies and rebuild only the outputs affected by changed inputs. The [GNU Make manual](https://www.gnu.org/software/make/manual/) is a useful reference.

### Web and network protocols

- **HTTP server** · *Starter* — Accept a connection, parse one request, and return a valid response. Start with [MDN's HTTP overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview) and [RFC 9110](https://www.rfc-editor.org/rfc/rfc9110).
- **DNS resolver** · *Intermediate* — Encode a query, send it to a resolver, and decode the answer. The message format is described in [RFC 1035](https://www.rfc-editor.org/rfc/rfc1035).
- **Reverse proxy** · *Intermediate* — Forward requests to an upstream server and handle timeouts and failures. [MDN's proxy guide](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling) introduces the concepts.
- **WebSocket endpoint** · *Intermediate* — Perform the HTTP upgrade and exchange framed messages. Refer to [RFC 6455](https://www.rfc-editor.org/rfc/rfc6455).
- **BitTorrent peer** · *Advanced* — Parse metainfo, discover peers, and transfer a piece of a file. The protocol's core is specified in [BEP 3](https://www.bittorrent.org/beps/bep_0003.html).
- **TCP networking exercises** · *Intermediate* — Build a client and server, then observe connection setup and data exchange. [Beej's networking guide](https://beej.us/guide/bgnet/) is a practical companion.

### Data, search, and distributed systems

- **Key-value store** · *Starter* — Persist key/value pairs, recover after restart, and add an index. [SQLite's architecture notes](https://www.sqlite.org/arch.html) offer design context.
- **SQL query engine** · *Intermediate* — Support a small query language over a few tables and make errors understandable. [How SQLite works](https://www.sqlite.org/howitworks.html) describes a mature implementation.
- **Cache with eviction** · *Starter* — Add an LRU policy and measure how workload changes affect hit rate. Compare your behavior with [Redis eviction policies](https://redis.io/docs/latest/develop/reference/eviction/).
- **Search index** · *Intermediate* — Tokenize documents, build an inverted index, and rank a result set. The [Stanford Information Retrieval book](https://nlp.stanford.edu/IR-book/) covers the foundations.
- **Message queue** · *Intermediate* — Append messages, let consumers acknowledge work, and recover unprocessed items. The [RabbitMQ tutorials](https://www.rabbitmq.com/tutorials) demonstrate common queue patterns.
- **Replicated log** · *Advanced* — Keep ordered entries consistent across nodes despite leader changes. The [Raft paper and visualizer](https://raft.github.io/) make consensus easier to explore.
- **MapReduce runner** · *Advanced* — Split a batch job into map and reduce phases and combine the results. Read Google's [MapReduce paper](https://research.google/pubs/mapreduce-simplified-data-processing-on-large-clusters/).
- **Event stream** · *Advanced* — Store an append-only sequence and let consumers resume from offsets. Kafka's [design documentation](https://kafka.apache.org/documentation/#design) explains the model.

### AI and machine learning

- **Automatic differentiation** · *Starter* — Record scalar operations in a graph and calculate gradients with the chain rule. [micrograd](https://github.com/karpathy/micrograd) is a compact reference implementation.
- **Small neural network** · *Intermediate* — Train a tiny model on a toy dataset and inspect each forward and backward pass. Follow [Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html).
- **Tokenizer** · *Intermediate* — Split text into model tokens and inspect how the vocabulary changes the result. The [GPT-2 encoder](https://github.com/openai/gpt-2/blob/master/src/encoder.py) is one concrete reference.
- **Vector search** · *Advanced* — Compare embedding vectors, measure nearest-neighbor quality, and explore approximate indexes. See the [Faiss documentation](https://faiss.ai/).
- **Document question answering** · *Advanced* — Retrieve relevant passages before composing an answer. [RAG from Scratch](https://github.com/langchain-ai/rag-from-scratch) breaks the pipeline into components.
- **Image generation concepts** · *Advanced* — Work through denoising steps and inspect how a diffusion model transforms noise. Use the [Hugging Face diffusion course](https://huggingface.co/learn/diffusion-course/en/unit1/3) as a guide.

### Graphics, interaction, and games

- **Ray tracer** · *Starter* — Render spheres, cast rays, and add simple materials. [Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html) provides a gradual path.
- **Software rasterizer** · *Intermediate* — Draw triangles into a pixel buffer and add depth and shading. [TinyRenderer](https://github.com/ssloy/tinyrenderer/wiki) explains the pipeline.
- **Browser layout engine** · *Advanced* — Parse a small markup subset, compute boxes, and paint a page. [Browser Engineering](https://browser.engineering/) is a practical textbook.
- **Frontend renderer** · *Intermediate* — Build a component tree, update state, and reconcile changes into a small DOM. [Build Your Own React](https://pomb.us/build-your-own-react/) is a focused walkthrough.
- **2D game** · *Starter* — Implement a game loop, input, collisions, and a win condition. MDN's [Breakout tutorial](https://developer.mozilla.org/en-US/docs/Games/Tutorials/2D_breakout_game_Phaser) is a browser-based start.
- **Physics sandbox** · *Advanced* — Simulate bodies, detect collisions, and apply simple impulses. Compare your design with the [Box2D documentation](https://box2d.org/documentation/).
- **Voxel world** · *Advanced* — Represent a block world and render only the visible surfaces. The [Let's Make a Voxel Engine series](https://sites.google.com/site/letsmakeavoxelengine/home) shows one approach.
- **Augmented reality scene** · *Intermediate* — Place a virtual object into a camera view and track its position. [AR with Python and OpenCV](https://bitesofcode.wordpress.com/2017/09/12/augmented-reality-with-python-and-opencv-part-1/) is one entry point.

### Operating systems and hardware

- **CHIP-8 emulator** · *Starter* — Decode a small instruction set and update registers, memory, and a display. This [CHIP-8 guide](https://tobiasvl.github.io/blog/write-a-chip-8-emulator/) outlines the system.
- **Memory allocator** · *Intermediate* — Manage a fixed region, split free blocks, and investigate fragmentation. Use [glibc allocator internals](https://sourceware.org/glibc/wiki/MallocInternals) for comparison.
- **Toy filesystem** · *Advanced* — Store directory entries and file contents in a disk image. [The Little Book About OS Development](https://littleosbook.github.io/) introduces low-level design ideas.
- **Tiny kernel** · *Advanced* — Boot a kernel, print output, and add one basic scheduling mechanism. The [OSDev Wiki](https://wiki.osdev.org/Main_Page) and [xv6 book](https://pdos.csail.mit.edu/6.828/2024/xv6/book-riscv-rev4.pdf) are references.
- **Processor model** · *Advanced* — Implement a small instruction set and observe how state changes instruction by instruction. [From NAND to Tetris](https://www.nand2tetris.org/) builds computer systems from first principles.

## A repeatable build loop

1. **Set a boundary.** Write down exactly what the first version supports.
2. **Study the contract.** Read a specification or guide and note the input/output rules.
3. **Build one vertical slice.** Make one realistic example work end to end.
4. **Probe the edges.** Add malformed input, failure cases, and a regression check.
5. **Explain the trade-offs.** Record what you simplified and what would be needed for a real system.

Keep the project small enough to finish. A constrained implementation that you understand is more valuable than a broad clone assembled from unexplained pieces.

## Resource selection

Projects are included when a learner can make progress from a public guide, standard, or reference implementation. The list favors material that explains the underlying idea, offers a practical sequence, and can be used without copying another project's prose or code into this repository. Difficulty labels are approximate; prerequisites vary by language.

## Contributing

Suggest a project or a better learning resource through [GitHub Issues](https://github.com/puffxhost/build-your-own-lab/issues) or a pull request. Please include:

- the project and the milestone it helps a learner reach;
- a direct link to the guide, standard, or reference;
- language and prerequisite information when known;
- any access, maintenance, or licensing caveats.

Keep descriptions in your own words, check for an existing entry, and avoid promotional claims. See [CONTRIBUTING.md](CONTRIBUTING.md) before submitting.

## Acknowledgements and licensing

This edition uses its own organization, learning paths, project briefs, and selection of resources. The initial breadth of topics was informed by [Build Your Own X](https://github.com/codecrafters-io/build-your-own-x), a community collection released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Thanks to its contributors for making that starting point available. This repository is independent and is not affiliated with CodeCrafters.

Original material written for Build Your Own Lab is released under the [MIT License](LICENSE). External tutorials, specifications, and projects remain the property of their respective authors and under their stated terms.

