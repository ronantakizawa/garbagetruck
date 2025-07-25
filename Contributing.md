# Contributing to GarbageTruck

Thank you for your interest in contributing to **GarbageTruck** — a distributed garbage collection system for microservices built with Rust and gRPC. This guide outlines how to set up your environment, follow code conventions, and submit contributions effectively.

---

## 🧰 Local Development Setup

### Prerequisites

- [Rust 1.75+](https://www.rust-lang.org/tools/install)
- [Protocol Buffers Compiler (`protoc`)](https://grpc.io/docs/protoc-installation/)
- [grpcurl](https://github.com/fullstorydev/grpcurl) (for testing gRPC)
- Docker + Docker Compose (for full local environment)

### Setup Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/ronantakizawa/garbagetruck.git
   cd garbagetruck
   ```
2. Build the project:

   ```bash
   cargo build --release --features "client,server"
   ```
3. Start via Docker Compose:

   ```bash
   docker-compose up --build
   ```

### Running Tests
* Run all unit and integration tests:

```bash
cargo test --all-features
```
*  Run gRPC-specific tests:

```bash
cargo test --features grpc
```

* Perform a gRPC health check:

```bash
garbagetruck health
```

### Code Style & Linting
* Follow standard Rust formatting:

```bash
cargo fmt
```

* Run Clippy for linting:

```bash
cargo clippy --all-targets --all-features -- -D warnings
```

* Code must compile without warnings before submitting a PR.

### Submitting a Pull Request
1. Fork the repository and create a new branch:

```bash
git checkout -b feature/your-feature-name
```
2. Make your changes with clear commits.
3. Before opening a PR:
   * Format your code (cargo fmt)
   * Run tests (cargo test)
   * Lint with Clippy (cargo clippy)
   * Ensure your branch is up to date with main
4. Submit a pull request with:
   * A clear title and description of what you changed
   * Reference to related issues (e.g., Closes #4)
5. Respond to feedback and make requested changes.

### Additional Resources
[Architecture](ARCHITECTURE.md): High-level system design and flow

[Readme](README.md): Quick start, commands, and demo links

[License](LICENSE): MIT License

Thanks again for contributing — we appreciate your help in making GarbageTruck better for everyone!
