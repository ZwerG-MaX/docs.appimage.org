Different ways to create AppImages
==================================

There are different ways to create AppImages:

#. Use Open Build Service (OBS)
#. Convert existing binary packages (.deb, .rpm, ...)
#. Bundling your Travis CI builds as AppImages
#. Run :code:`linuxdeployqt` on your Qt application
#. Using :code:`electron-builder` for Electron-based apps
#. Create an AppDir manually


1. Using the Open Build Service
-------------------------------

This option is recommended for open source projects because it allows you to leverage the existing Open Build Service infrastructure, security and license compliance processes. See `Using the Open Build Service <obs.html>`_ for how to use this.


2. Converting existing binary packages using pkg2appimage
---------------------------------------------------------

This option might be the easiest if you already have up-to-date packages in place, ideally a ppa for trusty or earlier or a debian repository for oldstable. In this case, you can write a small :code:`.yml` recipe and in many cases are done with the package to AppImage conversion. See `pkg2appimage <pkg2appimage.html>`_.


3. Bundling your Travis CI builds as AppImages
----------------------------------------------

This option might be the easiest if you already have continuous builds on Travis CI in place. In this case, you can write a small scriptfile and in many cases are done with the AppImage generation (`See examples <https://github.com/search?utf8=%E2%9C%93&q=%22Package+the+binaries+built+on+Travis-CI+as+an+AppImage%22&type=Code&ref=searchresults>`_).


4. Runing linuxdeployqt
-----------------------

This option might be the easiest if you build your application from source code using using :code:`cmake`, :code:`qmake`, or :code:`make`, and/or if you have a Qt-based application. In the latter case, you are probably already using :code:`windeployqt` and :code:`macdeployqt` and now can use :code:`linuxdeployqt` in the same fashion with the :code:`-appimage` argument and in many cases are done with the AppImage generation (`See example <https://github.com/coryo/amphetype2/blob/2d41de3b0c19ab9286672ff0d6a7c11eadc13d9c/.travis/deploy.sh>`_).


5. Using electron-builder
-------------------------

This option might be the easiest if you have an Electron-based application. In this case, you define AppImage as a target for Linux (default in the latest version of electron-builder) and in many cases are done with the AppImage generation (`See examples <https://github.com/search?utf8=%E2%9C%93&q=electron-builder+linux+target+appimage&type=Code&ref=searchresults>`_).


6. Manually creating an AppDir
------------------------------

Create an AppDir manually, then turn it into an AppImage. See `Manually creating an AppDir <manual.html>`_. Please note that this method should only be your last resort, as the other methods are much more convenient in most cases. Manually creating an AppDir is explained mainly to illustrate how things work under the hood.
