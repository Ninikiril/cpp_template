# C++ Project Template

This repository provides a template for C++ projects using Visual Studio Code, Vcpkg, Doxygen, and Visual Studio Community 2022.

## Prerequisites

- [Visual Studio Code](https://code.visualstudio.com/)
- [Vcpkg](https://github.com/microsoft/vcpkg)
- [Doxygen](http://www.doxygen.nl/)
- [Visual Studio Community 2022](https://visualstudio.microsoft.com/vs/community/)

## Getting Started

### Install VS Community

Download Visual Studio Installer and install Desktop development with C++ and don't forget to add windows11 SDK

### Install vscode

Install vscode and add "C/C++" and "C/C++ extension Pack" extensions

### Install Dependencies

Install doxygen

### Clone the Repository

```sh
git clone https://github.com/Ninikiril/cpp_template.git
```

### Clone the vcpkg Repository

```sh
git clone https://github.com/microsoft/vcpkg.git
```
make sure path to vcpkg/ has no white space

### Open in Visual Studio Code

## Configure, Build and Run

### CMakePresets.json
Change vscode setting "Cmake: Use CMake Presets" to "always"

To add your own configuration presets from the compiler using Visual Studio Code, follow these steps:

1. Open the Command Palette in Visual Studio Code by pressing `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac).
2. Type `CMake: Add Config Preset` and select it from the list.
3. Follow the prompts to configure your preset. You will be asked to select a compiler and specify other configuration details.
4. Once the preset is added, it will be available in your `CMakePresets.json` file.

to use vcpkg you'll need to add in cacheVariables
the two following lines

```sh
    "CMAKE_TOOLCHAIN_FILE": "$env{VCPKG_ROOT}/scripts/buildsystems/vcpkg.cmake",
    "VCPKG_TARGET_TRIPLET": "x64-windows",
```

we'll tackle the issue with VCPKG_ROOT right now

### CMakeUserPresets.json

In CMakeUserPresets.json change "inherits" to your config name and VCPKG_ROOT to your vcpkg root

```sh
    "name": "default",
        "inherits": "your_config",
        "environment": {
            "VCPKG_ROOT": "C:/path/to/vcpkg"
        ...
```
### Status bar

You should be now good to go !

In the status bar you should find cmake tools extension if not right click and and toggle show the extension (if you can't find it you'll have to add the extension to vscode).

You can now select the config "default" (on the left of Build)
Select the build you want (Release, Debug, MinSizeRel, RelWithDebInfo) and select "Targets In Preset"

### Run and Debug

On the left Bar you'll find run and debug or (Ctrl + Shift + D) to launch either the apps or the tests

## Doxygen

To generate the doxygen select the docs_build build and build. In out/build/default/docs/html/ you'll find index.html you can open it using any browser

## License

This project is licensed under the GNU GENERAL PUBLIC LICENSE V3. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Visual Studio Code](https://code.visualstudio.com/)
- [Vcpkg](https://github.com/microsoft/vcpkg)
- [Doxygen](http://www.doxygen.nl/)
- [Visual Studio Community 2022](https://visualstudio.microsoft.com/vs/community/)
