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

.. _linuxdeploy-plugin-qt: https://github.com/linuxdeploy/linuxdeploy-plugin-qt
.. _linuxdeploy-plugin-conda: https://github.com/linuxdeploy/linuxdeploy-plugin-conda


Output plugins
**************

Output plugins can be used to automatically create output formats like `AppImages <https://appimage.org>`_ from the AppDir in a single call. They can be enabled by adding :code:`--output <name>`, e.g., :code:`--output appimage`.

- linuxdeploy-plugin-appimage_

.. _linuxdeploy-plugin-appimage: https://github.com/linuxdeploy/linuxdeploy-plugin-appimage
