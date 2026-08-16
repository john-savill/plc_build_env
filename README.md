# plc_build_env
Test repository for PLC CI/CD process

## Structure

This repo will consist of:
 - `.github/` directory for the .yaml that defines the github action workflow.
 - `doc/` directory for the requirements documents (and any relevant documentation).
 - `src/` directory for the .st and .iecst source code.
 - `assets/` diagrams.
 - `templates/` useful templates related to CtrlX app building.

## Actions

I have setup a runner on my local RPI 4b for testing. It will be left off most of the time for security. Dependencies will need to be installed. To run: `./actions-runner/run.sh`

## Process

![](assets/DRAFT%20PLC%20build%20environment%20process.png)

## Plan

1. Add code **[DONE]**
   - .iecst, .st, .yaml (disabled actions from the settings for the moment).
   - Tag with requirements
2. Test functionality **[IN PROGRESS]**
   - configure runner
   - test Rusty compile
   - test bats tests
4. Test .yaml
   - configure github actions
   - relevant deployment
   - POC
5. Tidy up
   - UML diagram process explanation
   - Implementation requirements and process 
6. Further work
   - Include building of ctrlX apps (C, python) using the SDK
     - incorporate the snapcraft.yaml for building the snap
   - Deployment for BR systems
