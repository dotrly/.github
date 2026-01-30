<div align="center">
  <h1>Relay</h1>
  <p><strong>The Operating System for the Web</strong></p>
  
  <p>
    <a href="https://relay.dev">Website</a> •
    <a href="https://docs.relay.dev">Documentation</a> •
    <a href="https://github.com/dotrly/relay">GitHub</a>
  </p>

  <p>
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License" />
    <img src="https://img.shields.io/badge/status-beta-orange.svg" alt="Status" />
    <img src="https://img.shields.io/badge/location-Switzerland-red.svg" alt="Switzerland" />
  </p>
</div>

<br />

## Introduction

**Relay** is a high-performance runtime environment designed to bridge the gap between local operating systems and the open web. It decouples the application layer from the runtime layer, allowing for ultra-lightweight, secure, and instant applications.

**dotrly** is the organization behind the format. Apps are distributed as `.rly` files—secure, encrypted bundles that run instantly on the Relay Runtime.

Unlike Electron or React Native, which bundle the runtime with every application, Relay provides a shared, optimized engine that stays resident in memory.

## Philosophy

Relay rejects the modern trend of software bloat.

We draw inspiration from the efficiency of the **Java ME and Symbian** era, where devices with mere megabytes of RAM ran rich, complex multitasking environments. Today, a simple calculator app often ships with an entire 150MB web browser engine (Chromium) attached to it.

Relay returns to the principles of extreme optimization:
*   **Shared Resources**: A single runtime instance services all applications.
*   **Functional Density**: Maximum features with minimum memory footprint.
*   **Native constraints**: Building for the web with the discipline of embedded systems development.

## Comparison

Relay shifts the paradigm from "One Browser, Many Tabs" to "One Runtime, Many Apps".

| Feature | Relay App | Electron App | React Native / Expo |
| :--- | :--- | :--- | :--- |
| **Distribution** | **Decentralized** (URL) | Binary Install | App Stores |
| **Bundle Size** | **~50 KB** (App logic only) | ~120 MB (Runtime bundled) | ~30 MB (Native libs bundled) |
| **Memory Footprint** | **Shared** (Efficient) | High (Per-app Chromium instance) | Medium |
| **Security** | **Sandboxed** (Permission based) | Full Trust (High Risk) | Sandboxed (OS level) |
| **Updates** | **Instant** (Server-side) | Manual Download | Store Review Process |
| **System Access** | **Bridge** (Controlled API) | Direct (Node.js) | Native Modules |

## Architecture

Relay is built on a modular architecture designed for security and performance.

### Core Components

*   **Shell**: The visual window manager and desktop interface. It acts as the **high-performance host** for user applications, handling windowing, multitasking, and system UI with sub-millisecond precision.
*   **Helper**: A local Node.js WebSocket server that acts as the privileged bridge between the Helper and the host OS.
*   **SDK**: The toolkit (`@dotrly/sdk`) that empowers developers to build these native-feeling apps using React 19.

### Security Model

Relay prioritizes user safety through a "locked-by-default" architecture.

1.  **Isolation**: Every app runs in a restricted iframe sandbox.
2.  **Permissions**: Access to file system or shell commands requires explicit user approval via the secure Helper bridge.
3.  **Governance**: The Relay Runtime enforces a mandatory "Close Protocol", ensuring no app can hold the user hostage.

## Building Apps

Relay Apps are standard React applications enhanced with the Relay SDK.

```bash
npx relay create-app my-new-app
```

See the [Documentation](https://docs.relay.dev) for API references, including File System access and Ollama AI integration.

## Contributing

We are building a new standard for web applications. Contributions are welcome. Please read `CONTRIBUTING.md` before submitting a Pull Request.

---

<div align="center">
  <p>Built with precision by the dotrly Team</p>
</div>
