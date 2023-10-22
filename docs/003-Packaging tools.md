For C++ developers who want to distribute their software across multiple platforms, there are several tools that can assist in creating platform-specific packages like MSI for Windows, DEB for Debian-based Linux, and DMG for macOS. Here's a selection of tools that can help package C++ applications:

1. **CMake CPack** :
   * Part of the CMake suite, CPack can generate various installer formats based on the platform, including MSI, DEB, RPM, DMG, and more.
   * Offers a consistent method for packaging across platforms when you're already using CMake for your build system.
   * [Official Documentation](https://cmake.org/cmake/help/latest/manual/cpack.1.html)
2. **Inno Setup** :
   * A script-driven installation system created in Delphi for Windows.
   * While it doesn't create MSI files (it creates EXE installers), it's widely used and supports a lot of customization.
   * [Official Website](http://www.jrsoftware.org/isinfo.php)
3. **WiX (Windows Installer XML)** :
   * Toolset that builds Windows installation packages (MSI, MSP, MSM, etc.) from XML source code.
   * Integrates with build automation, thus can be used as part of a C++ project's build system.
   * [Official Website](https://wixtoolset.org/)
4. **fpm (Effing Package Management)** :
   * Helps in building packages for multiple platforms (DEB, RPM, etc.) with a single, consistent interface.
   * Useful for developers who might be unfamiliar with the nuances of each platform's package management.
   * [GitHub Repository](https://github.com/jordansissel/fpm)
5. **Packages** (for macOS):
   * A tool for macOS that helps design and build packages (.pkg) and distribution bundles (.dmg and .zip) for software distribution.
   * [Official Website](http://s.sudre.free.fr/Software/Packages/about.html)
6. **create-dmg** :
   * A simple shell script to create a fancy DMG for distribution on macOS.
   * [GitHub Repository](https://github.com/sindresorhus/create-dmg)
7. **electron-builder** :
   * While primarily designed for Electron apps, it can be used topackage non-Electron native apps (like those written in C++) with some effort.
   * Can package for Windows (MSI, NSIS), macOS (DMG, pkg), and Linux (AppImage, DEB, RPM, etc.).
   * [GitHub Repository](https://github.com/electron-userland/electron-builder)

While these tools can handle the packaging of applications, it's also crucial to handle dependencies correctly, especially for C++ applications that might link to various libraries. Some packaging tools and systems have built-in ways to handle dependencies, but developers might need to provide extra instructions or scripts to ensure everything is bundled correctly.
