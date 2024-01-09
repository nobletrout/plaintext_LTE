# Findings on deploying your own packet core so far

## MAGMA
https://magmacore.org/join-the-open-source-community/

start with the build steps here but stop at make in vagranat:
https://magma.github.io/magma/docs/next/basics/prerequisites

Don't fret about the steps for building AGW with make, use the bazel build instructions IN the same vagrant box
https://magma.github.io/magma/docs/next/bazel/agw_with_bazel

The dev environment on mac is great, but a huge resource hog. Be prepared for lots of microservices and three different opinions for running environments.
The TLDR there is that you will be running:
 - virtual box
 - docker
 - maybe some kubernetes magic

Registering UE's:
Sexy magic is here:
https://magma.github.io/magma/docs/next/lte/deploy_config_apn
