#include_directories(SYSTEM ${X11_X11_INCLUDE_PATH})

set(autotype_Win32_SOURCES
    AutoTypeWin32.cpp
)

set(autotype_Win32_MOC
    AutoTypeWin32.h
)

qt4_wrap_cpp(autotype_Win32_SOURCES ${autotype_Win32_MOC})

add_library(keepassx-autotype-win32 MODULE ${autotype_Win32_SOURCES})
target_link_libraries(keepassx-autotype-win32 ${QT_QTCORE_LIBRARY} ${QT_QTGUI_LIBRARY})
install(TARGETS keepassx-autotype-x11
        BUNDLE DESTINATION . COMPONENT Runtime
        LIBRARY DESTINATION ${PLUGIN_INSTALL_DIR} COMPONENT Runtime)
