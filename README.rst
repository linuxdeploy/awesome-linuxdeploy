Awesome linuxdeploy!
====================

This project contains a list of everything that makes linuxdeploy_ (more) awesome. Most importantly all kinds of plugins.

.. _linuxdeploy: https://github.com/linuxdeploy/linuxdeploy

**Contributions welcome!** Please don't hesitate to send pull requests adding new plugins.


linuxdeploy plugins
-------------------

The following list should be considered incomplete. Please feel free to send pull requests to add your plugin!


Input plugins
*************

Input plugins can be used to bundle additional resources for frameworks, languages etc. into the AppDir, which would otherwise impossible to discover. They can be enabled by adding :code:`--plugin <name>`, e.g., :code:`--plugin qt`.

- linuxdeploy-plugin-qt_ bundles Qt plugins, translations, QML files etc. into the AppDir.
- linuxdeploy-plugin-conda_ creates a Miniconda environment that can be used to bundle Python software or provide a portable Python interpreter to software that uses Python for scripting.
- linuxdeploy-plugin-python_ wraps a vanilla Python build inside an AppImage. The primary focus is to provide a close to native Python work environment: ready to use, portable and isolated. It can also be used as a minimalist starting point for a Python based application.
- linuxdeploy-plugin-checkrt_ allows for bundling a copy of libstdc++ together with the other libraries, allowing AppImages to ship with newer C++ libraries than the target systems support. This allows for using newer C++ standards on distributions which they normally wouldn't support.
- linuxdeploy-plugin-gtk_ bundles Gtk+ resources, GLib schemas, and a lot more. Works for both Gtk+ 2 and 3.
- linuxdeploy-plugin-ncurses_ bundles resources required for ncurses-based applications to run properly.
- linuxdeploy-plugin-gstreamer_ bundles GStreamer plugins into the AppDir, along with their dependencies.
- misc-plugins_ is a collection of miscellaneous linuxdeploy plugin scripts.

.. _linuxdeploy-plugin-qt: https://github.com/linuxdeploy/linuxdeploy-plugin-qt
.. _linuxdeploy-plugin-conda: https://github.com/linuxdeploy/linuxdeploy-plugin-conda
.. _linuxdeploy-plugin-python: https://github.com/niess/linuxdeploy-plugin-python
.. _linuxdeploy-plugin-checkrt: https://github.com/darealshinji/linuxdeploy-plugin-checkrt
.. _linuxdeploy-plugin-gtk: https://github.com/linuxdeploy/linuxdeploy-plugin-gtk
.. _linuxdeploy-plugin-ncurses: https://github.com/linuxdeploy/linuxdeploy-plugin-ncurses
.. _linuxdeploy-plugin-gstreamer: https://github.com/linuxdeploy/linuxdeploy-plugin-gstreamer
.. _misc-plugins: https://github.com/linuxdeploy/misc-plugins


Output plugins
**************

Output plugins can be used to automatically create output formats like `AppImages <https://appimage.org>`_ from the AppDir in a single call. They can be enabled by adding :code:`--output <name>`, e.g., :code:`--output appimage`.

- linuxdeploy-plugin-appimage_

.. _linuxdeploy-plugin-appimage: https://github.com/linuxdeploy/linuxdeploy-plugin-appimage


Projects using linuxdeploy
--------------------------

Many projects use linuxdeploy already to build AppDirs (and in most cases AppImages). This is a (really incomplete) collection of example projects which showcase how to use linuxdeploy, and might serve as an inspiration for your own scripts.

- linuxdeploy_, linuxdeploy-plugin-qt_: Of course, our tools are shipped as AppImages. The scripts aren't overly interesting, you find better information in `the AppImage packaging guide <https://docs.appimage.org/packaging-guide/from-source>`_.
- Pext_, the *Python Extendable Tool*: They use linuxdeploy to create AppImages for their Python GUI software using linuxdeploy-plugin-conda_. It uses PyQt5_, which turned out to be a little problematic to bundle. However, after a lot of work, the team managed to create a `not-so-long script <https://github.com/Pext/Pext/blob/master/ci/build-appimage.sh>`_ to build AppImages. Python app developers who intend to ship their app as AppImage might find the script useful.
- Calamares_, the cross-distro installer framework: AppImage building has been added recently in the form of a `build script <https://github.com/calamares/calamares/blob/master/ci/AppImage.sh>`_ in the repository. Calamares uses Python modules for some installation tasks via boost-python_, hence there was an interest in bundling a Python interpreter via linuxdeploy-plugin-conda_. This added some complexity to the build process, though, as now, Calamares must be built against this Python distribution, and may not use the system one. If your project uses Python through some wrapper like boost-python_ and you are curious to see how to successfully build AppImages for such an application, please check out the `Calamares AppImage build script <https://github.com/calamares/calamares/blob/master/ci/AppImage.sh>`_.
- AppImageUpdate_, the efficient AppImage updating solution: AppImageUpdate provides both a Qt-based UI and a CLI tool. Both are easy to bundle into AppImages, the challenge here is to build two AppImages from one build directory. `The build script <https://github.com/AppImage/AppImageUpdate/blob/rewrite/resources/build-appimages.sh>`_ shows that it's not difficult, and may serve people in a similar situation as source for inspiration.
- MediaElch_ is a MediaManager for Kodi that provides information about movies, TV shows etc. Also works with other media centers. They use a variety of plugins to bundle their software and assemble an AppImage. Please refer to `the build script <https://github.com/Komet/MediaElch/blob/master/scripts/packaging/package.sh>`_ for more information on their usage of linuxdeploy.

.. _Pext: https://pext.io
.. _PyQt5: https://www.riverbankcomputing.com/static/Docs/PyQt5/
.. _Calamares: https://calamares.io
.. _AppImageUpdate: https://github.com/AppImage/AppImageUpdate/
.. _boost-python: https://www.boost.org/doc/libs/1_69_0/libs/python/doc/html/index.html
.. _MediaElch: https://github.com/Komet/MediaElch/


Tools using linuxdeploy
-----------------------

This section is about tools which use linuxdeploy to perform tasks, not projects using it to deploy their apps and/or distribute AppImages.

- hsinstall_ is a tool for deploying Haskell software projects into AppDir-like directories. Uses linuxdeploy to bundle dependencies and build AppImages.

.. _hsinstall: https://hackage.haskell.org/package/hsinstall
