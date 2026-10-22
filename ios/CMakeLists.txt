cmake_minimum_required(VERSION 3.20)
project(sr_ios LANGUAGES C CXX OBJC OBJCXX)
set(CMAKE_CXX_STANDARD 17)
add_executable(sr_ios MACOSX_BUNDLE main.mm SRIcon.png)
set_source_files_properties(SRIcon.png PROPERTIES MACOSX_PACKAGE_LOCATION "Resources")
target_link_libraries(sr_ios PRIVATE
  "-framework UIKit" "-framework Foundation" "-framework AVFoundation" "-framework UniformTypeIdentifiers" "-framework MediaPlayer" "-framework CoreGraphics" "-framework AudioToolbox")
set_target_properties(sr_ios PROPERTIES
  MACOSX_BUNDLE TRUE
  MACOSX_BUNDLE_INFO_PLIST "${CMAKE_CURRENT_SOURCE_DIR}/Info.plist.in"
  MACOSX_BUNDLE_BUNDLE_NAME "S&R"
  MACOSX_BUNDLE_ICON_FILE "SRIcon.png"
  MACOSX_BUNDLE_GUI_IDENTIFIER "com.kaoxsk.sr"
  MACOSX_BUNDLE_BUNDLE_VERSION "7"
  MACOSX_BUNDLE_SHORT_VERSION_STRING "0.7-beta"
  XCODE_ATTRIBUTE_PRODUCT_NAME "S&R"
  XCODE_ATTRIBUTE_PRODUCT_BUNDLE_IDENTIFIER "com.kaoxsk.sr"
  XCODE_ATTRIBUTE_CODE_SIGNING_ALLOWED "NO"
  XCODE_ATTRIBUTE_TARGETED_DEVICE_FAMILY "1,2")
