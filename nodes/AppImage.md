---
context:
---

# AppImage

Format for distributing and running self-contained [[Linux]] applications.

---

Single executable file that contains the application and most of its required libraries.

Designed to run on many [[Linux Distribution|Linux Distributions]] without modification.

## How to Run

1. Make the AppImage file executable: `chmod +x file.AppImage`
2. Run directly: `./file.AppImage`

No root permissions required.

Nothing is unpacked into system directories.

## Characteristics

Pros:

**Portable**: One file works across many distributions.
**No Installation**: Runs directly from any location.
**Self-contained**: Bundles dependencies within itself.

Cons:

**Size**: Larger file sizes due to bundled libraries.
**No Updates**: Updates are not automatic (unless the AppImage supports that).
