local manifest and instructions for building omni on a d2 device. (If you are using these instructions, use the extrasrc.xml manifest.)

PLEASE NOTE: These instructions are for building with pure omni, but you won't be able to use a custom kernel because the kernel change needed to build omni in this manner will not be done by custom kernels, since omni and omni-based ROMs are the only ROMs that needs it. (If they used audio/media/display caf from omni) If you try to use a custom kernel, it will not boot. If you want to use a custom kernel and still use omni, check out my other README.

This was built on ArchLinux, but these instructions should be the same on any linux distro as long as you have all the proper dependencies.

This is subject to heavy change, so expect updates, and I'd recommend checking back here. (expect changes in the manifest as well). This is a simple build of omni with no added tweaks.

This guide assumes you are in your omnirom root directory (so wherever omnirom was repo sync'd). This guide also assumes you haven't changed anything yet.
===================================================================================

Steps:

1. Use the extrasrc.xml manifest. (Just in case you didn't know, place the local manifest in [insert omni build directory here]/.repo/local_manifests/ , and if the local_manifests directory doesn't exist, create it.)

2. Edit .repo/manifest.xml. Find the three projects (audio-caf, media-caf, and display-caf). Change the revision which should say "android-4.4" to "qcom-4.4_2.7". (You can still do this the way this used to be done without having to edit the default manifest, but for now, this method is easier for a few reasons. This is going to change soon.)

3. If you do a repo sync and you get an uncommitted changes in .repo/manifests "error", then you need to go into .repo/manifests, do a git reset --hard, and then do a repo sync. Then repeat step 2 again, and then do a repo sync again. 

4. Before starting the build, after running . build/envsetup.sh, run "repopick 5177 5361" without the quotes. (This command picks stuff from omni's gerrit that haven't been merged yet. This is subject to change as omni merges stuff, so expect this to change, maybe even right after this readme is uploaded to github.) You will have to run both of these commands every time you repo sync because repo sync will overwrite the changes.
