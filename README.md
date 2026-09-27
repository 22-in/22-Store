# 22 Store 🚀

### The Open-Source Package & Script Registry

**22 Store** is the community distribution system for reusable developer resources.

It supports two kinds of resources:

- **Libraries** — reusable packages installed with `22 install <name>`
- **Scripts** — ready-to-use tools downloaded with `22 get <name>`

The Store is designed for **QuickCode** first, while remaining usable by other developers and applications.

---

## 📦 Resource Types

### Libraries

Libraries are reusable packages/modules that can be installed into a development environment.

```bash
22 install google_generativeai
```

### Scripts

Scripts are standalone, ready-to-use resources.

```bash
22 get calculator
```

A script can then be placed into the user's currently active/open project folder.

---

## 🌍 Multi-Language Support

Resources are separated by language:

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

Future languages can be added without changing the registry model.

---

## 🧭 Registry

The registry is the source of truth for package discovery and distribution.

```text
registry/
├── index.json
├── schema.json
└── packages/
    ├── <package-id>.json
    └── ...
```

A client should **not hardcode package download URLs**.

The intended V3 flow is:

```text
22 install <name>
        ↓
registry/index.json
        ↓
package metadata
        ↓
compatible artifact
        ↓
install
```

The same registry model is used for `22 get <name>`.

This lets the Store change package locations, add versions, and provide different artifacts without requiring a client update.

---

## 🏗️ Architecture Compatibility

Architecture-independent packages can use:

```json
"architectures": ["any"]
```

Native/binary packages must declare their supported architectures and provide matching artifacts, for example:

```json
"architectures": ["armv7", "arm64"]
```

A package containing native components is **not** `any` merely because its main language is Python.

Current architecture values:

- `any`
- `source`
- `armv7`
- `arm64`
- `x86`
- `x86_64`

---

## 🔄 QuickCode V2 Compatibility

QuickCode V2 currently uses the legacy `libs.json` format.

**Do not remove `libs.json` yet.**

V2 continues to resolve its existing libraries through that file, while V3 is being designed around the registry.

This keeps V2 compatible without forcing V3 to keep the old architecture.

---

## 🛡️ Review & Security

Community contributions are reviewed before publication.

The planned process includes:

1. Contributor submits a resource.
2. Automated checks inspect the submission.
3. Security/malware checks provide additional signals.
4. Human review verifies the resource.
5. Approved resources are published to the registry.

A security finding should quarantine the affected resource rather than automatically removing unrelated legitimate resources.

Repeated malicious submissions can result in escalating strikes and a permanent contributor ban.

---

## 🤝 Contributing

Contributors should submit resources in the correct language and resource-type directory.

Before submission, make sure the resource:

- works as described
- includes accurate metadata
- respects its original license and copyright
- does not contain malicious or unauthorized code
- follows the Store's package structure

If a contributor's code is later modified or maintained by 22, the registry should preserve both the original author and the 22 maintainer attribution.

---

## 📜 Licensing

22 Store uses the MIT license for the repository itself.

Individual packages must respect their actual upstream licenses and copyright requirements. A contributor must have the right to submit code under the license declared in its package metadata.

The Store must not automatically relicense third-party code simply because it is hosted here.

---

## 🚀 Current Status

The registry foundation is being built incrementally.

Current goals:

- stable package IDs
- library/script separation
- multi-language support
- architecture-aware artifacts
- version-aware distribution
- secure community publishing
- QuickCode V3 integration

### Happy Coding 💻

**22 Store — Harvesting Potential Everywhere.**
