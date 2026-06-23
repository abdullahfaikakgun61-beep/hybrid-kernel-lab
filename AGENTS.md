# AI Agent Guidance for hybrid-kernel-lab

## What this repository is
- Primary source tree: `kernel-lab/linux-layer/linux`
- This is a Linux kernel source tree and should be treated as the main development area.
- Other directories such as `kernel-lab/microkernel-study`, `kernel-lab/security-layer`, and `kernel-lab/tests` exist in the workspace, but they are currently empty or secondary research/test layers.

## Where to focus
- Start with `kernel-lab/linux-layer/linux` for code, build, and test work.
- Use the tree’s native Linux kernel conventions rather than assuming a typical application repository.

## Build and test conventions
- Build from the Linux kernel tree root: `cd kernel-lab/linux-layer/linux`
- Common commands:
  - `make defconfig`
  - `make -j$(nproc)`
  - `make modules`
  - `make modules_install`
  - `make headers_install`
- If cross-building is required, set `ARCH=` and `CROSS_COMPILE=` appropriately.
- If asked for tests, prefer kernel selftests and Linux kernel tooling rather than application-level unit test frameworks.

## Important documentation
- `kernel-lab/linux-layer/linux/Documentation/process/coding-assistants.rst`
- `kernel-lab/linux-layer/linux/Documentation/process/coding-style.rst`
- `kernel-lab/linux-layer/linux/Documentation/kbuild/index.rst`
- `kernel-lab/linux-layer/linux/README`

## Agent behavior
- Preserve Linux kernel coding style and semantics.
- Avoid adding or changing large sections of kernel code unless the user explicitly requests it.
- For implementation, keep changes minimal and aligned with upstream Linux kernel patterns.
- When referencing documentation, link to the source files above instead of copying them verbatim.
- Do not assume this is a standard user-space project with npm, Python, or other application build systems.

## Notes
- No existing AI customization file was present before this guidance.
- The repository root contains only a high-level title README; the real development tree lives under `kernel-lab/linux-layer/linux`.
