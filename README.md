# DjVuLibre (DjvuNet Fork)

**Notice:** This repository is a customized fork of the upstream [DjVuLibre](https://djvu.sourceforge.net/) project. It is specifically maintained to serve as the **reference implementation** used to test compatibility and validate the outputs of the **[DjvuNet](https://github.com/DjvuNet/DjvuNet)** .NET library.

## Customizations for DjvuNet CI/CD

This fork includes specific modifications to modernize and streamline the build process so it can be reliably compiled in modern CI environments (like GitHub Actions and AppVeyor):

1. **vcpkg Integration:** The native dependency management has been completely migrated to `vcpkg` in manifest mode (`vcpkg.json`). The library dynamically links against modern, secure versions of its dependencies (including `libjpeg-turbo`, `tiff`, `libpng`, and `giflib`).
2. **MSBuild Modernization:** The legacy Visual Studio `.props` and `.vcxproj` files have been refactored. Hardcoded legacy paths (e.g., `deps\` folder references) have been removed in favor of `vcpkg`'s native MSBuild integration, allowing automatic restoration and AppLocal deployment of required dynamic DLLs during compilation.
3. **Multi-Architecture Support:** The project configuration seamlessly supports building for `x86`, `x64`, and `arm64` natively, ensuring compatibility with modern testing environments.

## Upstream Documentation

For the original DjVuLibre documentation, compilation instructions for standard platforms, and license information, please refer to the original `README` file located in this directory.

---
*Maintained as part of the DjvuNet project.*