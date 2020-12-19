# studiorack-plugin-dplug
![Release](https://github.com/studiorack/studiorack-plugin-dplug/workflows/Release/badge.svg)

Audio plugin starter template using Dplug framework to build VST3 plugins using:

* Bash
* CMake 3.4.x
* Dplug 10.0.x


## Installation

Install D-lang and D-compiler using:

    brew install dub dmd ldc

Check you have the correct dependencies installed:

    dub --version
    dmd --version
    ldc2 --version

Ensure all git submodules are initialized:

    git submodule update --init --recursive

Build the tool:

    cd ./dplugsdk/tools/dplug-build && dub --compiler ldc2 && cd ../../../

## Usage

Make all your plugin development changes in the source folder at:

    ./src

Ensure you also update the preview image and audio files:

    ./src/assets/name.png
    ./src/assets/name.wav


## Testing your plugin

Todo


## Build (manual)

Check your default compiler target using:

    ldc2 -version

Compile a development version of the plugin using:

    cd ./dplugsdk/examples/clipit && ../../tools/dplug-build/dplug-build -c VST3 -a x86_64 && cd ../../../

View the built plugin files at:

    ./build/

Build the final plugin binaries using:

    cd ./dplugsdk/examples/clipit && ../../tools/dplug-build/dplug-build -c VST3 -a x86_64 --final && cd ../../../

Rename file if it contains invalid characters/spaces:

    mv "./dplugsdk/examples/clipit/builds/macOS-64b-VST3/Witty Audio CLIP It.vst3" "./dplugsdk/examples/clipit/builds/macOS-64b-VST3/WittyAudioCLIPIt.vst3"

Copy any additional files:

    cp -v ./src/assets/* ./dplugsdk/examples/clipit/builds/macOS-64b-VST3

For metadata generation as json use the studiorack-cli:

    npm install @studiorack/cli -g

Validate your plugin:

    studiorack validate "./dplugsdk/examples/clipit/builds/**/*.{vst,vst3}"

Convert and enrich validator report metadata into json:

    studiorack validate "./dplugsdk/examples/clipit/builds/**/*.{vst,vst3}" --json


## Build (automatic)

Release a plugin version on GitHub by simply creating a version tag:

    git tag v0.0.1
    git push && git push origin --tags

This will run an automated build and release process on GitHub Actions:

    .github/workflows/release.yml


## Resources & guides

* [Dplug framework source code and examples](https://github.com/AuburnSounds/Dplug)
* [Official Dplug guide to creating VST audio plugins](https://dplug.org)


## Contact

For more information please contact kmturley
