# 22 Store 🚀

### Open-Source Library & Script Store

**22 Store** is a free, community-driven collection of reusable libraries and ready-to-use scripts for developers.

It is built to make code easier to **find, download, reuse, and share** across different projects and languages.

---

## 📦 What's in 22 Store?

22 Store has two main resource types:

### Libraries

Reusable packages or modules that can be added to a project and used by other code.

Libraries are suitable for things such as:

- APIs and SDKs
- utilities and helper modules
- AI or automation libraries
- reusable application logic
- language-specific packages

### Scripts

Ready-to-use programs or tools that can be downloaded and used directly.

Scripts are suitable for things such as:

- utilities
- automation tools
- small developer tools
- examples and standalone programs

---

## 💻 QuickCode

22 Store is integrated with **QuickCode**, where Store resources can be accessed through QuickCode's own command system.

### Install a Library

Inside QuickCode:

```bash
22 install <name>
```

Example:

```bash
22 install google_generativeai
```

This command tells QuickCode to find the requested library in the 22 Store registry and install the appropriate package.

### Get a Script

Inside QuickCode:

```bash
22 get <name>
```

Example:

```bash
22 get calculator
```

The requested script is downloaded from the Store and placed into the currently active project folder in QuickCode.

> **Important:** `22 install` and `22 get` are QuickCode commands. They are not commands provided by GitHub or by this repository itself.
>
> Other developers and applications can use the 22 Store registry with their own commands, interfaces, installers, or workflows.

---

## 🌍 Multi-Language Support

22 Store is designed to support resources written in different languages.

Current structure:

```text
libraries/
├── python/
├── java/
├── cpp/
└── web/

scripts/
├── python/
├── java/
├── cpp/
└── web/
```

Additional languages can be added as the Store grows.

The language of a resource does not determine how another application has to access it. Developers are free to integrate Store resources into their own tools in the way that fits their project.

---

## 🧭 How the Store Works

The repository contains both the actual resources and a registry that describes them.

```text
Developer
   │
   ├── finds a resource
   │
   ├── reads its metadata
   │
   └── downloads the appropriate file
   │
   ▼
22 Store
```

The registry provides machine-readable information such as:

- package ID
- name
- type
- language
- version
- release status
- supported architectures
- source
- available distribution files

Applications can use this information to discover and download resources without relying on hardcoded package URLs.

---

## 🏗️ Architecture Support

Some resources are architecture-independent, while others contain native or compiled components.

### Architecture-independent

A pure-source or architecture-independent package may declare:

```json
"architectures": ["any"]
```

### Native / compiled resources

If a resource contains architecture-dependent native binaries, it must declare the architectures it actually supports.

Example:

```json
"architectures": ["armv7", "arm64"]
```

A package is **not** automatically `any` just because its primary language is Python. If it contains native components, those components determine the required architecture support.

Current architecture identifiers include:

- `any`
- `source`
- `armv7`
- `arm64`
- `x86`
- `x86_64`

---

## 🔎 Finding Resources

Each resource has metadata in the registry.

The registry is organized as:

```text
registry/
├── index.json
├── schema.json
└── packages/
    ├── <package-id>.json
    └── ...
```

The index connects a resource's stable ID to its metadata.

Package metadata can describe the resource, its version, license, author, maintainer, supported architectures, and distribution files.

---

## 🤝 Contributing

Want to add something to 22 Store?

The basic contribution flow is:

```text
Create / prepare resource
        ↓
Choose Library or Script
        ↓
Choose the correct language
        ↓
Add accurate metadata
        ↓
Submit contribution
        ↓
Review
        ↓
Publication
```

Before submitting, make sure your contribution:

- works as described
- is placed in the correct resource and language directory
- has accurate metadata
- respects its original license and copyright
- does not contain malicious or unauthorized code
- is safe for others to use

If a contribution is later modified or maintained by 22, the original author and 22's maintainer role should both remain properly attributed.

---

## 🛡️ Review & Security

Contributions are reviewed before publication.

The review process may include:

1. Automated validation
2. Malware and security checks
3. Manual review
4. Metadata and license verification
5. Publication after approval

Automated security checks are signals for review; human review remains important.

If a resource is found to be malicious or unsafe, the affected resource can be quarantined or unpublished so that unrelated resources remain available.

Repeated malicious submissions may result in contributor restrictions or a permanent ban.

---

## 📜 Licensing

The 22 Store repository is licensed under the **MIT License**.

For individual resources, contributors must have the right to submit the code under the license declared for that resource.

Third-party code must retain its applicable copyright notices, attribution, and license requirements.

Hosting code in 22 Store does not automatically change its original license.

---

## 📁 Repository Structure

```text
22-Store/
├── libraries/
│   ├── python/
│   ├── java/
│   ├── cpp/
│   └── web/
│
├── scripts/
│   ├── python/
│   ├── java/
│   ├── cpp/
│   └── web/
│
├── registry/
│   ├── index.json
│   ├── schema.json
│   └── packages/
│
├── libs.json
├── LICENSE
└── README.md
```

---

## 🌱 Built for Developers

Whether you are:

- **Exploring** the Store
- **Downloading** a resource for your project
- **Integrating** the registry into your own application
- **Contributing** a library or script

22 Store is designed to keep the process simple and understandable.

---

### Happy Coding 💻

**22 Store — Harvesting Potential Everywhere.**
