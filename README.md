# Tasmota Build Environment

This project aims to give a VERY quick and painless way to set up a Dev Container based environment for creating your own Tasmota build. All you should need is Docker and VS Code installed on your local machine.

The repo uses submodules to pull in the "docker-tasmota" project and the source code for Tasmota itself. This generally works by the Dev Container opening the "docker-tamsmota" container and suppressing the default entrypoint. The default entrypoint will build all of the tasmota builds. 

This gives us the ability to modify the Tasmota source code and kick off our own builds via running VSCode tasks. I have two set up; one that runs the normal default 'tasmota' build and another for running the minimal build.

## Tasmota User Overrides

The **user_config_override.h** file is pre-created in the solutions /src folder and docker mapped into the correct location in the tamsota source code.

If you make changes to the file, it will be included in the builds you run.

It is currently set-up for Azure IoT Hub support. NOTE: If you run the minmial build, you may run into problems and need to comment out the TLS support.