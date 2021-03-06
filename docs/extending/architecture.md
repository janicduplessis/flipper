---
id: arch
title: Architecture
---

Flipper is built to be a universal pluggable platform for development tools. Currently Flipper focuses on Android and iOS development but its design does not limit it to these platforms. Another way to think of Flipper is a more general purpose implementation of Chrome DevTools.

### Overview
Flipper consists of a desktop interface built with javascript on top of Electron so that it can be packaged to run on any operating system.

This desktop app connects over a [tcp connection](establishing-a-connection) to applications running on simulators and connected devices. An application running on a device or simulator is what we refer to as a client.

The connection is bi-directional allowing the desktop to query information from the client as well as the client to push updates directly to the desktop.

By querying data and responding to pushing from the client a Flipper plugin is able to visualize data, debug problems, and change behavior of running applications. Flipper provides the platform to build these tools on top of and does not limit what kind of tools that may be.
There are two kinds of plugins in Flipper, client plugins and desktop plugins. Client plugins expose information as an API to desktop plugins whose responsibility it is to render this information in a easy-to-digest way. Client plugins are written once for each platform in the platform's native language. Desktop plugins are written only once in JavaScript using React and consume the APIs exposed by the client plugins.
