# Build Your Own Lab

> Learn how the tools you use every day work by building small versions of them yourself.

A community-curated collection of practical, step-by-step guides and references for recreating software systems from scratch. Pick one project, build a tiny working version, and learn by experimenting.

This is an independent learning list maintained by [PuffxHost](https://github.com/puffxhost). It is inspired by the broad idea of learning through reimplementation and is not affiliated with or endorsed by CodeCrafters.

## Contents

- [How to use this list](#how-to-use-this-list)
- [Projects](#projects)
  - [Web servers and networking](#web-servers-and-networking)
  - [Languages and interpreters](#languages-and-interpreters)
  - [Developer tools](#developer-tools)
  - [Data and search](#data-and-search)
  - [Operating systems and hardware](#operating-systems-and-hardware)
  - [AI and machine learning](#ai-and-machine-learning)
  - [Graphics and games](#graphics-and-games)
  - [Distributed systems](#distributed-systems)
- [Learning references](#learning-references)
- [Contributing](#contributing)
- [License and attribution](#license-and-attribution)

## How to use this list

1. Choose a project that interests you.
2. Read the guide once, then close it and implement the smallest useful version.
3. Keep notes about what surprised you and what you would change.
4. Add tests and compare your implementation with the protocol or format specification.

Most entries link to independently maintained tutorials, specifications, or source repositories. Check each resource's license and terms before reusing its text or code. This list does not claim ownership of linked material.

## Projects

### Web servers and networking

- **HTTP server** — Handle a request, parse a few headers, and return a response. [MDN: HTTP overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview) · [RFC 9110](https://www.rfc-editor.org/rfc/rfc9110)
- **DNS resolver** — Build DNS queries and decode responses. [RFC 1035](https://www.rfc-editor.org/rfc/rfc1035)
- **TCP/IP stack** — Explore Ethernet, IP, TCP, and sockets. [RFC 9293: TCP](https://www.rfc-editor.org/rfc/rfc9293) · [Beej's Guide to Network Programming](https://beej.us/guide/bgnet/)
- **WebSocket chat server** — Implement the upgrade handshake and framed messages. [RFC 6455](https://www.rfc-editor.org/rfc/rfc6455)
- **BitTorrent client** — Parse a torrent file, contact trackers, and exchange pieces. [BEP 3](https://www.bittorrent.org/beps/bep_0003.html)
- **Proxy server** — Forward HTTP requests and learn about connection handling. [MDN: Proxy servers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling)

### Languages and interpreters

- **Programming language interpreter** — Tokenize expressions, parse them, and evaluate an AST. [Crafting Interpreters](https://craftinginterpreters.com/)
- **Bytecode virtual machine** — Add a compiler and a small stack-based VM. [Crafting Interpreters: A Virtual Machine](https://craftinginterpreters.com/a-virtual-machine.html)
- **Regular expression engine** — Start with literals and concatenation, then add repetition and alternation. [Russ Cox: Regular Expression Matching](https://swtch.com/~rsc/regexp/regexp1.html)
- **JSON parser** — Parse JSON values and report useful syntax errors. [RFC 8259](https://www.rfc-editor.org/rfc/rfc8259)
- **Markdown parser** — Convert a small Markdown subset into HTML. [CommonMark spec](https://spec.commonmark.org/)

### Developer tools

- **Git** — Build a content-addressed object store and a basic commit history. [Git book](https://git-scm.com/book/en/v2) · [Git reference](https://git-scm.com/docs)
- **Shell** — Parse commands, run processes, and connect pipes. [POSIX shell overview](https://pubs.opengroup.org/onlinepubs/9799919799/utilities/V3_chap02.html)
- **Text editor** — Create a terminal editor with cursor movement, editing, and file saving. [Build Your Own Text Editor](https://viewsourcecode.org/snaptoken/kilo/)
- **Container runtime** — Learn namespaces, cgroups, and filesystem isolation. [Linux namespaces](https://man7.org/linux/man-pages/man7/namespaces.7.html) · [cgroups](https://docs.kernel.org/admin-guide/cgroup-v2.html)
- **Build system** — Track source files and rebuild targets when dependencies change. [GNU Make manual](https://www.gnu.org/software/make/manual/)

### Data and search

- **Key-value database** — Implement a log-structured store, then add indexing. [SQLite architecture](https://www.sqlite.org/arch.html)
- **SQL database** — Parse a small SQL subset and execute queries over tables. [SQLite: How It Works](https://www.sqlite.org/howitworks.html)
- **Search engine** — Index documents, build an inverted index, and rank results. [Stanford: Information Retrieval](https://nlp.stanford.edu/IR-book/)
- **Cache** — Add eviction policies such as LRU and measure hit rates. [Redis eviction](https://redis.io/docs/latest/develop/reference/eviction/)
- **Compression tool** — Implement Huffman coding and compare output sizes. [Huffman coding overview](https://en.wikipedia.org/wiki/Huffman_coding)

### Operating systems and hardware

- **Operating system kernel** — Boot a tiny kernel and add a basic scheduler. [OSDev Wiki](https://wiki.osdev.org/Main_Page) · [xv6 book](https://pdos.csail.mit.edu/6.828/2024/xv6/book-riscv-rev4.pdf)
- **CPU emulator** — Decode instructions and model registers and memory. [CHIP-8 guide](https://tobiasvl.github.io/blog/write-a-chip-8-emulator/)
- **Memory allocator** — Start with a free list, then experiment with allocation strategies. [glibc malloc internals](https://sourceware.org/glibc/wiki/MallocInternals)
- **File system** — Store files and directory entries in a disk image. [The little book about OS development](https://littleosbook.github.io/)

### AI and machine learning

- **Neural network** — Implement forward and backward passes for a tiny network. [Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html)
- **Autograd engine** — Build a scalar computation graph and calculate gradients. [micrograd](https://github.com/karpathy/micrograd)
- **Tokenizer** — Learn byte-pair encoding and inspect token boundaries. [GPT-2 encoder](https://github.com/openai/gpt-2/blob/master/src/encoder.py)
- **Vector search** — Store embeddings and compare cosine similarity and approximate indexes. [Faiss documentation](https://faiss.ai/)

### Graphics and games

- **3D renderer** — Transform and rasterize triangles, then add lighting. [Scratchapixel](https://www.scratchapixel.com/)
- **Ray tracer** — Trace rays through a scene and shade simple spheres. [Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html)
- **Physics engine** — Add rigid bodies, collision detection, and simple impulses. [Box2D documentation](https://box2d.org/documentation/)
- **Game of Life** — Build a grid simulation and experiment with rules and rendering. [Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life)

### Distributed systems

- **Message queue** — Persist messages and let consumers acknowledge work. [RabbitMQ tutorials](https://www.rabbitmq.com/tutorials)
- **Raft consensus** — Implement leader election and replicated logs. [Raft paper](https://raft.github.io/raft.pdf) · [visualizer](https://raft.github.io/)
- **MapReduce** — Split a job into map and reduce stages. [Google MapReduce paper](https://research.google/pubs/mapreduce-simplified-data-processing-on-large-clusters/)
- **Event stream** — Build an append-only log with offsets and consumer groups. [Kafka design](https://kafka.apache.org/documentation/#design)

## Learning references

- [Teach Yourself Computer Science](https://teachyourselfcs.com/) — A structured map of core CS subjects.
- [The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) — Practical tools for working effectively.
- [Computer Science Field Guide](https://csfieldguide.org.nz/en/) — Accessible explanations and activities.

## Contributing

Contributions are welcome. Please open an issue or pull request with:

- the project category and a short description;
- a direct link to a high-quality tutorial, specification, or reference implementation;
- the resource's language, difficulty, and any prerequisites, if known;
- a note if the resource is paid, incomplete, or no longer maintained.

Prefer original sources and step-by-step material. Check that links work, avoid duplicate entries, and do not copy tutorial text into this repository. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License and attribution

The original text and organization in this repository are released under the [MIT License](LICENSE). Linked resources belong to their respective authors and remain under their own terms. This project is independent and is not affiliated with CodeCrafters or any linked organization.

