# Suspicious Package

This repository is a home for the Suspicious Package disk image download, available under **Releases**.

For more information, see these pages on the Suspicious Package website:

* [User Guide](https://www.mothersruin.com/software/SuspiciousPackage/use.html)
* [FAQ](https://www.mothersruin.com/software/SuspiciousPackage/faq.html)
* [Release Notes](https://www.mothersruin.com/software/SuspiciousPackage/relnotes.html)

## What's New in Suspicious Package 3.7 (773)

_Released on March 7, 2021_

- Runs natively on Apple Silicon Macs.
- Improved compatibility with macOS 11 (Big Sur), including:
  - Adopted the new "unified" style for the toolbar, and updated the icons
    to fit in better with the general Big Sur "design language,"
    especially when the toolbar is configured for Icon Only mode.
  - Updated to a new ~~iOS-style~~ Big Sur-style app icon. We're still not fans, but since
    our app icons were all circles before, we can't get _too_ snotty about them
    all being "squircles" now. Having every icon _on the system_ be the same shape
    seems a dubious improvement to macOS, but our icons aren't going to change anything.
  - Fixed other display and icon issues throughout the app.
- Added information about the supported processor architectures to the Package Info
  tab. This is relevant when running on an Apple Silicon Mac, where a package that
  doesn't explicit declare its support will wind up running the macOS Installer under Rosetta 2.
- Made the Quick Look preview more usable from the Finder's preview pane, i.e.
  `View > Show Preview`. Since the preview pane is typically much smaller,
  and since some information is shown directly by the Finder at the bottom of that
  pane, Suspicious Package now uses a more compact format here. When using
  `View > as Gallery`, or the classic separate window of `File > Quick Look Item`,
  Suspicious Package still creates a larger and more complete preview. Unfortunately, 
  Apple provides no proper way for us to detect what context we're being shown in, so 
  there's a bit of guesswork involved here, but we think it at least works better than it did.
- Fixed some bugs in the handling of the toolbar, including the fact that changes made via
  `View > Customize Toolbar` did not get saved, and that items pushed into the trailing
  "overflow" section of the toolbar did not get enabled properly.
- Fixed a bug where the Terminal might be chosen as a logical default app for opening
  a non-text install script, such as a Mach-O binary: this never should've been
  suggested as a default, since it would _run_ the binary and would be unsafe.
  Instead, Suspicious Package now chooses to show the item in the Finder if there's no more logical default.
- Fixed a bug in handling the unusual situation in which a package contains a
  folder whose name ends with a space character. Suspicious Package would show
  two versions of the folder, and could produce spurious Review messages about
  sizes being incorrect.

