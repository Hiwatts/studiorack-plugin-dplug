# studiorack-plugin-dplug
![Release](https://github.com/studiorack/studiorack-plugin-dplug/workflows/Release/badge.svg)

Audio plugin starter template using Dplug framework to build VST3 plugins using:

* Bash
* CMake 3.4.x
* Dplug 10.0.x


## Installation

Install D-lang and D-compiler using:

    brew install dub dmd ldc2

Check you have the correct dependencies installed:

    dub --version
    dmd --version
    ldc2 --version

Ensure all git submodules are initialized:

    git submodule update --init --recursive


## Usage

Make all your plugin development changes in the source folder at:

    ./src

Ensure you also update the preview image and audio files:

    ./src/assets/name.png
    ./src/assets/name.wav


## Testing your plugin

Todo


## Build (manual)

Depending on the the operating system you are on/building for, swap the generator string in the build commands:

* Linux: "Unix Makefiles"
* MacOS: "Xcode"
* Windows: "Visual Studio 16 2019"

Compile a development version of the plugin using:

    ?

View the built plugin files at:

    ./build/

Build the final plugin binaries using:

    ?

Copy any additional files:

    cp -v ./src/assets/* ./build/

For metadata generation as json use the studiorack-cli:

    npm install @studiorack/cli -g

Validate your plugin:

    studiorack validate "./build/**/*.{vst,vst3}"

Convert and enrich validator report metadata into json:

    studiorack validate "./build/**/*.{vst,vst3}" --json


## Build (automatic)

Release a plugin version on GitHub by simply creating a version tag:

    git tag v0.0.1
    git push && git push origin --tags

This will run an automated build and release process on GitHub Actions:

    .github/workflows/release.yml


## Resources & guides

* [Dplu framework source code and examples](https://github.com/AuburnSounds/Dplug)
* [Official Dplug guide to creating VST audio plugins](https://dplug.org)


## Contact

For more information please contact kmturley
