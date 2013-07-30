Panappticon
===========
> Event-based tracing to measure Android application and platform performance


Details
-----------

For more information, see the [Panappticon
homepage](http://ziyang.eecs.umich.edu/projects/panappticon/) and
associated [technical
paper](http://ziyang.eecs.umich.edu/projects/panappticon/paper.pdf/).


Building Panappticon
--------------------

Panappticon consists of four code repositories. Each is included as a
submodule of this one.

* [panappticon-kernel](https://github.com/EmbeddedAtUM/panappticon-kernel) the Linux kernel modified for Panappticon tracing
* [panappticon-platform-framework-base](https://github.com/EmbeddedAtUM/panappticon-platform-framework-base) the Android base framework modified for Panappticon tracing
* [panappticon-platform-libcore](https://github.com/EmbeddedAtUM/panappticon-platform-libcore) the Android libcore modified for Panappticon tracing
* [panappticon-tools](https://github.com/EmbeddedAtUM/panappticon-tools) custom tools and Android services/applications for Panappticon trace collection and analysis

Only the Galaxy Nexus phone (the tuna family, maguro (GSM) and toro
(CDMA)) with Android versions 4.1.1_r6 and 4.1.2_r1 is currently
supported.

1. Clone this repository and checkout the branch for your desired version of Android:

   `git clone https://github.com/EmbeddedAtUM/panappticon.git`

   `git checkout panappticon-tuna-4.1.2_r1`

   `git submodule update --remote`

2. Replace the framework/base and libcore directories of your Android
   source tree with the corresponding directories in this repository.

3. Compile the kernel and replace the provided kernel image in your Android source tree.

4. Build the Android system images in the standard fashion.

5. Build and install on your server the EventLoggingServer application in the tools/ directory.  Panappticon traces will be uploaded by the phone.

6. Update the EventLogging application in the tools/ directory to point to your server's URL.

7. Build the EventLogging application and install the resulting *.apk.

8. The scripts in the tools/ directory may be helpful for parsing and interpretting the logs.


License
-------

The modified Linux kernel and Android platform sources are released
under their respective licenses.

The Panappticon tools are released under the GPLv3.
