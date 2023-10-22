Cross-platform UI frameworks for C++ have made it possible to write applications once and deploy them on multiple platforms without major modifications. Here are some of the most common free cross-platform UI frameworks for C++:

1. **Qt** :
   * One of the most popular and mature cross-platform UI libraries.
   * Provides a wide range of features, including a GUI toolkit, networking, file I/O, and more.
   * Uses a custom meta-object compiler (MOC) for features like signals and slots.
   * Available under both open-source (GPL & LGPL) and commercial licenses.
   * [Official Website](https://www.qt.io/)
2. **wxWidgets** :
   * Provides native-looking GUI applications for multiple platforms.
   * Has been around since the 1990s and has a mature codebase.
   * Uses native controls on each platform.
   * Open source (wxWindows License).
   * [Official Website](https://www.wxwidgets.org/)
3. **Dear ImGui** :
   * An immediate-mode GUI toolkit, primarily for creating tools, debuggers, and other visualizations.
   * Highly portable and renderer agnostic.
   * Great for integrating with game engines or real-time applications.
   * Open source (MIT License).
   * [GitHub Repository](https://github.com/ocornut/imgui)
4. **FLTK (Full Light Toolkit)** :
   * Lightweight and modular GUI toolkit.
   * Uses its own drawing routines, ensuring a consistent look across platforms.
   * Open source (GPL & LGPL with an exception that allows static linking).
   * [Official Website](https://www.fltk.org/)
5. **GTK+ (GIMP Toolkit)** :
   * Originally developed for the GIMP, but expanded into a general-purpose library.
   * Primarily targets Linux but has ports for other platforms.
   * Uses a signal-based mechanism for event handling.
   * Open source (LGPL License).
   * [Official Website](https://www.gtk.org/)
6. **JUCE** :
   * Suited for both applications and audio plugins.
   * Provides a wide range of features beyond just UI, such as audio, networking, and more.
   * Open source (GPL) and commercial licenses available.
   * [Official Website](https://juce.com/)
7. **NanoGUI** :
   * A minimalistic cross-platform widget library for OpenGL.
   * Suitable for real-time applications like games or interactive simulations.
   * Open source (BSD License).
   * [GitHub Repository](https://github.com/mitsuba-renderer/nanogui)
8. **Nuklear** :
   * A minimalist GUI library, inspired by immediate-mode GUI concepts.
   * Highly portable and has no dependencies.
   * Open source (Public Domain).
   * [GitHub Repository](https://github.com/Immediate-Mode-UI/Nuklear)

When selecting a framework, consider the specific requirements of your project, such as the platforms you're targeting, the look and feel you want for your application, and the available development resources. For many general applications, Qt or wxWidgets are popular choices due to their comprehensive feature sets and mature ecosystems.
