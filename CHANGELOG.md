# Changelog

## SFML 2.4.2

Also available on the website: http://www.sfml-dev.org/changelog.php#sfml-2.4.2

  * **System**
    * (Bugfix) [Windows] Removed thread affinity changes in sf::Clock (#1107)
  * **Window**
    * (Bugfix) Fixed bug where TransientContextLock would hang (#1165, #1172)
    * (Bugfix) [Linux] Fixed GLX extensions being loaded too late (#1183)
    * (Bugfix) [Linux] Fix wrong types passed to XChangeProperty (#1168 #1171)
    * (Bugfix) [Windows] Make context disabling via wglMakeCurrent more tolerant of broken drivers (#1186)
  * **Graphics**
    * (Bugfix) Optimized sf::Image::create and made it more exception safe (#1166)

## SFML 2.4.1

Also available on the website: http://www.sfml-dev.org/changelog.php#sfml-2.4.1

  * **General**
    * [kFreeBSD] Define SFML_OS_FREEBSD when compiling for kFreeBSD (#1129)
    * [Windows] Added some simple messaging when trying to build under Cygwin (#1153)
  * **Window**
    * (Bugfix) Fixed stack overflow on GlContext creation with multiple threads (#989, #1002)
    * (Bugfix) Adjusted mouse cursor grab documentation (#1133)
    * (Bugfix) [iOS] Fixed orientation change not rescaling window size properly (#1049, #1050)
    * (Bugfix) [Linux] Fixed fullscreen issue (#921, #1138)
    * (Bugfix) [Linux] Switched from XCB back to Xlib for windowing (#1138)
    * (Bugfix) [Linux] Fixed window icon not showing up on some distros (#1087, #1088)
    * (Bugfix) [Linux] Fixed an issue where GNOME flags window unresponsive (#1089, #1138)
    * (Bugfix) [Linux] Fixed leak of XVisualInfo objects during GlxContext creation (#1135)
    * (Bugfix) [Linux] Fixed possible hang when setting visibility if external window sources (#1136)
    * (Bugfix) [OS X] Fixed inconsistency between doc and impl on OS X for the grab feature (#1133, #1148, #1150)
    * (Bugfix) [Windows] Fixed context memory leaks (#1143, #1002)
  * **Graphics**
    * (Bugfix) Adjusted uniform error message (#1131)
    * (Bugfix) Clarify documentation on Rect::contains function bounds (#1151)
  * **Network**
    * (Bugfix) Fixed a typo in comment for void unbind() (#1121)

## SFML 2.4.0

Also available on the website: http://www.sfml-dev.org/changelog.php#sfml-2.4.0

  * **General**
    * Added deprecation macro (#969)
    * Fixed issues reported by Coverity Scan static analysis (#1064)
    * Fixed some initialization issues reported by Cppcheck (#1008)
    * Changed comment chars in FindSFML.cmake to # (#1090)
    * Fixed some typos (#1098, #993, #1099, #956, #963, #979)
    * Updated/fixed string comparisons in Config.cmake (#1102)
    * Added the missing -s postfix for the RelWithDebInfo config (#1014)
    * [Android] Fixed current Android compilation issues (#1116, #1111, #1079)
    * [OS X] Update Xcode template material (#976, #968)
    * [Windows] Added support for VS 2015 (#972)
    * [Windows] Create and install PDB debug symbols alongside binaries (#1037)
  * **Deprecated API**
    * sf::RenderWindow::capture(): Use a sf::Texture and its sf::Texture::update(const Window&) function and copy its contents into an sf::Image instead.
    * sf::Shader::setParameter(): Use setUniform() instead.
    * sf::Text::getColor(): There is now fill and outline colors instead of a single global color. Use getFillColor() or getOutlineColor() instead.
    * sf::Text::setColor(): There is now fill and outline colors instead of a single global color. Use setFillColor() or setOutlineColor() instead.
    * sf::LinesStrip: Use LineStrip instead.
    * sf::TrianglesFan: Use TriangleFan instead.
    * sf::TrianglesStrip: Use TriangleStrip instead.
  * **System**
    * (Feature) [Android] Added sf::getNativeActivity() (#1005, #680)
    * (Bugfix) Added missing <iterator> include in String.hpp (#1069, #1068)
    * (Bugfix) Fixed encoding of UTF-16 (#997)
    * (Bugfix) [Android] Fixed crash when trying to load a non-existing font file (#1058)
  * **Window**
    * (Feature) Added ability to grab cursor (#614, #394, #1107)
    * (Feature) Added Multi-GPU preference (#869, #867)
    * (Feature) Added support for sRGB capable framebuffers (#981, #175)
    * (Feature) [Linux, Windows] Improved OpenGL context creation (#884)
    * (Feature) [Linux, Windows] Added support for pbuffers on Windows and Unix (#885, #434)
    * (Bugfix) Updated platform-specific handle documentation (#961)
    * (Bugfix) [Android] Accept touch events from "multiple" devices (#954, #953)
    * (Bugfix) [Android] Copy the selected EGL context's settings to SFML (#1039)
    * (Bugfix) [Linux] Fixed modifiers causing sf::Keyboard::Unknown being returned (#1022, #1012)
    * (Bugfix) [OS X] Improved memory management on OS X (#962, #790)
    * (Bugfix) [OS X] Fixed crash when resizing a window to a zero-height/width size (#986, #984)
    * (Bugfix) [OS X] Use the mouse button constant instead of 0 to avoid a compiler error on OSX (#1035)
    * (Bugfix) [OS X] OS X improvement: warnings + bugfix + refactoring, the lot! (#1042)
  * **Graphics**
    * (Feature) Added support for outlined text (#840)
    * (Feature) Add support for geometry shaders (#886, #428)
    * (Feature) Feature/blend mode reverse subtract (#945, #944)
    * (Feature) Implemented support for mipmap generation (#973, #498, #123)
    * (Feature) Added new API to set shader uniforms (#983, #538)
    * (Feature) Rewrite RenderWindow::capture (#1001)
    * (Bugfix) Exporting some Glsl utility functions due to linking issues (#1044, #1046)
    * (Bugfix) Fixed missing initialisation of Font::m_stroker (#1059)
    * (Bugfix) Changed primitive types to be grammatically correct (#1095, #939)
  * **Audio**
    * (Feature) Implemented stereo audio recording (#1010)
    * (Bugfix) Added an assignment operator to SoundSource (#864)
    * (Bugfix) [OS X] Updates OpenAL-soft for OS X to version 1.17.2 (#1057, #900, #1000)
    * (Bugfix) Fixed a bug where vorbis can't handle large buffers (#1067)
    * (Bugfix) Added support for 24-bit .wav files (#958, #955)
    * (Bugfix) Fixed threading issue in sf::SoundRecorder (#1011)
    * (Bugfix) Made WAV file reader no longer assume that data chunk goes till end of file to prevent reading trailing metadata as samples (#1018)
    * (Bugfix) Fixed seeking in multi channel FLAC files (#1041, #1040)
  * **Network**
    * (Feature) Added optional argument on which address to bind (socket). (#850, #678)
    * (Bugfix) Fixed FTP directory listing blocking forever (#1086, #1025)

## SFML 2.3.2

Also available on the website: http://www.sfml-dev.org/changelog.php#sfml-2.3.2

  * **General**
    * Fixed an issue where FindSFML.cmake couldn't find older versions of SFML (#903)
    * Robust alCheck and glCheck macros (#917)
    * Fixed FindSFML.cmake to use the uppercase FLAC name (#923)
    * Added a CONTRIBUTING file so GitHub shows a message when creating a new issue (#932)
  * **Window**
    * (Bugfix) [Linux] Fixed an issue where the keypad's key weren't being detected (#910)
    * (Bugfix) [Linux] Revert to Xlib event handling (#934)
    * (Bugfix) [Linux] Fixed `XK_*` inconsistency in InpuImpl.cpp (#947)
    * (Bugfix) [Linux] Fix `_NET_WM_PING` messages not being replied to properly (#947)
  * **Graphics**
    * (Bugfix) Fixed clear bug on RenderTextures (#915)
    * (Bugfix) Fixed image file extension detection (#929, #930, #931)
    * (Bugfix) Secure function against random data return (#935, #942)

## SFML 2.3.1

Also available on the website: http://www.sfml-dev.org/changelog.php#sfml-2.3.1

  * **Window**
    * (Bugfix) [Android] Make sure a window still exists before trying to access its dimensions (#854)
    * (Bugfix) [Android] Added Android API level checks (#856)
    * (Bugfix) [Android] Updated the JNI/event handling code (#906)
    * (Bugfix) [Linux] Resized events are only spawned when the window size actually changes (#878, #893)
    * (Bugfix) [Linux] Whitelisted X SHAPE events (#879, #883)
    * (Bugfix) [Linux] Remap Unix keyboard when user changes layout (#895, #897)
    * (Bugfix) [Linux] Fix undefined behavior in ewmhSupported() (#892, #901)
  * **Graphics**
    * (Bugfix) Added support for GL_EXT_texture_edge_clamp for systems that don't expose GL_SGIS_texture_edge_clamp (#880, #882)
  * **Audio**
    * (Bugfix) [Android] Fixed audio files not loading (and possibly crashing) (#855, #887)

## SFML 2.3

Also available on the website: http://www.sfml-dev.org/changelog.php#sfml-2.3

  * **General**
    * Examples only link against sfml-main in release mode (#610, #766)
    * Replaced unsigned int with std::size_t for array indices and sizes (#739)
    * Fixed some issues with the Doxygen documentation (#750)
    * Added support for EditorConfig (#751)
    * Hide success message for CMake in quiet mode (#753)
    * Improved documentation for statuses with sf::Ftp (#763)
    * Moved stb_image into the extlibs directory (#795)
    * Changed the SOVERSION to major.minor (#812)
    * Fixed warnings about switch-statements (#863)
    * Added missing includes in the general headers (#851)
    * [Android] Updated toolchain file and dependencies (#791)
    * [Linux] Fixed missing pthread dependency (#794)
    * [OS X] Relaxed CMake installation rules regarding framework dependencies (#767)
  * **Deprecated API**
    * sf::Event::MouseWheelEvent: This event is deprecated and potentially inaccurate. Use MouseWheelScrollEvent instead.
  * **Window**
    * (Feature) Added new events for handling high-precision scrolling (#95, #810, #837)
    * (Feature) Switched from Xlib to XCB (#200, #319, #694, #780, #813, #825)
    * (Feature) Added support for OpenGL 3 core context creation (#654, #779)
    * (Bugfix) Fixed glXSwapIntervalSGI being broken for some driver implementations (#727, #779)
    * (Bugfix) Fixed simultaneous context operations causing crashes on some AMD hardware (#778, #779)
    * (Bugfix) Fixed joystick identification (#809, #811)
    * (Bugfix) [iOS] Fixed various issues including stencil bits, device orientation and retina support (#748)
    * (Bugfix) [iOS] Fixed inconsistency between sf::Touch::getPosition and touch events (#875)
    * (Bugfix) [Linux] Fixed Alt+F4 not getting triggered in window mode (#274)
    * (Bugfix) [Linux] Fixed Unix joystick stuff (#838)
    * (Bugfix) [OS X] Fixed typo in JoystickImpl.cpp to prevent a crash (#762, #765)
    * (Bugfix) [OS X] Fixed an issue in InputImpl::getSFOpenGLViewFromSFMLWindow (#782, #792)
  * **Graphics**
    * (Feature) Replaced GLEW with loader generated by glLoadGen (#779)
    * (Feature) Added a new constructor to sf::Color that takes an sf::Uint32 (#722)
    * (Feature) Updated stb_image to v2.02 (#777)
    * (Feature) Updated FreeType to v2.5.5 (#799, #804)
    * (Feature) Added checks for software OpenGL (#870)
    * (Bugfix) Fixed GL_ARB_compatibility not being detected (#859)
    * (Bugfix) Fixed pixel format selection (#862)
    * (Bugfix) Bumped back the OpenGL version requirement to 1.1 (#858)
  * **Audio**
    * (Feature) Dropped libsndfile and started using Vorbis, FLAC and OGG directly (#604, #757)
    * (Feature) Added a FLAC file to the sound example (#815)
    * (Bugfix) Fixed access violation error in the destructor of sf::AudioDevice (#30, #602)
    * (Bugfix) [OS X] Fixed threading issue with sf::SoundStream and OpenAL (#541, #831)
  * **Network**
    * (Bugfix) Fixed sf::TcpSocket not handling partial sends properly (#749, #796)

## SFML 2.2

Also available on the website: http://www.sfml-dev.org/changelog.php#sfml-2.2

  * **General**
    * Support for iOS and Android platform (#410, #440)
    * Various documentation corrections (#438, #496, #497, #714)
    * Fixed support for compilers on Debian FreeBSD (#380, #578)
    * Added support for Visual Studio 2013 and proper support for the TDM builds (#482)
    * Fixed CMake problems related to FindSFML and cached variables (#637, #684)
    * Switched and enforced LF line endings (#708, #712)
    * Updated OpenAL to version 1.15.1 (d077210)
    * Made compiler and OS variable names much clearer in CMake files (9b0ed30)
    * Re-enabled RPATH feature (e157e7a)
    * Slight adjustments to the examples (#737)
    * [FreeBSD] Various configuration fixes (#577, #578)
    * [Linux] Updated FindSFML.cmake to add UDev to SFML's dependencies (#728, #729, #734, #736)
    * [OS X] Fixed incorrect symlink in freetype.framework (#519)
    * [OS X] CMake module for correct dependencies (#548)
    * [OS X] Fixed SFML target for Xcode (#595, #596)
    * [OS X] Updated implementation, mainly reverting to non-ARC (#601)
    * [OS X] Fixed memory leaks and dead store (#615)
    * [OS X] Improved event handling and performance (#617)
    * [OS X] Reduced memory usage (#672, #698)
    * [OS X] OS X 10.10 support (#691, #699)
    * [OS X] Improve flexibility of dependencies' locations (#713)
    * [Windows] Removed the hack that copied external libraries into SFML static libraries (dbf01a7)
  * **System**
    * (Feature) Added substring and replace functions to sf::String (#21, #355)
    * (Feature) Added toUtfX to sf::String (#501)
    * (Feature) Added fromUtfX functions to set the internal data to a string by converting from another string in a fixed encoding (#196)
    * (Feature) Added modulo operator for sf::Time (#429, #430)
    * (Feature) Added division operator for sf::Time (#453)
    * (Bugfix) Ensured a high resolution for sf::sleep (#439, #475)
    * (Bugfix) [Windows] Fixed stack unalignment by two internal functions (#412)
  * **Window**
    * (Feature) Added window methods to request and to check focus (#518, #525, #613, #723, #735)
    * (Feature) Provide name, manufacturer ID and product ID via sf::Joystick (#152, #528)
    * (Feature) [FreeBSD] Joystick support (#477)
    * (Feature) [OS X] Improved integration with menus and dock actions (#11)
    * (Feature) [OS X] Support for OpenGL 3.2 (#84)
    * (Feature) [OS X] Improved fullscreen support (#343)
    * (Feature) [OS X] Added support for retina displays (#353, #388)
    * (Feature) [Windows] Removed support for Windows 9x (#469)
    * (Feature) [Windows] Fixed typo in Windows keyboard implementation (#516)
    * (Bugfix) sf::Window::create() now also resets framerate limit (#371)
    * (Bugfix) Fixed OpenGL context leak (#635, #705)
    * (Bugfix) Fixed various joystick problems (memory leak, accelerometer detected, code refactoring) (#660, #686, #742, #743)
    * (Bugfix) Optimized sf::Window::waitEvent a bit, no sleep if events are available at first try (ff555d6)
    * (Bugfix) [Linux] Output error message when XOpenDisplay() fails (#508, #616)
    * (Bugfix) [Linux] Resize window with setSize when sf::Style::Resize is set (#466)
    * (Bugfix) [Linux] Fixed broken key repeat on window recreation (#564, #567)
    * (Bugfix) [OS X] Fixed KeyReleased not being fired in fullscreen mode (#465)
    * (Bugfix) [OS X] Fixed an issue where disconnecting the keyboard would cause a crash (#467)
    * (Bugfix) [OS X] Fixed unexpected resizing behavior (#468)
    * (Bugfix) [OS X] Improved resizing windows (#474)
    * (Bugfix) [OS X] Fixed memory leak with sf::Window::create() (#484)
    * (Bugfix) [OS X] Fixed menu shortcuts in fullscreen on OS X (#527)
    * (Bugfix) [OS X] Improved cursor hiding (#703)
    * (Bugfix) [OS X] Fixed right click not detected with trackpads (#716, #730)
    * (Bugfix) [Windows] Fixed joystick POV values (ef1d29b)
    * (Bugfix) [Windows] Fixed Unicode inconsistency (#635)
    * (Bugfix) [Windows] Fixed Alt+F4 and mouse clicks issues (#437, #457)
    * (Bugfix) [Windows] Send MouseButtonReleased event when the mouse is outside of the window (#455, #457)
    * (Bugfix) [Windows] Fixed sf::Joystick wrong registry usage (#701, #702, #706)
  * **Graphics**
    * (Feature) Provide more information about the loaded font in sf::Font (#164)
    * (Feature) Implemented a more flexible blending system (#298)
    * (Feature) Added strikethrough text style (#243, #362, #682)
    * (Feature) Slight optimization for sf::Text::setString (#413)
    * (Feature) Added subtraction operator for sf::Color (#114, #145)
    * (Feature) Optimized sf::Image::flipVertically/flipHorizontally (#555)
    * (Feature) Changed sf::Font measurements from int to float to allow better underline drawing (#693)
    * (Bugfix) Improved text quality for small and pixelated fonts (#228)
    * (Bugfix) Yet another fix for Intel GPUs with sf::RenderTexture (#418)
    * (Bugfix) Removed VTab since it causes issues and doesn't have a use nowadays (#442, #445, #460, #588)
    * (Bugfix) Fixed broken BDF and PCF font formats (#448)
    * (Bugfix) Fixed compilation issue with newer versions of GCC for sf::Rect (#458)
    * (Bugfix) Fixed resetGLStates() not explicitly setting the default polygon mode (#480)
    * (Bugfix) Fixed division-by-zero in sf::RectangleShape (#499)
    * (Bugfix) Fixed potential memory leak in sf::Font (#509)
    * (Bugfix) Updated glext and removed glxext (#511, #583)
    * (Bugfix) Make sure texture unit 0 is active when resetting sf::RenderTarget states (#523, #591)
    * (Bugfix) Fixed texture rect computation in fonts (#669)
    * (Bugfix) Improved rendering of underlined text (#593)
    * (Bugfix) Avoided repeated output of error messages (#566)
    * (Bugfix) Fixed text rendered with vertical offset on ascent and font size mismatch (#576)
    * (Bugfix) Fixed rounding problem for viewports (#598)
    * (Bugfix) Fixed sf::Shader::isAvailable() possibly breaking context management (#211, #603, #608, #603)
    * (Bugfix) Fixed sf::Texture::getMaximumSize() possibly breaking context management (#666)
    * (Bugfix) Fixed various sf::Text rendering issues (#692, #699)
    * (Bugfix) The texture matrix is now reset in sf::Texture::bind(NULL) (7c4b058)
    * (Bugfix) [Windows] Fixed DPI scaling causing strange window behavior (#679, #681, #688)
  * **Audio**
    * (Feature) Added support for selecting the audio capture device (#220, #470)
    * (Feature) Make sf::SoundRecorder processing frequency configurable (#333)
    * (Feature) Added up vector to sf::Listener (#545)
    * (Bugfix) Prevented sf::SoundStream::setPlayingOffset() from restarting playing even when paused (#203, #592)
    * (Bugfix) Fixed sf::SoundBuffer contents not being able to be updated when still attached to sounds (#354, 367, #390, #589)
    * (Bugfix) Catch audio format error and prevent division by zero (#529)
    * (Bugfix) Fixed sf::SoundBuffer returning wrong duration for sounds containing more than ~4.3 million samples (2ff58ed)
    * (Bugfix) Optimized sf::Listener with a cache (d97e524)
  * **Network**
    * (Feature) Added support for PUT and DELETE in sf::Http (#257, #312, #607)
    * (Feature) Added support for chunked HTTP transfers (#296, #337)
    * (Feature) Added support for 64-bit integers in sf::Packet (#710)
    * (Feature) Made sf::Ftp::sendCommand() public (2c5cab5)
    * (Bugfix) Checked socket descriptor limit (#153, #628, #683)
    * (Bugfix) Fixed sf::TcpSocket::connect()'s switching from blocking to non-blocking mode on immediate connection success (#221)
    * (Bugfix) Fixed FTP download and upload file sizes being limited by available RAM (#565, #590)
    * (Bugfix) Fixed C++11 compiler warnings for sf::Uint8 (#731, #732)

## SFML 2.1

Also available on the website: http://www.sfml-dev.org/changelog.php#sfml-2.1

  * **General**
    * Updated the Window and OpenGL examples (got rid of GLU and immediate mode)
  * **Window**
    * (Feature) Now using inotify on Linux to avoid constantly polling joystick connections (#96)
    * (Feature) Add keypad return, equal and period keys support for OS X
    * (Feature) Improved mouse events on OS X regarding fullscreen mode
    * (Feature) Improved mouse events on OS X (#213, #277)
    * (Feature) Improved reactivity of setMousePosition on OS X (#290)
    * (Feature) Added support for right control key on OS X
    * (Feature) Improved TextEntered for OS X (#377)
    * (Feature) Improved the performances of Window::getSize() (the size is now cached)
    * (Feature) Added the WM_CLASS property to SFML windows on Linux
    * (Feature) Fake resize events are no longer sent when the window is moved, on Linux
    * (Feature) Pressing ALT or F10 on Windows no longer steals the focus
    * (Bugfix) Fixed MouseMove event sometimes not generated when holding left button on Windows (#225)
    * (Bugfix) Fixed ContextSettings ignored when creating a 3.x/4.x OpenGL context on Linux (#258)
    * (Bugfix) Fixed ContextSettings ignored on Linux when creating a window (#35)
    * (Bugfix) Fixed windows bigger than the desktop not appearing on Windows (#215)
    * (Bugfix) Fixed KeyRelease events sometimes not reported on Linux (#404)
    * (Bugfix) Fixed mouse moved event on OS X when dragging the cursor (#277)
    * (Bugfix) Fixed KeyRelease event with CMD key pressed (#381)
    * (Bugfix) Fixed taskbar bugs on Windows (#328, #69)
    * (Bugfix) Fixed Window::getPosition() on Linux (#346)
    * (Bugfix) Unicode characters outside the BMP (> 0xFFFF) are now correctly handled on Windows (#366)
  * **Graphics**
    * (Feature) Checking errors in RenderTarget::pushGLStates() to avoid generating false error messages when user leaves unchecked OpenGL errors (#340)
    * (Feature) Optimized Shader::setParameter functions, by using a cache internally (#316, #358)
    * (Bugfix) Fixed bounding rect of sf::Text ignoring whitespaces (#216)
    * (Bugfix) Solved graphics resources not updated or corrupted when loaded in a thread (#411)
    * (Bugfix) Fixed white pixel showing on first character of sf::Text (#414)
    * (Bugfix) sf::Rect::contains and sf::Rect::intersects now handle rectangles with negative dimensions correctly (#219)
    * (Bugfix) Fixed Shape::setTextureRect not working when called before setTexture
  * **Audio**
    * (Feature) loadFromStream functions now explicitly reset the stream (seek(0)) before starting to read (#349)
    * (Bugfix) Added a workaround for a bug in the OS X implementation of OpenAL (unsupported channel count no properly detected) (#201)
    * (Bugfix) Fixed SoundBuffer::loadFromStream reading past the end of the stream (#214)
  * **Network**
    * (Feature) Replaced the deprecated gethostbyname with getaddrinfo (#47)
    * (Feature) Minor improvements to sf::Packet operators (now using strlen and wcslen instead of explicit loops) (#118)
    * (Bugfix) Fixed non-blocking connection with a sf::TcpSocket on Windows
    * (Bugfix) Fixed TCP packet data corruption in non-blocking mode (#402, #119)
    * (Bugfix) On Unix systems, a socket disconnection no longer stops the program with signal SIGPIPE (#72)

## SFML 2.0

Also available on the website: http://www.sfml-dev.org/changelog.php#sfml-2.0

No changelog available. *Everything changed.*

# Older Releases

See the website for changelogs of older releases: http://www.sfml-dev.org/changelog.php
