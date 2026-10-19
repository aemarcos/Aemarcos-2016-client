# Aemarcos-2016-client

AEMARCOS 2016 Client Integration

A community project exploring the integration of an old Roblox Android client with the AEMARCOS game catalog and server infrastructure.

Overview

The goal of this project is to allow users to select a game, such as Neon Arena, and launch the native legacy Roblox Android client instead of playing a browser-based imitation.

The project also explores future compatibility with a self-hosted AEMARCOS server running on Termux, Ubuntu Server, or Windows Server.

Current Status

Status: Incomplete — Native Client Launch and Server Integration Are Separate Tasks

The project is not yet a fully functional standalone multiplayer platform.

Intended Features

- Launch the native legacy Roblox Android application from a game entry.
- Display games in an AEMARCOS catalog.
- Preserve the original client's own login interface where supported by the existing client.
- Explore future connections to an independently hosted AEMARCOS server.
- Support development and testing on Android devices.

«Important: Native application launching, authentication, and joining a multiplayer game are three different operations. Successfully opening the client does not mean the game has been joined.»

Why Is the Project Incomplete?

1. Legacy Client Launch

The Android application can be configured to request that Android opens the native client through an application intent.

Actual behavior depends on the installed package, Android version, intent handling, and the specific APK build. Device-level launch success has not been confirmed unless explicitly documented by a test report.

2. Multiplayer Server Compatibility

The original Roblox client was designed to communicate with Roblox's own infrastructure and protocols. An ordinary Node.js server running in Termux cannot automatically act as a compatible game server.

A working implementation would require a compatible game protocol, server-side simulation, player synchronization, and the necessary networking and session-handling components.

These parts have not been completed or verified.

3. Authentication

The original client's login interface is separate from AEMARCOS account authentication.

This project does not claim that Roblox accounts can authenticate against an AEMARCOS server. Official Roblox passwords, cookies, and session tokens must never be collected or forwarded to a third-party server.

Any future AEMARCOS account system should use its own authentication flow and securely handle its own credentials.

4. Device Testing

Compatibility must be tested on a real Android device. Successful compilation, APK signature verification, or automated tests alone do not prove that the application launches correctly or can join a multiplayer session.

Testing on the target device and documenting the results remain necessary.

Development Roadmap

- [ ] Verify that the native legacy client launches from the game catalog.
- [ ] Document the Android versions and devices tested.
- [ ] Build an independent AEMARCOS authentication system.
- [ ] Define a documented protocol for AEMARCOS multiplayer.
- [ ] Implement server-side game state and player synchronization.
- [ ] Connect the client to the compatible server.
- [ ] Test joining, disconnecting, and reconnecting to multiplayer sessions.
- [ ] Publish reproducible build and installation instructions.

Planned Server Environments

The intended server environments are:

- Termux: Android-based development and testing.
- Ubuntu Server: Dedicated hosting and backend development.
- Windows Server: An alternative hosting environment.

These are planned deployment targets, not a guarantee that the current client works with all three.

Security Notes

- Do not commit passwords, API keys, private signing keys, or session cookies.
- Do not transmit official Roblox credentials to an AEMARCOS server.
- Keep development credentials and production credentials separate.
- Only modify and distribute APKs when you have the necessary rights and permissions.
- Clearly document any third-party software and licensing restrictions.

Disclaimer

AEMARCOS is an independent community project. It is not an official Roblox product and is not endorsed by Roblox Corporation.

This repository does not claim to provide a complete replacement for Roblox's original backend or a working connection between the legacy client and an AEMARCOS multiplayer server.

The project is incomplete, and features should be considered experimental until they have been implemented and tested.

Contributions

Contributions are welcome when they improve documentation, Android compatibility, security, independent server development, or reproducible testing.

Please report verified results separately from planned features so that users can understand what currently works.
