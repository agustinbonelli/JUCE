cmake_minimum_required (VERSION 2.6)

set(PROJECT_NAME Juce)

project(${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 14)


add_definitions(-DJUCE_GLOBAL_MODULE_SETTINGS_INCLUDED)
add_definitions(-DJUCE_WEB_BROWSER=0)

include_directories( 
	modules 
	/usr/include/gtk-3.0/
	/usr/include/gtk-3.0/gdk/ 
	/usr/include/webkitgtk-3.0/ 
	/usr/include/libsoup-2.4/ 
	/usr/include/freetype2/
	/usr/include/glib-2.0/
	/usr/lib/x86_64-linux-gnu/glib-2.0/include/
	/usr/include/pango-1.0/
	/usr/include/cairo/
	/usr/include/gdk-pixbuf-2.0/
	/usr/include/atk-1.0/
	)

ADD_LIBRARY( ${PROJECT_NAME} STATIC
			modules/juce_analytics/juce_analytics.cpp
			modules/juce_audio_basics/juce_audio_basics.cpp
			modules/juce_audio_devices/juce_audio_devices.cpp
			modules/juce_audio_formats/juce_audio_formats.cpp
			modules/juce_audio_processors/juce_audio_processors.cpp
			modules/juce_audio_utils/juce_audio_utils.cpp
			modules/juce_blocks_basics/juce_blocks_basics.cpp
			modules/juce_box2d/juce_box2d.cpp			
			modules/juce_core/juce_core.cpp
			modules/juce_cryptography/juce_cryptography.cpp
			modules/juce_data_structures/juce_data_structures.cpp
			modules/juce_dsp/juce_dsp.cpp
			modules/juce_events/juce_events.cpp
			modules/juce_graphics/juce_graphics.cpp
			modules/juce_gui_basics/juce_gui_basics.cpp
			modules/juce_gui_extra/juce_gui_extra.cpp
			modules/juce_opengl/juce_opengl.cpp
			modules/juce_osc/juce_osc.cpp
			modules/juce_product_unlocking/juce_product_unlocking.cpp
			modules/juce_video/juce_video.cpp
			)

TARGET_LINK_LIBRARIES( ${PROJECT_NAME} GL Xext X11 pthread dl freetype asound curl)