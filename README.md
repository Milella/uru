## URU – Unleash Ruby (Modern Windows‑Maintained Fork)
Current Version: 0.8.6  
Maintained by: Scott Milella  
Original Author: Jon Maken (jonforums)  
License: BSD 3‑Clause

<hr>

Overview
URU is a lightweight command‑line tool that helps you manage and switch between multiple Ruby installations (MRI, JRuby, Rubinius) on a single machine. Originally created by Jon Maken, URU was designed to be a simple, cross‑platform alternative to tools like RVM, rbenv, pik, and chruby.

This repository is a modernized continuation of the original project, rebuilt and maintained by Scott Milella. The goal is to preserve Jon’s excellent work while updating the internals so URU continues to function reliably on modern Ruby versions and Windows systems.

At this time, this fork focuses primarily on Windows support, as that is the platform actively used and tested. Linux/macOS support may be revisited in the future.

<hr>

What’s New in This Fork
Migrated to Go modules (no GOPATH required)

Updated project layout following modern Go standards

Fixes for JRuby 10.x and newer Ruby version formats

Updated regex and version parsing logic

Removal of legacy Bitbucket dependencies

Cleaned and rebuilt command structure

Version bump to 0.8.6

This fork is intended to be stable, buildable, and easy to maintain going forward.

<hr>

Installation (Windows)
Prebuilt Windows binaries will be available on the GitHub Releases page.

Build From Source
bash
git clone https://github.com/milella/uru.git
cd uru
go build ./cmd/uru
This produces uru.exe.

Install URU on Windows
Place uru.exe somewhere on your PATH (e.g., C:\tools).

Run:

console
C:\tools> uru admin install
(Optional) Register an existing Ruby already on your PATH:

console
C:\tools> uru admin add system
<hr>

Usage
Once you’ve registered your Ruby installations, URU makes switching between them simple.

List installed Rubies
bash
uru ls
Switch to a Ruby
bash
uru 200p255
Switch back to system Ruby
bash
uru sys
Run a Ruby command under each registered Ruby
bash
uru ruby -e "puts 'Hello from Ruby!'"
Example Output
bash
$ uru ls
    174         : jruby 1.7.4 (1.9.3p392)
    200p255     : ruby 2.0.0p255
 => system      : ruby 2.1.0dev
<hr>

Project Structure
Code
cmd/uru          → main CLI entrypoint
internal/env     → environment detection, Ruby metadata, UI helpers
internal/command → command routing and admin operations
misc/            → packaging scripts
tasks/           → build automation
<hr>

Credits
Original Author
Jon Maken (jonforums) — creator of URU and the original implementation.

Modernization & Maintenance
Scott Milella — updated the codebase, migrated to Go modules, fixed version parsing, restored compatibility with modern Ruby/JRuby, and rebuilt the project for ongoing use.

<hr>

License
URU is distributed under the BSD 3‑Clause License, consistent with the original project.

<hr>

Status
This fork is actively maintained for Windows.
Linux/macOS support may be revisited in the future.

<hr>