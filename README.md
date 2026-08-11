# plc_build_env
Test repository for PLC CI/CD process

## Structure

This repo will consist of:
 - `.github/` directory for the .yaml that defines the github action workflow.
 - `doc/` directory for the requirements documents (and any relevant documentation).
 - `src/` directory for the .st and .iecst source code

## Plan

1. Add code **[IN PROGRESS]**
   - .iecst, .st, .yaml
   - Tag with requirements
2. Test functionality
   - test Rusty compile
   - test bats tests
3. Test .yaml
   - configure github actions
   - relevant deployment
   - POC
4. Tidy up
   - UML diagram process explanation
   - Implementation requirements and process 
5. Further work
   - Include building of ctrlX apps (C, python) using the SDK
   - Deployment for BR systems
