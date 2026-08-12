# log notes

creating apps for the OS (use the datalayer, interact with the PLC)
 - https://www.youtube.com/watch?v=JujnawKLWeI
 - so snap is just a way of running apps like Docker
   - transferable, less resources than VMs fast exe, container-based
   - snap is more running like it's own process, more interaction between host OS
   - Docker can run multiple, Snap can only run once in host system (not multiple of the same snap)
   - **snap is closer to the host system so it can be realtime, unlike Docker**
   - snap is the name of the container that contains app, DLLS etc.
 - The app is an installable package that can contain for than one snap
   - one app will usually alway contain 2 snaps, one for ARM, one for AMD
   - app is rexroth specific, snap is canonical (ubuntu) generic
   - .app is just archive that you can open and find the snap folders (contains .snap container)
 - process of making an app
   - un-compiled source code > compile into exe, cmake for example (script files like python don't need to be compiled)> snapcraft.yaml to pack into snaps with used libraries > sign into apps
 - development environment (linux required), can set from scratch, but I think the sdk thing is what we want
 - CMakeLists.txt has TARGET_PROJECT_NAME, overall structure:
   - min required
   - internal versioning system, project name
   - **target project name** (will need to be changed for own app)
   - dependency directories
   - option to build the snap package, can ask cmake to automate the snap build (usually off so you can check the build process and can take around 20 seconds)
   - compiler settings (arm or x64)
   - **executable source file**
   - set libraries that will be used later on
   - snap build options
   - installation of files
 - snapcraft.yaml has Name, Version, Summary
   - (in snap folder) 
   - useful link for reference: https://ubuntu.com/docs/snapcraft/9/reference/snapcraft-yaml/
     - link is broken to the snapcraft yaml references, maybe worth opening issue on sdk
   - name of application (easier to name the same as cmakelists, will be seen in ctrlx core)
   - versioning (mandatory for updates and stuff)
   - grade to tell developers state
   - description
   - base is the version of ubuntu to be used
   - confinement should be set to strict to control access
   - apps: are the application(s)/executable(s) inside of the snap
     - **Command name needs to be the same as in the cmakelsits**
     - plugs are what the app will need to access in the ubuntu core and (other snaps with plugs and slot mechanism)
     - daemon describes how the app should be handled (simple means app will be started with snap)
 - Main.cpp has the functional code used in the app

make template of both cmake and snap for app building: /home/boschrexroth/application_development/template_proj
 - made a reasonable template for the code will have to test and refine
 - push to a relevant github eventually

further software app development, specifically integration with CtrlX automation
 - manifest (manifest.json, at configs/package-assets/?)
   - version and ID
   - "menus" to integrate into the menus (sidebar)
   - "link" to the .html that is used by thr webserver
 - schema link, ok this provides some intellisense for the the manifest.json.