# Minecraft Server Docker OpenShift Container via Source to Image (S2I)

## OpenShift

Create a project named e.g. `test` on the web console (NOT using `oc new-project test`), and:

    oc project test

    oc new-app fabric8/s2i-java~https://github.com/vorburger/s2i-minecraft-server.git

    oc logs -f bc/s2i-minecraft-server

## Locally

Build it [using S2I](https://github.com/openshift/source-to-image):

    s2i build --copy . fabric8/s2i-java s2i-minecraft-server

Run it with:

    docker run -p 25566:25565 s2i-minecraft-server

Debug it with:

    docker run -it s2i-minecraft-server /bin/bash

## What else?

The sources are in the .s2i/ directory, which you may not see if you are filtering .*
