local manifest and instructions for building omni on a d2 device.

These instructions should be the same on any linux distro assuming you have a proper build environment set up.

This is subject to heavy change, so expect updates, and I'd recommend checking back here. (expect changes in the manifest as well). This is a simple build of omni with no added tweaks.

This guide assumes you are in your omnirom root directory (so wherever omnirom was repo sync'd). This guide also assumes you haven't changed anything yet.
===================================================================================

Steps:

1. Use extrasrc.xml, (Just in case you didn't know, place the local manifest in [insert build directory here]/.repo/local_manifests/ , and if the local_manifests directory doesn't exist, create it.)

2. After running . build/envsetup.sh , run "repopick 5946 6353 6663 7954" (without the quotes). Then, just run "brunch d2lte" to start the build.