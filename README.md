# cross_platform_system_info

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.


## windows build require fix explained here

https://github.com/fluttercommunity/plus_plugins/issues/202

https://github.com/fluttercommunity/plus_plugins/issues/193

Path: example\windows\flutter\ephemeral\.plugin_symlinks\network_info_plus_windows\windows\network_info_plus_windows_plugin.cpp

Change

#include "include/network_info_plus_windows/network_info_plus_windows_plugin.h"

#include <flutter/method_channel.h>
#include <flutter/plugin_registrar_windows.h>
#include <flutter/standard_method_codec.h>

#include "include/network_info_plus_windows/network_info.h"
To

#include "include/network_info_plus_windows/network_info.h"
#include "include/network_info_plus_windows/network_info_plus_windows_plugin.h"

#include <flutter/method_channel.h>
#include <flutter/plugin_registrar_windows.h>
#include <flutter/standard_method_codec.h>
Path: example\windows\flutter\ephemeral\.plugin_symlinks\network_info_plus_windows\windows\include\network_info_plus_windows\network_info.h

Change

#include <windows.h>
#include <winerror.h>
#include <winsock2.h>
#include <wlanapi.h>
To

#include <winsock2.h>
#include <windows.h>
#include <winerror.h>
#include <wlanapi.h>