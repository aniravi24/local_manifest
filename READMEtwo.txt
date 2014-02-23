local manifest and instructions for building omni on a d2 device. (If you are using these instructions, use the extrasrctwo.xml manifest.)

PLEASE NOTE: The manifest that goes along with this one is not pure omni (there's a little slimROM) but it will allow you to use a custom kernel if you want. Note that the instructions are the same as the first one except the media-caf cherry-pick is not necessary. The necessary changes have been made in the manifest. 

This was built on ArchLinux, but these instructions should be the same on any linux distro as long as you have all the proper dependencies.

This is subject to heavy change, so expect updates, and I'd recommend checking back here. (expect changes in the manifest as well). This is a simple build of omni with no added tweaks.

This guide assumes you are in your omnirom root directory (so wherever omnirom was repo sync'd). This guide also assumes you haven't changed anything yet.
===================================================================================

Steps:

1. Use extrasrctwo.xml, (Just in case you didn't know, place the local manifest in [insert build directory here]/.repo/local_manifests/ , and if the local_manifests directory doesn't exist, create it.)

And build! There's nothing special needed anymore :)
