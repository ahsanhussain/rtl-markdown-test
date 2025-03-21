  ![](media/image1.png)**SIEMENS EDA**
 
  **Innexis™ Linux® User’s and Reference Manual**
 
  Software Version 2025.1.0
 
  Unpublished work. © 2025 Siemens
 
  This Documentation contains trade secrets or otherwise confidential
  information owned by Siemens Industry Software Inc. or its affiliates
  (collectively, “Siemens”), or its licensors. Access to and use of this
  Documentation is strictly limited as set forth in Customer’s
  applicable agreement(s) with Siemens. This Documentation may not be
  copied, distributed, or otherwise disclosed by Customer without the
  express written permission of Siemens, and may not be used in any way
  not expressly authorized by Siemens.
 
  This Documentation is for information and instruction purposes.
  Siemens reserves the right to make changes in specifications and other
  information contained in this Documentation without prior notice, and
  the reader should, in all cases, consult Siemens to determine whether
  any changes have been made.
 
  No representation or other affirmation of fact contained in this
  publication shall be deemed to be a warranty or give rise to any
  liability of Siemens whatsoever.
 
  If you have a signed license agreement with Siemens for the product
  with which this Documentation will be used, your use of this
  Documentation is subject to the scope of license and the software
  protection and security provisions of that agreement. If you do not
  have such a signed license agreement, your use is subject to the
  Siemens Universal Customer Agreement, which may be viewed
 
  at
  [**https://www.sw.siemens.com/en-US/sw-terms/base/uca/**](https://www.sw.siemens.com/en-US/sw-terms/base/uca/),
  as supplemented by the product specific terms which may be viewed at
 
  [**https://www.sw.siemens.com/en-US/sw-terms/supplements/**](https://www.sw.siemens.com/en-US/sw-terms/supplements/).
 
  SIEMENS MAKES NO WARRANTY OF ANY KIND WITH REGARD TO THIS
  DOCUMENTATION INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND
  NON-INFRINGEMENT OF INTELLECTUAL PROPERTY. SIEMENS SHALL NOT BE LIABLE
  FOR ANY DIRECT, INDIRECT, INCIDENTAL, CONSEQUENTIAL OR PUNITIVE
  DAMAGES, LOST DATA OR PROFITS, EVEN IF SUCH DAMAGES WERE FORESEEABLE,
  ARISING OUT OF OR RELATED TO THIS DOCUMENTATION OR THE INFORMATION
  CONTAINED IN IT, EVEN IF SIEMENS HAS BEEN ADVISED OF THE POSSIBILITY
  OF SUCH DAMAGES.
 
  **TRADEMARKS:** The trademarks, logos, and service marks
  (collectively, "Marks") used herein are the property of Siemens or
  other parties. No one is permitted to use these Marks without the
  prior written consent of Siemens or the owner of the Marks, as
  applicable. The use herein of third party Marks is not an attempt to
  indicate Siemens as a source of a product, but is intended to indicate
  a product from,
 
  or associated with, a particular third party. A list of Siemens' Marks
  may be viewed at:
  **[https://www.plm.automation.siemens.com/](https://www.plm.automation.siemens.com/global/en/legal/trademarks.html)
  [global/en/legal/trademarks.html](https://www.plm.automation.siemens.com/global/en/legal/trademarks.html)**.
  The registered trademark Linux® is used pursuant to a sublicense from
  LMI, the exclusive licensee of Linus Torvalds, owner of the mark on a
  world-wide basis.

## About Siemens Digital Industries Software

  Siemens Digital Industries Software is a global leader in the growing
  field of product lifecycle management (PLM), manufacturing operations
  management (MOM), and electronic design automation (EDA) software,
  hardware, and services. Siemens works with more than 100,000
  customers, leading the digitalization of their planning and
  manufacturing processes. At Siemens Digital Industries
 
  Software, we blur the boundaries between industry domains by
  integrating the virtual and physical, hardware and software, design
  and manufacturing worlds. With the rapid pace of innovation,
  digitalization is no longer tomorrow’s idea. We take what the future
  promises tomorrow and make it real for our customers today. Where
  today meets tomorrow. Our culture encourages creativity, welcomes
  fresh thinking and focuses on growth, so our people, our business, and
  our customers can achieve their full potential.
 
  Support Center:
  [**https://support.sw.siemens.com**](https://support.sw.siemens.com/)
 
  Send Feedback on Documentation:
  [**https://support.sw.siemens.com/doc_feedback_form**](https://support.sw.siemens.com/doc_feedback_form)
 
  **Table of Contents**

[Introduction 1-1](#introduction)

  [Syntax Conventions 1-2](#syntax-conventions)
 
  [Product Support 1-2](#product-support)
 
  [Build System Overview 1-3](#build-system-overview)
 
  [BitBake Operation 1-4](#_bookmark6)

[Software Manifest Files 1-4](#software-manifest-files)

[bitbake. 1-6](#bitbake)

[setup-environment Script 1-9](#setup-environment-script)

[setup-environment. 1-10](#setup-environment)

  [Yocto Project Documentation 1-11](#yocto-project-documentation)

[OS Images 2-1](#os-images-1)

  [Prepare the Workspace for a Build
  2-1](#prepare-the-workspace-for-a-build)
 
  [Set Up the Build Environment 2-3](#set-up-the-build-environment)
 
  [Build the Target Image 2-4](#build-the-target-image)
 
  [Build Customization 2-5](#build-customization)

[Shared State Caches. 2-7](#shared-state-caches)

[Set Up Parallel Builds. 2-7](#set-up-parallel-builds)

[Image Features Settings 2-7](#image-features-settings)

[Distribution Features. 2-9](#distribution-features)

[Virtual Platform BSPs. 3-1](#virtual-platform-bsps)

[Innexis Hybrid 3-1](#innexis-hybrid)

[Build Configuration for Innexis Hybrid
3-2](#build-configuration-for-innexis-hybrid)

[Set Up an Innexis Hybrid Workspace.
3-3](#set-up-an-innexis-hybrid-workspace)

[Run the Innexis Linux Image With Innexis Hybrid
3-5](#run-the-innexis-linux-image-with-innexis-hybrid-1)

[Benchmarks. 3-7](#benchmarks)

[Features for Innexis Hybrid. 3-8](#features-for-innexis-hybrid)

[IDE Connection Configuration for Innexis Hybrid
3-31](#ide-connection-configuration-for-innexis-hybrid)

  [Innexis Architecture Native Acceleration
  3-33](#innexis-architecture-native-acceleration)

[Build Configuration for ANA. 3-33](#build-configuration-for-ana)

[Run the Innexis Linux Image in the ANA Arm64 Environment.
3-34](#run-the-innexis-linux-image-in-the-ana-arm64-environment)

[Features for ANA. 3-37](#features-for-ana)

[IDE Connection Configuration for Innexis ANA
3-61](#ide-connection-configuration-for-innexis-ana)

[Adding and Modifying Packages and Recipes
4-1](#adding-and-modifying-packages-and-recipes)

  [Innexis Linux Layout 4-1](#innexis-linux-layout)
 
  [Layers. 4-2](#_bookmark94)

[Create a Layer 4-3](#_bookmark96)

[Enable a Layer. 4-5](#_bookmark97)

[Prioritize a Layer. 4-6](#prioritize-a-layer)

[Recipes 4-6](#_bookmark99)

[Simple Recipe File. 4-7](#simple-recipe-file)

[Package Groups 4-8](#package-groups)

[Add Recipe Artifacts to the Image 4-8](#_bookmark103)

[Create a HelloDemo Package 4-9](#_bookmark104)

[Append Files. 4-11](#append-files)

[Modify an Existing Package (Adding a Patch) 4-12](#_bookmark106)

[Use a Custom BusyBox Configuration
4-14](#use-a-custom-busybox-configuration-1)

[Rebuild a Package for a Project That Uses a Cached Binary Mirror
4-15](#rebuild-a-package-for-a-project-that-uses-a-cached-binary-mirror)

[Application Development 5-1](#application-development)

[Software Development Kit 5-1](#software-development-kit)

[Build a Yocto Project SDK 5-1](#build-a-yocto-project-sdk)

[SDK Build Customization 5-2](#sdk-build-customization)

[Managing Embedded Linux SDKs 5-2](#managing-embedded-linux-sdks)

[Install the SDK Using the Innexis CodeBench IDE.
5-3](#install-the-sdk-using-the-innexis-codebench-ide)

[Install the SDK From the Command Line
5-4](#install-the-sdk-from-the-command-line)

[Uninstall the Yocto Project SDK Using Innexis CodeBench.
5-5](#uninstall-the-yocto-project-sdk-using-innexis-codebench)

[Add an Existing SDK to the Innexis CodeBench IDE
5-6](#add-an-existing-sdk-to-the-innexis-codebench-ide)

[Innexis CodeBench IDE. 5-7](#innexis-codebench-ide)

[Create a Project Using an SDK 5-7](#create-a-project-using-an-sdk-2)

[Create a Makefile Project Using an SDK
5-8](#create-a-makefile-project-using-an-sdk)

[Build a Project. 5-9](#build-a-project)

[Debug Applications in the Innexis CodeBench IDE
5-9](#debug-applications-in-the-innexis-codebench-ide)

[Profile Applications in the Innexis CodeBench IDE
5-10](#profile-applications-in-the-innexis-codebench-ide)

[(Windows) Profile Applications in the Innexis CodeBench IDE
5-12](#windows-profile-applications-in-the-innexis-codebench-ide)

[Kernel and Kernel Module Debugging
6-1](#kernel-and-kernel-module-debugging)

[Kernel Debugging 6-1](#kernel-debugging)

[Debug a Linux Kernel 6-1](#debug-a-linux-kernel)

[Kernel Module Debugging 6-3](#kernel-module-debugging)

[Build a Kernel Module Project 6-3](#build-a-kernel-module-project)

[Debug a Linux Kernel Module 6-5](#debug-a-linux-kernel-module)

[Machine Learning 7-1](#machine-learning)

[Features and Benefits 7-1](#features-and-benefits)

[Acceleration and Instrumentation
7-3](#acceleration-and-instrumentation)

[Getting Started With ML 7-3](#getting-started-with-ml)

[Build Innexis Linux With ML. 7-3](#build-innexis-linux-with-ml)

[Set Up the SDK for Innexis CodeBench.
7-4](#set-up-the-sdk-for-innexis-codebench)

[Using ML in an Application 7-5](#using-ml-in-an-application)

[Application Build Settings 7-5](#application-build-settings)

[Writing Code to Perform Inferences
7-6](#writing-code-to-perform-inferences)

[Run Applications From the Innexis CodeBench IDE.
7-7](#run-applications-from-the-innexis-codebench-ide)

[Task Library API Reference 7-8](#task-library-api-reference)

[Task Library Classes. 7-9](#task-library-classes)

[SemlAccelerationConfig 7-11](#semlaccelerationconfig)

[BaseTaskApi. 7-15](#basetaskapi)

[Working With TensorFlow Lite Models
7-16](#working-with-tensorflow-lite-models)

[Load a Model 7-17](#load-a-model)

[Modify the Model Cache 7-17](#modify-the-model-cache)

[Working With Metadata. 7-18](#working-with-metadata)

[Model Metadata XML Reference. 7-20](#model-metadata-xml-reference)

[Hardware Acceleration 7-34](#hardware-acceleration)

[Using a GPU. 7-35](#using-a-gpu)

[Using Accelerators with External Delegates
7-37](#using-accelerators-with-external-delegates)

[Performance Analysis and Optimization
7-37](#performance-analysis-and-optimization)

[Using Innexis CodeBench Analyzer to Profile ML Inferences.
7-37](#using-innexis-codebench-analyzer-to-profile-ml-inferences)

[Example Applications 7-39](#example-applications)

[Command-Line Options 7-42](#command-line-options)

[Switching Demo Models 7-44](#switching-demo-models)

### [Sample Application Walkthrough.....................................................................A-1](#sample-application-walkthrough)

##### [Create a Sample Application......................................................................................... A-1](#_bookmark181)

  [**Deploy and Run the Sample
  Application.......................................................................A-2**](#_bookmark182)
 
  [**Performing
  Benchmarking............................................................................................
  A-3**](#performing-benchmarking)
 
  [**Set Up Profiling Using Innexis CodeBench
  Analyzer.....................................................
  A-3**](#set-up-profiling-using-innexis-codebench-analyzer)

### [Sample Code for Profiling With Perfetto.......................................................... A-1](#a.-sample-code-for-profiling-with-perfetto) [Glossary. v](#glossary)

  **List of Figures**

##### [Figure 3-1: Explore the Trace With Perfetto 3-26](#figure-3-1-explore-the-trace-with-perfetto)

##### [Figure 6-2: Debug Session 6-3](#figure-6-2-debug-session)

##### [Figure 7-3: Machine Learning Components 7-2](#figure-7-3-machine-learning-components)

  **List of Tables**

##### [Table 1-1: Syntax Conventions 1-2](#table-1-1-syntax-conventions)

  [**Table 1-2: Innexis Linux setup-environment Script**
  **1-11**](#table-1-2-innexis-linux-setup-environment-script)
 
  [**Table 2-3: Tasks to Build a Target Image**
  **2-1**](#table-2-3-tasks-to-build-a-target-image)
 
  [**Table 2-4: local.conf Variables**
  **2-6**](#table-2-4-local.conf-variables)
 
  [**Table 2-5: Enabling Image Features**
  **2-8**](#table-2-5-enabling-image-features)
 
  [**Table 2-6: User Features** **2-9**](#table-2-6-user-features)
 
  [**Table 3-7: Supported Target and Machine Name**
  **3-1**](#table-3-7-supported-target-and-machine-name)
 
  [**Table 3-8: Image Files** **3-2**](#table-3-8-image-files)
 
  [**Table 3-9: Supported Benchmarks**
  **3-7**](#table-3-9-supported-benchmarks)
 
  [**Table 3-10: Supported Title and Machine Name**
  **3-33**](#table-3-10-supported-title-and-machine-name)
 
  [**Table 3-11: Image Files** **3-33**](#table-3-11-image-files)
 
  [**Table 4-12: Installation Components**
  **4-1**](#table-4-12-installation-components)
 
  [**Table 4-13: Build System Files and Extensions**
  **4-2**](#table-4-13-build-system-files-and-extensions)
 
  [**Table 4-14: Common Layer Directories**
  **4-2**](#table-4-14-common-layer-directories)
 
  [**Table 4-15: BitBake Recipes** **4-7**](#table-4-15-bitbake-recipes)
 
  viii Innexis™ Linux® User’s and Reference Manual

# Introduction

  Innexis™ CodeBench provides a customization and integration platform
  to satisfy the unique requirements of embedded projects. The OS is
  based on the Yocto Project®, which provides templates, tools, and
  methods to help you create custom Linux®-based systems.

###### [Syntax Conventions 1-2](#syntax-conventions)

###### [Product Support 1-2](#product-support)

###### [Build System Overview 1-3](#build-system-overview)

###### [BitBake Operation 1-4](#_bookmark6)

###### [setup-environment Script 1-9](#setup-environment-script)

###### [Yocto Project Documentation 1-11](#yocto-project-documentation)

## Syntax Conventions

  This table lists the syntax conventions used in this manual.

###### Table 1-1: Syntax Conventions

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Convention</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p><strong>Bold</strong></p>
</blockquote></td>
<td><blockquote>
<p>Indicates a required item.</p>
</blockquote></td>
</tr>
<tr class="even">
<td><em>Italic</em></td>
<td>Indicates a user-supplied argument.</td>
</tr>
<tr class="odd">
<td><blockquote>
<p>Monospace</p>
</blockquote></td>
<td><blockquote>
<p>Indicates a shell command, line of code, or URL. A bolded monospaced
font identifies text to be entered by the user.</p>
</blockquote></td>
</tr>
<tr class="even">
<td>Underline</td>
<td>Indicates either the default argument or the default value of an
argument.</td>
</tr>
<tr class="odd">
<td>UPPERCASE</td>
<td><blockquote>
<p>Indicates the minimum keyword characters. In most cases, you may omit
the lowercase letters and abbreviate the keyword.</p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>[ ]</p>
</blockquote></td>
<td><blockquote>
<p>Enclose optional arguments. Do not include the square brackets when
entering the command.</p>
</blockquote></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>{ }</p>
</blockquote></td>
<td><blockquote>
<p>Enclose arguments to show grouping. Do not include the curly braces
when entering the command.</p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>‘ ’</p>
</blockquote></td>
<td><blockquote>
<p>Enclose metacharacters that are intended to be entered literally.</p>
</blockquote></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>|</p>
</blockquote></td>
<td>Indicates an either/or choice between items. Do not include the
vertical bar when entering the command.</td>
</tr>
<tr class="even">
<td>…</td>
<td>Follows an argument or group of arguments that may appear more than
once. Do not include the ellipsis when entering the command.</td>
</tr>
</tbody>
</table>

## Product Support

  Siemens Digital Industries Software validates the builds and prebuilt
  images listed for the board support packages (BSPs) in the **[Virtual
  Platform BSPs](#virtual-platform-bsps)** section. You may encounter
  issues as a result of
 
  modifications to the included packages or configuration of the
  validated builds and images. To receive full product support, a
  reproducible test case using a supported virtual platform specified in
  the release notes is required. If such a test case cannot be provided,
  product support will be limited to Q&A support using available
  diagnostic data.

## Build System Overview

  Innexis Linux is based on the Yocto Project 5.0 release. You can use
  the build engine within the OS to create the custom images and root
  file system for your embedded system. The build engine reads metadata,
  such as recipes and configuration files that make up the instructions
  that describe what
 
  packages are outputted and how platform images are created. The OS is
  compatible with Innexis Linux BSPs.
 
  The build engine contains the following components:

- **BitBake** — The task executor and scheduler used to build images.

- **Metadata** — Instructions that you can use to build an embedded
  > Linux®[1](#_bookmark5) distribution. Metadata consists of many text
  > files that describe a package, image, or configuration. The most
  > common metadata type is a recipe.

  BitBake reads and interprets metadata. It also performs the following
  tasks:

1.  Builds a dependency tree.

2.  Creates a task queue based on the dependency tree.

3.  Executes tasks based on the task queue.

  BitBake is capable of efficiently utilizing multiple cores to speed up
  the build process. The dependency tree that BitBake creates ensures
  that tasks are executed in the proper order to satisfy task
  dependencies.
 
  The Innexis Linux build system alleviates the challenges of building
  an embedded Linux distribution through the following features:

- **Build Configuration** — Provides a configuration utility
  (*setup‑environment*). This script creates a *local.conf* file and an
  environment setup script, which together define the overall build
  configuration. You can use the local configuration file to set up
  specific variables and features. For more information about
  *setup‑environment* options, refer to [**setup-environment
  Script**](#setup-environment-script).

- **Image Features** — Uses a feature list in the local configuration
  file to enable certain platform features and output the packages
  required to support these platform features into your file system
  image. Each hardware platform contains a list of supported features.
  Based on the requested features, the build system utilizes certain
  package groups and determines what packages end up in the resulting
  file system image. This makes it easier to ensure that when the user
  starts up Linux on a target, the software required to support the
  application is available.

- **Caching of Binaries** — Enables you to cache and reuse binaries from
  a previous build, which reduces the time required during subsequent
  builds.

  <span id="_bookmark5" class="anchor"></span>1 Linux® is a registered
  trademark of Linus Torvalds in the U.S. and other countries.

#### Related Topics

###### [BitBake Operation](#_bookmark6)

  **[setup-environment Script](#setup-environment-script) [OS
  Images](#os-images-1)**

<span id="_bookmark6" class="anchor"></span>**BitBake Operation**

  BitBake parses metadata, generating a list of tasks from it, and then
  performs those tasks. To see a list of the options BitBake supports,
  use the following help command:
 
  bitbake --help
 
  The most common usage for BitBake is bitbake *\<foo\>*, where “foo” is
  the name of the recipe you want to build. For example, to build the
  package defined by the *wayland* recipe file, type the following:
 
  bitbake wayland
 
  BitBake selects the most current version of wayland it encounters
  during parsing, unless that is overridden elsewhere in the metadata.
  BitBake performs any dependent tasks first if they are not already
  built.
 
  The configuration files (*.conf*) define various configuration
  variables that govern the build process.
 
  These files fall into several areas that define machine configuration
  options, distribution configuration options, compiler tuning options,
  general common configuration options, and user configuration options
  (*local.conf*).

###### [Software Manifest Files. 1-4](#software-manifest-files)

  [**bitbake.** **1-6**](#bitbake)

### Software Manifest Files

  Each BitBake build produces the following manifest files:
  *license.manifest*, *image_license.manifest*, and
 
  *package.manifest*. These files list package details of each included
  package.
 
  The software license manifest files are located in the
  *\<project\>/build/tmp/deploy/licenses/\<machine-
  name\>/development-image-\<machine-name\>.rootfs-\<timestamp\>/*
  directory:

- *image_license.manifest*

- *license.manifest*

- *package.manifest*

  The files contain the following information for each package included
  in the BitBake build:

- Base package name.

- Package version.

- Recipe name.

- A list of software licenses being used by the package. This
  information originates from the BitBake image recipe.

### bitbake

  Performs the specified tasks for a set of BitBake files.

#### Usage

  bitbake \[arguments\] recipe-name

#### Arguments

- --version

  Show program’s version number and exit.

- -h, --help

  Show this command's help message and exit.

- -b BUILDFILE, --buildfile=BUILDFILE

  Execute tasks from a specific *.bb* recipe directly.

- -k, --continue

  Continue as much as possible after an error. While the target that
  failed (and anything depending on it) cannot be built, as much of it
  as possible will be built before stopping.

- -f, --force

  Force the specified targets or task to run (invalidating any existing
  stamp file).

- -c CMD \| --cmd=CMD

  Specify the task to execute. The exact options available depend on the
  metadata. Some examples might be 'compile' or 'populate_sysroot' or
  'listtasks', may give a list of the tasks available.

- -C INVALIDATE_STAMP, --clear-stamp=INVALIDATE_STAMP

  Invalidate the stamp for the specified task, such as ‘compile’, and
  then run the default task for the specified target(s).

- -r PREFILE, --read=PREFILE

  Read the specified file before the *bitbake.conf* file.

- -R POSTFILE, --postread=POSTFILE

  Read the specified file after the *bitbake.conf* file.

- -v, --verbose

  Enable tracing of shell tasks (with 'set -x'). Also print bb.note(...)
  messages to stdout and write them to
 
  \${T}/log.do\_\<task\>.

- -D, --debug

  Increase the debug level. You can specify this more than once. -D sets
  the debug level to 1, where only bb.debug(1, ...) messages are printed
  to stdout; -DD sets the debug level to 2, where both bb.debug(1, ...)
  and bb.debug(2, ...) messages are printed; and so on. Without -D, no
  debug messages are printed.

- -q, --quiet

  Output to the terminal without log message data. You can specify this
  more than once.

- -n, --dry-run

  Do not execute, just go through the motions.

- -S SIGNATURE_HANDLER, --dump-signatures=SIGNATURE_HANDLER

  Dump the signature construction information with no task execution.
  The SIGNATURE_HANDLER parameter is passed to the handler. Two common
  values are none and printdiff, but the handler
 
  may define more or less. None means only dump the signature; printdiff
  means compare the dumped signature with the cached one.

- -p, --parse-only

  Quit after parsing the BitBake recipes (*.bb* files).

- -s, --show-versions

  Show the current and preferred versions of all recipes.

- -e, --environment

  Show the global or per recipe environment with complete information
  about where variables were set or changed.

- -g, --graphviz

  Save dependency tree information for the specified targets in the dot
  syntax.

- -I EXTRA_ASSUME_PROVIDED, --ignore-deps=EXTRA_ASSUME_PROVIDED

  Assume these dependencies do not exist and are already provided
  (equivalent to ASSUME_PROVIDED). Useful to make dependency graphs more
  appealing.

- -l DEBUG_DOMAINS, --log-domains=DEBUG_DOMAINS Show debug logging for
  the specified logging domains.

- -P, --profile

  Profile the command and save reports.

- -u UI, --ui=UI

  Set the user interface to use (knotty, ncurses, taskexp or teamcity -
  default is knotty).

- --token=XMLRPCTOKEN

  Specify the connection token to use when connecting to a remote
  server.

- --revisions-changed

  Set the exit code depending on whether the upstream floating revisions
  have changed or not.

- --server-only

  Run BitBake without a user interface (UI), only starting a server
  (cooker) process.

- -B BIND, --bind=BIND

  The name or address for the BitBake xmlrpc server to bind to.

- -T SERVER_TIMEOUT, --idle-timeout=SERVER_TIMEOUT

  Set timeout to unload BitBake server due to inactivity; -1 means no
  unload; default: Environment variable BB_SERVER_TIMEOUT.

- --no-setscene

  Do not run any setscene tasks. sstate will be ignored and everything
  needed will be built.

#### Description

  Complete information on BitBake is in the *BitBake User Manual* from
  the **[Yocto Project](https://docs.yoctoproject.org/bitbake/)** web
  site. The basic syntax for bitbake is:
 
  bitbake *recipe-name*
 
  where *recipe-name* is the name of the recipe you want to build. This
  usually equates to the first part of a *.bb* file name. For example,
  to build the my_package recipe, type the following:
 
  bitbake my_package
 
  Different versions of my_package might exist and BitBake will choose
  the one selected by the distribution configuration. BitBake will also
  try to execute any dependent tasks first.

#### Examples

  Build a package:
 
  bitbake development-image
 
  Remove the local copy of the cached binary for the package:
 
  bitbake -c cleansstate busybox

#### Related Topics

###### [OS Images](#os-images-1)

## setup-environment Script

  Innexis Linux provides a configuration script called
  *setup-environment*. This script creates a *local.conf* file and an
  environment setup script, which together define the overall build
  configuration.

###### [setup-environment 1-10](#setup-environment)

### setup-environment

  Creates a *local.conf* file and an environment setup script.

#### Usage

  source \<innexis-linux-workspace\>/meta-flex/setup-environment
  \[argument\] "\<layer\>" **\<machine-name\>**

#### Arguments

- -b BUILDDIR

  Specify the build directory to create (default: 'build').

- -o FLEXDIR

  Specify the root of the Innexis Linux install, where you can find
  bitbake and the layers.

- -p PATHS

  Specify a colon-separated list of paths, where you can find layers in
  addition to the root of the Innexis Linux install (default: empty). If
  any path in this list contains wildcards, the list must be quoted to
  avoid wildcard substitution by the shell.

- -l LAYERS

  Specify a space-separated list of the names of additional layers you
  want to include in the configuration. This argument is cumulative.
  Both '-l "meta-foo meta-bar"' and '-l meta-foo -l meta-bar' are valid
  and include both layers.

- -f

  Force overwrite of existing configuration files in the build
  directory. This includes *local.conf* and
 
  *bblayers.conf*, but not *site.conf*.

- -h

  Show this command's usage information.

#### Description

  The actions of the script depend on how many BSPs you have installed,
  as shown in [**Table
  1-2**](#table-1-2-innexis-linux-setup-environment-script). You can
  find the machine name in the BSP quick start for your target.

###### Table 1-2: Innexis Linux setup-environment Script

<table>
<colgroup>
<col style="width: 31%" />
<col style="width: 68%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Number of BSPs Installed</strong></p>
</blockquote></th>
<th><strong>Script Action</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>One BSP</td>
<td><p>The script uses the template configuration file from the
installed BSP and automatically configures a build directory. The</p>
<p>&lt;machine-name&gt; parameter is optional.</p></td>
</tr>
<tr class="even">
<td>Multiple BSPs</td>
<td><p>The script displays a list of available machines from the
installed BSPs and prompts you to select a machine from the list.</p>
<p>After you select a machine, the script will use the template
configuration files from that BSP.</p></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>No BSPs</p>
</blockquote></td>
<td><p>The actions of the script depend on whether you have created and
configured a build directory:</p>
<ul>
<li><blockquote>
<p>Build directory has <em>not</em> been created or configured.</p>
</blockquote></li>
</ul>
<blockquote>
<p>The script prompts you for a machine name. The script sets up the
project directory with a base set of layers plus all layers that include
the machine <em>.conf</em> file for the specified machine, sorted by
layer recipe priority.</p>
</blockquote>
<ul>
<li><blockquote>
<p>Build directory has been created and configured.</p>
</blockquote></li>
</ul>
<blockquote>
<p>The script automatically detects the machine name and sets you up for
that project directory without changing its configuration.</p>
</blockquote></td>
</tr>
</tbody>
</table>

  **Examples**
 
  To build the virtualization layer:

## Yocto Project Documentation

  The Yocto Project offers comprehensive documentation on many tasks
  that you can perform with the Innexis Linux. The Innexis Linux
  documentation provides information specific to the product itself and
  enough reference material so you can perform fundamental tasks.
 
  For detailed information on more advanced tasks, such as reconfiguring
  the kernel or adding a new platform, consult The Yocto Project
  documentation, which you can access at the following web address:

###### <https://docs.yoctoproject.org/5.0.3/index.html>

# OS Images

  With the Innexis Linux development platform, you can build an image
  using the default settings or edit the
 
  *local.conf* file to build a custom image for your platform.
 
  Prebuilt images are also available in your BSP. For details on how to
  use the prebuilt binary files, refer to

###### [Virtual Platform BSPs](#virtual-platform-bsps).

  The following table describes the flow of the tasks required to build
  an Innexis Linux image:

###### Table 2-3: Tasks to Build a Target Image

<table>
<colgroup>
<col style="width: 47%" />
<col style="width: 52%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Task</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>1. Prepare the Workspace for a Build</p>
</blockquote></td>
<td>Prepare the host system and create a workspace to build images.</td>
</tr>
<tr class="even">
<td>2. Set Up the Build Environment</td>
<td><p>Run the <em>setup-environment</em> script to create your build
environment.</p>
<p>If the default settings do not fit your project needs, you can build
a custom image. See <strong><a href="#build-customization">Build
Customization</a></strong> for details.</p></td>
</tr>
<tr class="odd">
<td>3. Build the Target Image</td>
<td>Build the image for your target board.</td>
</tr>
</tbody>
</table>

###### [Prepare the Workspace for a Build 2-1](#prepare-the-workspace-for-a-build)

###### [Set Up the Build Environment 2-3](#set-up-the-build-environment)

###### [Build the Target Image 2-4](#build-the-target-image)

###### [Build Customization 2-5](#build-customization)

## Prepare the Workspace for a Build

  Use setup scripts to prepare the host system for building an Innexis
  Linux image. The installers provide git repositories. Before you can
  build an image, you must create and prepare the workspace directory
 
  where all the layers for your BSP will be checked out. For this
  purpose, the *setup-flex* script shows the BSPs available, and you can
  select the BSP layers you want to install.
 
  You only have to create the workspace once. Then you can create
  multiple builds from a single workspace.
 
  **Prerequisites**

- You are using one of the supported Linux host systems. For details,
  refer to the *Innexis CodeBench Installation Instructions* in your
  installation directory.

- You have root access to your host system. You must have access to the
  package manager as root through the sudo Linux command. If you do not
  have root access, contact your system administrator.

- You have installed the Innexis CodeBench product with the Innexis
  Linux component.

#### Procedure

1.  Create a directory on a partition with sufficient space and navigate
    > to that directory.

2.  For a first time installation of the Innexis Linux, run one of the
    > setup scripts. For example, run the following when using an Ubuntu
    > Linux host system:

  \<*install-path*\>/innexis-linux/*\<version\>*/scripts/setup-ubuntu
 
  Use **setup-rh** for a Red Hat® Linux® host system.
 
  The script needs to be run only once per host machine and is the only
  operation that requires root access. You will be prompted for your
  password when you invoke the script.

3.  Source the *setup-flex* script from your Innexis Linux installation
    > to create a workspace directory.

  Use the -w option to specify the workspace directory you want to
  create. For more information on the script, run **setup-flex -h**.
 
  If you do not use the -w option, the script creates the workspace
  directory by default. For example:
 
  source \<install-path\>/innexis-linux/\<version\>/setup-flex
 
  This command creates the workspace.

4.  If prompted, select the appropriate BSP manifest.

  Selecting a manifest will prepare the component in the workspace
  directory within your project.

#### Results

  The layers are checked out in the workspace directory. You can use the
  *setup-environment* script in the workspace you created to set up a
  build.
 
  To configure the build for your Innexis Linux image, see [**Set Up the
  Build Environment**](#set-up-the-build-environment).

## Set Up the Build Environment

  In the workspace you created, run the *setup-environment* script with
  the required layer and build folder options to set up a build
  environment for a specific target machine.
 
  You can find the target machine name in [**Virtual Platform
  BSPs**](#virtual-platform-bsps).
 
  The *setup-environment* script creates a new build folder that
  contains the *conf* directory. The *conf*
 
  directory holds the following files:

- *local.conf* — Configuration file required for the build. It contains
  local user‑configurable variables.

  If the default build settings do not meet your needs, you can build a
  custom image by modifying the
 
  *conf/local.conf* file. For additional information, refer to [**Build
  Customization**](#build-customization).

- *bblayers.conf* — Configuration file that defines the layers to be
  enabled during the build. For more information, see [**Enable a
  Layer**](#_bookmark97).

  **Prerequisites**

- Your host system has the required packages necessary to build images,
  > and you have created a workspace directory. See **[Prepare the
  > Workspace for a Build](#prepare-the-workspace-for-a-build)** for
  > details.

#### Procedure

1.  Navigate to the *\<innexis-linux-workspace\>* you previously
    > created. For example:

  /home/*\<username\>*/myproject/myworkspace/

2.  Source the *setup-environment* script with the appropriate layer and
    > folder options for your build.

  Refer to **[setup-environment Script](#setup-environment-script)** for
  more information.

#### Results

  You have set up your build environment, and you can continue to the
  next procedure, **[Build the Target](#build-the-target-image)
  [Image](#build-the-target-image)**.

## Build the Target Image

  When you have set up the build environment, you are ready to build the
  Innexis Linux target image.

#### Prerequisites

- Your Innexis Linux build environment is set up and you are in the
  > build directory. For details, refer to
  > **[Set](#set-up-the-build-environment) [Up the Build
  > Environment](#set-up-the-build-environment)**.

- If you want to build from a new shell, you must source your project’s
  > *setup-environment* script as follows:

  source *\<innexis-linux-workspace\>/meta-flex/setup-environment*
 
  This restores the build environment in the current shell or terminal.
  This *setup-environment* script is located within your build directory
  and is generated by the *meta-flex/setup-environment* script you ran
  to create the build directory. This generated script helps restore the
  build environment with the options you specified when you first
  created the build directory.

#### Procedure

1.  To build an image, run the bitbake command.

  bitbake \<target-image\>
 
  For example:
 
  Builds are based on image features and only development-image is
  supported.

2.  (Optional) If you want to build the Yocto SDK for the
    > development-image to use in application development workflows, run
    > the following command after building the image:

  bitbake development-image:do_populate_sdk
 
  or
 
  bitbake -c populate_sdk development-image

#### Results

  The build process starts. The duration of the build depends on many
  factors, such as the build target, number of cores, processor speed,
  internet speed, and the ability to use existing build elements.
 
  After the build completes successfully, the binary images are
  generated in the *\<innexis-linux-workspace\>/
  build/tmp/deploy/images/\<machine-name\>/* directory. The SDK
  installer script is generated in the *\<innexis-
  linux-workspace\>/build/tmp/deploy/sdk/* directory. Application
  developers can then install and use the SDK to develop applications.
  The name of the SDK installer script depends on the BSP you build, see
  **[Software](#software-development-kit) [Development
  Kit](#software-development-kit)** for more information.
 
  When you successfully build an Innexis Linux image, you can run the
  image on the supported virtual platforms. For details, see the
  following sections:

###### [Run the Innexis Linux Image With Innexis Hybrid](#run-the-innexis-linux-image-with-innexis-hybrid-1)

- [**Run the Innexis Linux Image in the ANA Arm64
  Environment**](#run-the-innexis-linux-image-in-the-ana-arm64-environment)

## Build Customization

  You can build an image using the default settings. However, you can
  also customize how your image is built by editing the *local.conf*
  file in the project directory (for example:
  *\<build-dir\>/conf/local.conf*). The
 
  generated *local.conf* file contains examples and definitions for all
  available build configuration variables for the BSP. This section
  covers some common build configuration topics.
 
  The following table lists some of the most important configurable
  variables in *local.conf*.

###### Table 2-4: local.conf Variables

<table>
<colgroup>
<col style="width: 41%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Variable Name</strong></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>DISTRO</p>
</blockquote></td>
<td>Defines the Linux distribution. The default is “innexis-
linux”.</td>
</tr>
<tr class="even">
<td>MACHINE</td>
<td>Defines the machine name.</td>
</tr>
<tr class="odd">
<td>EXTRA_IMAGE_FEATURES</td>
<td>Adds features (or groups of packages) to the image.</td>
</tr>
<tr class="even">
<td>CORE_IMAGE_EXTRA_INSTALL</td>
<td>Adds additional packages to images.</td>
</tr>
<tr class="odd">
<td>BB_NO_NETWORK</td>
<td>Set BB_NO_NETWORK= “1” in the <em>local.conf</em> file, which allows
you to do a build with no connection to the Internet.</td>
</tr>
<tr class="even">
<td>BB_NUMBER_THREADS</td>
<td>Sets the maximum number of BitBake tasks (or threads) that can be
issued in parallel. By default, this is set to double the number of CPU
cores available on your host machine.</td>
</tr>
<tr class="odd">
<td>PARALLEL_MAKE</td>
<td>Configures the number of jobs the make utility should run during
compilation. By default, this is set to double the number of CPU cores
available on your host machine.</td>
</tr>
<tr class="even">
<td>DL_DIR</td>
<td>Defines the directory for storing fetched sources.</td>
</tr>
<tr class="odd">
<td>SSTATE_DIR</td>
<td>Defines the directory used for cached binaries. Binary caching is
referred to as “shared state” in the Yocto Project implementation.</td>
</tr>
</tbody>
</table>

###### [Shared State Caches 2-7](#shared-state-caches)

###### [Set Up Parallel Builds 2-7](#set-up-parallel-builds)

###### [Image Features Settings 2-7](#image-features-settings)

###### [Distribution Features 2-9](#distribution-features)

### Shared State Caches

  Shared state is the binary caching implementation used by the Yocto
  Project. The SSTATE_DIR and SSTATE_MIRROR_SITES variables in the
  *local.conf* file control the location of shared state files.

### Set Up Parallel Builds

  BitBake enables you to run multiple tasks in parallel through the use
  of the BB_NUMBER_THREADS and PARALLEL_MAKE variables in the
  *local.conf* file. By default, the BB_NUMBER_THREADS and PARALLEL_MAKE
  variables are set to values equaling twice the number of CPU cores
  available on your host system. You can customize this by changing the
  values of these variables.

#### Prerequisites

- You have created a build or project directory. For details, refer to
  [**Set Up the Build Environment**](#set-up-the-build-environment).

#### Procedure

1.  Open the *conf/local.conf* file in the project directory with a text
    > editor.

2.  Set the BB_NUMBER_THREADS and PARALLEL_MAKE variables to the values
    > you want.

  The following examples configure BitBake to run a build with eight
  jobs and eight threads:

3.  Save the *local.conf* file.

4.  If you are done configuring your build options, build your target
    > image. For more information, see [**Build the Target
    > Image**](#build-the-target-image).

### Image Features Settings

  Innexis Linux provides the image recipe to build a development image.
 
  The development-image recipe creates a basic BSP with the following
  image features related to debugging included by default: debug-tweaks,
  codebench-debug, ssh-server-openssh, and tools-profile.
 
  For on-target development, tools-sdk is also included by default.
 
  If you want to add features in the development image, you can use the
  EXTRA_IMAGE_FEATURES variable in *local.conf*.

#### Enabling Image Features

  You can add the EXTRA_IMAGE_FEATURES variable in *local.conf* to add
  groups of packages to the generated images. Before you build your
  target image, set the EXTRA_IMAGE_FEATURES variable with the feature
  you want to add. The following image features are available in Innexis
  Linux. Some of these options are added to certain image types
  automatically.

###### Table 2-5: Enabling Image Features

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 70%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Image Feature</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>codebench-debug</td>
<td>Add core debug tools for use with Innexis CodeBench. This is a
subset of tools-debug (gdbserver, strace, and sftp server).</td>
</tr>
<tr class="even">
<td>debug-tweaks</td>
<td>Make an image suitable for development (for example, ssh root access
has a blank password).</td>
</tr>
<tr class="odd">
<td>dev-pkgs</td>
<td>Add -dev packages for all installed packages to enable application
development on the target.</td>
</tr>
<tr class="even">
<td>graphics</td>
<td>Add a graphical environment with support for HDLCD.</td>
</tr>
<tr class="odd">
<td>kerneldev-pkgs</td>
<td>Add Linux kernel source to enable full kernel development or
external module builds on the target.</td>
</tr>
<tr class="even">
<td>ssh-server-openssh</td>
<td>Add OpenSSH to enable secure remote access.</td>
</tr>
<tr class="odd">
<td>target-sdk</td>
<td>Add development tools on the target. This is a subset of tools-sdk
(gcc, make, pkgconfig, and so on).</td>
</tr>
<tr class="even">
<td>tools-debug</td>
<td>Add debugging tools (gdb, gdbserver, strace) for debugging on the
target.</td>
</tr>
<tr class="odd">
<td>tools-profile</td>
<td><p>Add profiling and tracing tools.</p>
<p>Innexis Hybrid: oprofile, exmap, and lttng valgrind Innexis ANA:
oprofile, lttng, valgrind, and perfetto</p></td>
</tr>
</tbody>
</table>

  To add an image feature, add it to the *local.conf* file using the
  following format:
 
  EXTRA_IMAGE_FEATURES += “*\<image-feature\>*”
 
  For additional options that you can use, see
  *meta/classes/image.bbclass* and *meta/classes/core- image.bbclass*
  for more details.

### Distribution Features

  Innexis Linux distribution features are controlled by the
  USER_FEATURES variable in the *local.conf* file. This variable lets
  you manipulate the distribution (distro) features before you build
  your image. To add a distribution feature, add it to the USER_FEATURES
  variable. To remove a feature, prefix it with a tilde (~).
 
  You can add or remove the following distribution features in Innexis
  Linux:

###### Table 2-6: User Features

<table>
<colgroup>
<col style="width: 31%" />
<col style="width: 40%" />
<col style="width: 28%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Feature</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>USER_FEATURES Setting</strong></p>
</blockquote></th>
<th><strong>Layer Name</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Arm® HDLCD</td>
<td>hdlcd-support</td>
<td></td>
</tr>
<tr class="even">
<td>Benchmarking Tools</td>
<td>flex-bsp-extras</td>
<td></td>
</tr>
<tr class="odd">
<td>Debugging</td>
<td>flex-debugging</td>
<td></td>
</tr>
<tr class="even">
<td>EWAOL</td>
<td>N/A</td>
<td></td>
</tr>
<tr class="odd">
<td>GPU IP</td>
<td>rtl-gpu</td>
<td>&lt;gpu-ip-layer&gt;</td>
</tr>
<tr class="even">
<td>Machine Learning (ML)</td>
<td>machine-learning</td>
<td>machine-learning</td>
</tr>
<tr class="odd">
<td>Tracing</td>
<td>tracing</td>
<td></td>
</tr>
<tr class="even">
<td>VirtIO GPU</td>
<td>virtio-gpu</td>
<td></td>
</tr>
<tr class="odd">
<td>Virtualization</td>
<td>virtualization</td>
<td>virtualization-layer</td>
</tr>
</tbody>
</table>

  **Arm HDLCD** Support for HDLCD. It is an RGB streamer that reads the
  data from a framebuffer and displays it on the graphical window
  created by Innexis-QEMU.
 
  **Benchmarking Tools** Support for benchmarking tools (coremark,
  dhrystone, stream and stress-ng) and other utilities (fbv, htop,
  imagemagick, jpeghw, lshw, util-linux).
 
  **Debugging** Support for kernel and kernel module debugging with core
  debug tools for use with the Innexis CodeBench IDE (gdbserver, strace,
  and sftp server). This feature automatically configures the system so
  you can perform debugging.
 
  **EWAOL** Support for the EWAOL (2.0.0) software stack with baremetal
  architecture as the reference implementation for SOAFEE (Scalable Open
  Architecture For Embedded Edge).
 
  **GPU IP** Support for building an OS image with RTL GPU.

###### Machine Learning (ML)

  Support for developing and deploying machine learning based on
  TensorFlow Lite by extending and integrating the Task Library with new
  features that leverage the Innexis Linux platform and tools.
 
  **Tracing** Support for kernel and user space tracing.
 
  **VirtIO GPU** Support for a virtual GPU device that paravirtualizes
  the GPU and display controller.
 
  **Virtualization** Support for containers and other virtualization
  features on the target.
 
  **Add Support for a Feature**
 
  To add virtualization support to your distribution:
 
  USER_FEATURES += "virtualization"
 
  When you set up your build environment, the source setup-environment
  command looks like this:
 
  source meta-flex/setup-environment -b \<build-dir\> -l \\
  virtualization-layer *\<machine-name\>*

#### Remove Support for a Feature

  To remove virtualization support:
 
  USER_FEATURES += "~virtualization"

# Virtual Platform BSPs

  Innexis Linux supports board support packages (BSPs) for virtual
  platforms.
 
  **Innexis Hybrid** Innexis Hybrid is one of the software product
  options included with the Innexis Developer Pro Bundle. It is a
  virtual platform.

###### Innexis Architecture Native Acceleration (ANA)

  ANA software is a cloud-based high-speed virtual platform. By running
  natively on Arm-based servers, the software workloads run at much
  higher speeds than on typical instruction set simulation-based virtual
  platforms.

###### [Innexis Hybrid 3-1](#innexis-hybrid)

  [**Innexis Architecture Native Acceleration**
  **3-33**](#innexis-architecture-native-acceleration)

## Innexis Hybrid

  You can boot the Innexis Linux image in the Innexis™ Hybrid Arm64
  environment. Use the image files that are included with your product
  installation or generated by performing an OS image build.

###### Table 3-7: Supported Target and Machine Name

<table>
<colgroup>
<col style="width: 54%" />
<col style="width: 45%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Supported Target</strong></p>
</blockquote></th>
<th><strong>Machine Name</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Innexis Hybrid</td>
<td>innexis-arm64</td>
</tr>
</tbody>
</table>

  The following types of image files can be used to quickly boot Innexis
  Linux on the target platform:

- **Prebuilt image files** — The prebuilt image files are included in
  your product installation. You can use these files without performing
  an OS image build. They are located in the
  *\<install-path\>/innexis-linux/*

  *\<version\>/\<machine-name\>/\<version\>/binary* directory.

- **Default image files** — The default image files are the image files
  generated when you run a build using the default settings for BSP.
  This build is called the default build. Performing a default build
  ensures that you can build image files using the Innexis Linux
  development platform.

  You can use the BitBake recipe “development-image” to build your
  image.
 
  After a successful build, you can find the image files in the
  *\<innexis-linux-workspace\>/\<build-dir\>/tmp/
  deploy/images/\<machine-name\>* directory.

###### Table 3-8: Image Files

<table>
<colgroup>
<col style="width: 18%" />
<col style="width: 31%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>File Type</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Prebuilt Image Files</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Default Image Files</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>Image</p>
</blockquote></td>
<td><blockquote>
<p><em>Image</em></p>
</blockquote></td>
<td><blockquote>
<p><em>Image</em></p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>Rootfs</p>
</blockquote></td>
<td><blockquote>
<p><em>development-image.ext4</em></p>
</blockquote></td>
<td><em>development-image-&lt;machine- name&gt;.rootfs.ext4</em></td>
</tr>
</tbody>
</table>

###### [Build Configuration for Innexis Hybrid. 3-2](#build-configuration-for-innexis-hybrid)

###### [Set Up an Innexis Hybrid Workspace 3-3](#set-up-an-innexis-hybrid-workspace)

###### [Run the Innexis Linux Image With Innexis Hybrid 3-5](#run-the-innexis-linux-image-with-innexis-hybrid-1)

###### [Benchmarks 3-7](#benchmarks)

###### [Features for Innexis Hybrid 3-8](#features-for-innexis-hybrid)

###### [IDE Connection Configuration for Innexis Hybrid 3-31](#ide-connection-configuration-for-innexis-hybrid)

### Build Configuration for Innexis Hybrid

  You can enable additional functionality for your target image by
  modifying the build configuration file
  (*\<build-dir\>/conf/local.conf*) before building the target image.
  After modifying the configuration file, proceed with the build.
 
  **Add Extra Space to the Root File System (Optional)**
 
  To increase the free space, if necessary, in the root file system of
  the image being generated, add the following line in *local.conf*:
 
  IMAGE_ROOTFS_EXTRA_SPACE:append = " + \<space-in-KBs-here\>"

#### Enable Custom Device Tree (Optional)

  To build a custom device tree, create *flex-external-artifacts/dts*
  directories under *\<build_dir\>*. Then place the *.dts* and *.dtsi*
  files in *\<build-dir\>/flex-external-artifacts/dts*. Update the
  following variables in *local.conf*:

#### Enable Graphics (Optional)

  To enable the graphics feature, which brings the Weston desktop in
  Innexis Linux, uncomment the EXTRA_IMAGE_FEATURES line for graphics,
  and you must also remove HDLCD support as shown:

### Set Up an Innexis Hybrid Workspace

  Set up a workspace using the Linux reference platform.

#### Prerequisites

- You have installed the Innexis™ Developer Pro. See the *Innexis
  > Developer Pro Installation Guide* for details.

- You have completed one of the following:

  - You have installed the Questa® SIM simulation environment. See the
    > *Questa SIM Installation and Licensing Guide* for details.

  - You have installed the Veloce™ emulator. See the Veloce Installation
    > Guide for details.

- You have installed the Veloce VirtuaLAB software. See the *Veloce
  > VirtuaLAB Installation Instructions* for details.

#### Procedure

1.  Create the Innexis Hybrid workspace directory; change into the
    > workspace directory; and create the

  *default_script* directory.
 
  mkdir \<innexis-hybrid-workspace\> cd \<innexis-hybrid-workspace\>
  mkdir default_script

2.  In the *\<innexis-hybrid-workspace\>/default_script* directory,
    > create the *site.sh* file.

  The *site.sh* file must provide the paths to the software tools you
  installed in the Prerequisites.
 
  You can use the following example as a template for your *site.sh*
  file. Review and modify the paths according to your setup:
 
  \# Directory where your SW tools are installed export
  TOOLS_INSTALL_DIR=**\<tools-install-dir\>**
 
  \# Path to Innexis Developer Pro installation export
  INNEXIS_DEVPRO_VERSION=2024.4
 
  export
  INNEXIS_DEVPRO_HOME=\${TOOLS_INSTALL_DIR}/innexis_home/devpro\_\$
 
  {INNEXIS_DEVPRO_VERSION}
 
  export
  PATH=\${INNEXIS_DEVPRO_HOME}/bin:\${INNEXIS_DEVPRO_HOME}/libexec:\$
 
  {PATH}
 
  export
  LD_LIBRARY_PATH=\${INNEXIS_DEVPRO_HOME}/lib:\${INNEXIS_DEVPRO_HOME}/
 
  packages/capstone/5.0.0/lib:\${INNEXIS_DEVPRO_HOME}/packages/slirp/
  lib64:\${LD_LIBRARY_PATH}
 
  \# Path to VirtuaLab installation export VLAB_VERSION=v24.2
 
  export
  VLAB_HOME=\${TOOLS_INSTALL_DIR}/vlab/\${VLAB_VERSION}/VirtuaLAB\_\$
 
  {VLAB_VERSION}
 
  export AXI_SLAVE_RELS=\${VLAB_HOME}/devices/SoftModelMemories/
  AMBA_AXI_SlaveSoftmodelMemory_5.2.1
 
  export XL_VIP_HOME=\${VLAB_HOME}/common/virtualab-open_kit_v24.0.2a/
  xl_vip-questa2024.2
 
  \# Path to QuestaSim installation - Needed only if you're using Questa
  export QUESTA_VERSION=2024.3_1
 
  export QUESTA_HOME=\${TOOLS_INSTALL_DIR}/questa/\${QUESTA_VERSION}/
  questasim
 
  export PATH=\${QUESTA_HOME}/bin:\${PATH}
 
  \# Enable 64 bit mode export MTI_VCO_MODE=64
 
  \# Path to Veloce installation - Needed only if you're using Veloce

3.  Save your changes.

#### Results

  After saving your changes, you can source the *site.sh* file later to
  run Innexis Hybrid.

### Run the Innexis Linux Image With Innexis Hybrid

  To run the Innexis Linux image (innexis-arm64) with Innexis Hybrid,
  create a hybrid Linux platform directory, copy the images to the
  platform directory and run it.

#### Prerequisites

- You have set up the Innexis Hybrid workspace. See **[Set Up an Innexis
  > Hybrid Workspace](#set-up-an-innexis-hybrid-workspace)** for
  > details.

#### Procedure

1.  Clone the Innexis Hybrid Linux platform directory.

  cd \<innexis-hybrid-workspace\> source default_script/site.sh
 
  This clones a platform directory called *linux* and copies the default
  *site.sh* under *linux/config/site.sh*.
 
  \$INNEXIS_DEVPRO_HOME/bin/innexis-clone
  --site-defaults=default_script/ site.sh
  \$INNEXIS_DEVPRO_HOME/platforms/hybrid/linux linux

2.  Copy the innexis-arm64 image to the
    > *\<innexis-hybrid-workspace\>/linux* directory.

  cd \<innexis-hybrid-workspace\>/linux
 
  cp \<build-dir\>/tmp/deploy/images/innexis-arm64/Image
  sw/output/images/ Image
 
  cp
  \<build-dir\>/tmp/deploy/images/innexis-arm64/development-image-innexis-
  arm64.rootfs.ext4 \\

sw/output/images/rootfs.ext4

3.  (Optional) If you built the image with a custom device tree, then
    > also copy the *board.dtb* file.

4.  (Optional) If you built the image with support for graphics,
    > configure the QEMU parameters

  by editing the
  *\<innexis-hybrid-workspace\>/linux/config/generated/platform-common.conf*
  file as follows:

1.  Enable the PCIe bus by modifying the value of pcie-present from
    > false to true.

  pcie-present=true

2.  Attach the following PCIe device:

  The Weston desktop, which uses drm-backend, requires the VGA device in
  QEMU.
 
  -device "VGA,edid=on"

3.  Since HDLCD is not enabled in the Innexis Linux “graphics” build,
    > you may see an uninitialized HDLCD display. To suppress that
    > window, deactivate HDLCD in QEMU by changing the value of
    > hdlcd-present from true to false.

  hdlcd-present=false

5.  Run the image using the Questa SIM simulation environment or the
    > Veloce emulation environment.

    1.  Source the *site.sh* file.

  cd \<innexis-hybrid-workspace\>/linux source ./config/site.sh

2.  To run the image, do the following: If you are using Questa:

  ./questa/build
 
  ./questa/run
 
  If you are using Veloce:
 
  ./veloce/build
 
  ./veloce/run

### Benchmarks

  The Innexis Hybrid platform enables benchmarks and software workload
  runs in the early stages of the design cycle. Innexis Linux supports
  the following benchmarks, which you can run on Innexis Hybrid from the
  command line.

###### Table 3-9: Supported Benchmarks

<table>
<colgroup>
<col style="width: 18%" />
<col style="width: 12%" />
<col style="width: 68%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Benchmark</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Version</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>CoreMark</p>
</blockquote></td>
<td><blockquote>
<p>1.01</p>
</blockquote></td>
<td><p>CoreMark is an industry-standard benchmark that measures the
performance of central processing units (CPU) and embedded
microcontrollers (MCU). This is a simple benchmark used to</p>
<p>test only the processor’s core features. The benchmark involves three
key algorithms: the first involves the operations on linked- list, the
second is matrix-multiplication, and the third is state- machine
operations.</p>
<p>There are four types available in Innexis Linux:</p>
<ul>
<li><blockquote>
<p>coremark — single-thread (default)</p>
</blockquote></li>
<li><blockquote>
<p>coremark_mt4f — multi-thread with 4 threads using fork</p>
</blockquote></li>
<li><blockquote>
<p>coremark_mt4s — multi-thread with 4 threads using fork and
sockets</p>
</blockquote></li>
<li><blockquote>
<p>coremark_mt4p — multi-thread with 4 threads using pthread</p>
</blockquote></li>
</ul></td>
</tr>
<tr class="even">
<td>Dhrystone</td>
<td>2.1</td>
<td><p>Dhrystone is a measure of processor and compiler efficiency. It
is a synthetic benchmark; that is, a simple program carefully designed
to statistically mimic the processor usage of some common set of
programs. The program is balanced according to statement type, as well
as data type.</p>
<p>The following is true for Dhrystone:</p>
<ul>
<li><blockquote>
<p>It does not use floating point since typical programs do not.</p>
</blockquote></li>
<li><blockquote>
<p>It does not do I/O for simplicity though typical programs do.</p>
</blockquote></li>
<li><blockquote>
<p>It does not contain much code that can be optimized by vector
processors.</p>
</blockquote></li>
<li><blockquote>
<p>It gives results in dhrystones/second. Bigger numbers are better.</p>
</blockquote></li>
</ul>
<p>The executable called <em>dhry</em> is available in Innexis
Linux.</p></td>
</tr>
<tr class="odd">
<td>STREAM</td>
<td>5.10</td>
<td>STREAM is an industry standard, simple synthetic benchmark program
that measures sustainable memory bandwidth (in</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 18%" />
<col style="width: 12%" />
<col style="width: 68%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Benchmark</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Version</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
<td><p>MB/s) and the corresponding computation rate for simple vector
kernels.</p>
<p>STREAM uses four kernels for analysis:</p>
<ul>
<li><blockquote>
<p>“Copy'” measures transfer rates in the absence of arithmetic.</p>
</blockquote></li>
<li><blockquote>
<p>“Scale'” adds a simple arithmetic operation.</p>
</blockquote></li>
<li><blockquote>
<p>“Sum” adds a third operand to allow multiple load or store ports on
vector machines to be tested.</p>
</blockquote></li>
<li><blockquote>
<p>“Triad'” allows chained, overlapped, fused multiply, and add
operations.</p>
</blockquote></li>
</ul>
<p>There are two types available in Innexis Linux:</p>
<ul>
<li><blockquote>
<p>stream_c — single-thread (default)</p>
</blockquote></li>
<li><blockquote>
<p>stream_c_openmp — multi-thread where the number of threads can be
specified by the environment variable OMP_NUM_THREADS</p>
</blockquote></li>
</ul>
<p>For reference see the AMD</p>
<p>website: <strong><a
href="https://www.amd.com/en/developer/zen-software-studio/applications/spack/stream-benchmark.html">https://www.amd.com/en/developer/zen-software-</a>
<a
href="https://www.amd.com/en/developer/zen-software-studio/applications/spack/stream-benchmark.html">studio/applications/spack/stream-benchmark.html</a></strong></p></td>
</tr>
<tr class="even">
<td><blockquote>
<p>stress-ng</p>
</blockquote></td>
<td><blockquote>
<p>0.17.05</p>
</blockquote></td>
<td><p>stress-ng (stress next generation) is used to stress test a
computer system in various selectable ways. It was designed to exercise
various physical subsystems of a computer as well as the various
operating system kernel interfaces. stress-ng also has a wide range of
CPU-specific stress tests (known as “stressors”) that exercise floating
point, integer, bit manipulation and control flow.</p>
<p>stress-ng can also measure test throughput rates; this can be useful
to observe performance changes across different</p>
<p>operating system releases or types of hardware. However, its intended
use is not to be a precise benchmark test suite.</p>
<p>The executable called <em>stress-ng</em> is available in Innexis
Linux.</p></td>
</tr>
</tbody>
</table>

### Features for Innexis Hybrid

###### [VirtIO-GPU Support for Innexis Hybrid 3-9](#_bookmark37)

###### [GPU IP Support. 3-20](#gpu-ip-support)

###### [Tracing 3-24](#tracing)

###### [HDLCD 3-30](#hdlcd)

  <span id="_bookmark37" class="anchor"></span>**VirtIO-GPU Support for
  Innexis Hybrid**
 
  This section provides an overview of the support for VirtIO-GPU
  acceleration for OpenGL on the Innexis LinuxBSP for Innexis Hybrid.
  This integration enables hardware-accelerated rendering and compute
  shader workloads on this BSP, reducing CPU overhead and improving
  graphics rendering performance.
 
  OpenGL is a cross-language, cross-platform API for rendering 2D and 3D
  vector graphics. This API
 
  can leverage supported GPUs for hardware-accelerated rendering.
  Innexis Linux enables OpenGL host offloading by using the QEMU
  emulation of virtio-gpu-gl-pci device pass-through (For details refer
  to:
  [**https://www.qemu.org/docs/master/system/devices/virtio-gpu.html**](https://www.qemu.org/docs/master/system/devices/virtio-gpu.html)).
  This setup uses the VirGL driver – a Mesa Gallium component that
  serializes OpenGL and OpenGL ES commands over the VirtIO transport
  layer. On the host system, libvirglrenderer translates these
  serialized commands into native OpenGL calls. The host GPU then
  processes these native OpenGL calls to render the graphics as
  requested.

###### OpenGL Modes of Operation

  The OpenGL APIs operate in the guest OS in the following modes: the
  graphics feature is enabled with or without VirtIO-GPU.
 
  **Graphics With VirtIO-GPU**
 
  When the graphics feature is enabled with VirtIO-GPU, VirGL
  acceleration is used, and it further depends on GPU availability on
  the host system:

- If a GPU is available on the host, such as an NVIDIA GPU, VirGL
  > acceleration will be hardware-based. You must set the following
  > environment variables:

  - DRI_PRIME –– If you have hybrid graphics cards (Integrated +
    > Discrete GPUs) and NVIDIA GPU is available as discrete GPU, then
    > set this to 1 to select the discrete GPU.

  - NV_PRIME_RENDER_OFFLOAD –– To configure a graphics application to be
    > offloaded to the NVIDIA GPU screen, set this to 1.

  - GLX_VENDOR_LIBRARY_NAME –– If the graphics application (QEMU) uses
    > GLX on the host system, then also set this to nvidia, so that
    > NVIDIA GLX driver is loaded.

  For more information, see
  **[https://download.nvidia.com/XFree86/Linux-x86_64/555.42.02/README/](https://download.nvidia.com/XFree86/Linux-x86_64/555.42.02/README/primerenderoffload.html)
  [primerenderoffload.html](https://download.nvidia.com/XFree86/Linux-x86_64/555.42.02/README/primerenderoffload.html)**.

- If a GPU is not available on the host, then VirGL acceleration will be
  software-based, with software rendering done on the host CPUs. This
  mode is selected automatically in this case. However, you can force
  software-based acceleration. Set the following environment variables
  on the host system before launching the Questa simulation or Veloce
  emulation:

#### Graphics Without VirtIO-GPU

  When the graphics feature is enabled without VirtIO-GPU, software
  rendering is performed on QEMU virtual CPUs. See **[Enable Graphics
  (Optional)](#enable-graphics-optional)** for details.
 
  However, if you enabled support for VirtIO-GPU in your image, you can
  force software rendering inside the guest OS by setting these
  environment variables before running any application:

###### Build Configuration for VirtIO-GPU

  To enable graphics with VirtIO-GPU, uncomment the USER_FEATURES line
  for virtio-gpu in *local.conf* as follows:
 
  For more information on building an Innexis Linux OS image, see [**OS
  Images**](#os-images-1).

###### Set Up the Host Environment to View GPU Usage

  Install the appropriate drivers on the host to view GPU usage.

#### Procedure

1.  Check if the NVIDIA GPU is available on your host by running the
    > lspci (list PCI) command.

  lspci

2.  To view GPU usage for an NVIDIA GPU, use the RPM package manager to
    > install the NVIDIA driver on the supported hosts for Innexis
    > Hybrid.

  sudo dnf config-manager --add-repo
  https://developer.download.nvidia.com/ compute/cuda/repos/rhel\$(rpm
  -E %{rhel})/x86_64/cuda-rhel\$(rpm -E %
 
  {rhel}).repo
 
  sudo dnf install nvidia-driver nvidia-settings
 
  sudo dnf install -y
  https://dl.fedoraproject.org/pub/epel/epel-release- latest-\$(rpm -E
  %{rhel}).noarch.rpm
 
  sudo dnf install nvtop

#### Results

  Your host is now set up to view GPU usage.

###### Set Up the Innexis Hybrid Linux Platform

  Set up the Innexis Hybrid Linux virtual platform for GPU sharing with
  the host OS.

#### Prerequisites

- You have installed Innexis™ Developer Pro and set up an Innexis Hybrid
  > workspace. See **[Set Up an](#set-up-an-innexis-hybrid-workspace)
  > [Innexis Hybrid Workspace](#set-up-an-innexis-hybrid-workspace)**
  > for details.

- You have installed Innexis Linux and built an image with support for
  the virtio-gpu device. See
  **[Build](#build-configuration-for-virtio-gpu) [Configuration for
  VirtIO-GPU](#build-configuration-for-virtio-gpu)** for details.

#### Procedure

1.  Source the *site.sh* file, and clone the Innexis Hybrid Linux
    > virtual platform.

  cd \<innexis-hybrid-workspace\> source default_script/site.sh
 
  \$INNEXIS_DEVPRO_HOME/bin/innexis-clone
  \$INNEXIS_DEVPRO_HOME/platforms/ hybrid/linux linux-virtio-gpu

2.  Copy the images from the Innexis Linux build directory into the
    > Innexis Hybrid workspace.

  cd \<innexis-hybrid-workspace\>/linux-virtio-gpu
 
  cp
  \<build\>/tmp/deploy/images/innexis-arm64/development-image-innexis-
  arm64-\<timestamp\>.rootfs.ext4 sw/output/images/rootfs.ext4
 
  cp \<build\>/tmp/deploy/images/innexis-arm64/Image
  sw/output/images/Image

3.  Configure the QEMU parameters by editing the
    > *config/generated/platform-common.config* file as follows:

    - Set pci-present to true: pci-present=true

    - Enable gl with SDL display: sdl,gl=on

    - Enable virtio-gpu-gl-pci device, the max_outputs value specifies
      > the number of display windows:

  -device
  "virtio-gpu-gl-pci,id=gpu1,addr=08.0,xres=1920,yres=1080,max_outputs=1"

- Set the resolution so it is the same as the one passed to
  > virtio-gpu-gl-pci device: -g "1920x1080"

- Enable the XHCI USB controller and attach the usb-kbd and usb-tablet
  > devices: -device "qemu-xhci"

  -device "usb-kbd" -device "usb-tablet"

- Set hdlcd-present to false so it is not used with VirtIO-GPU:
  > hdlcd-present=false

  root=/dev/vda\\"
 
  -append "\\consoleblank=0 console=ttyAMA0 qemu=1
 
  -fsdev "local,id=r,path="\$
 
  {INNEXIS_PLATFORM_DIR}"/sw/dropbox,security_model=none"
 
  -device "virtio-9p- device,fsdev=r,mount_tag=dropbox"
 
  \+ -device "virtio-gpu-gl-
  pci,id=gpu1,addr=08.0,xres=1920,yres=1080,max_outputs=1"
 
  \+ -device "qemu-xhci"
 
  \+ -device "usb-kbd"
 
  \+ -device "usb-tablet"
 
  \]
 
  qemu : {
 
  multi_threading : false
 
  \-
 
  machine : "arm-a-series,usb-present=true,virtio-present=true,mci-
  present=false,goldfish-event-support=true,clcd-present=false,goldfish-
  support=false,pcie-present=false,firmware=\$INNEXIS_PLATFORM_DIR/sw/
  output/images/inxboot.bin,num-irqs=480,gicr-base=0x2c040000,hdlcd-
  present=true"
 
  \+
 
  machine : "arm-a-series,usb-present=true,virtio-present=true,mci-
  present=false,goldfish-event-support=true,clcd-present=false,goldfish-
  support=false,pcie-present=true,firmware=\$INNEXIS_PLATFORM_DIR/sw/
  output/images/inxboot.bin,num-irqs=480,gicr-base=0x2c040000,hdlcd-
  present=false"
 
  }
 
  elf_file : \[
 
  \${INNEXIS_PLATFORM_DIR}"/sw/output/images/Image"

#### Results

  You have configured the Innexis Hybrid virtual platform.

###### Run the Image With virtio-gpu Support

  Run the Innexis Linux image with virtio-gpu enabled using the Questa
  SIM simulation environment.

#### Prerequisites

- You have set up the Innexis Hybrid Linux virtual platform. See **[Set
  > Up the Innexis Hybrid
  > Linux](#set-up-the-innexis-hybrid-linux-platform)
  > [Platform](#set-up-the-innexis-hybrid-linux-platform)** for details.

- You have set up your host to view GPU usage. See [**Set Up the Host
  > Environment to View GPU
  > Usage**](#set-up-the-host-environment-to-view-gpu-usage)

  for details.

#### Procedure

1.  Ensure that you are in the Innexis Hybrid workspace.

  cd \<innexis-hybrid-workspace\>/linux-virtio-gpu

2.  Run the image using the Questa SIM simulation environment.

  source config/site.sh questa/build questa/run

#### Results

  During boot, a QEMU (virtio-gpu head-0) window opens with the
  following message: Guest has not initialized the display (yet).
 
  This transitions into the following window in which you control the
  mouse pointer. You can click weston- terminal to launch a shell
  terminal.

<img src="media/image2.png" style="width:7.14583in;height:4.33854in" />

#### Examples

  After the system boots, you can check the following:

- GPU device and render node

- Weston output device

- Renderer and rendering device

- DRM device information

#### Check for the GPU Device and Render Node

  To verify that the GPU device and its render node are available under
  */dev/dri*, run the following command:

#### Check the Weston Output Device

  Weston, the Wayland compositor on Innexis Linux, uses the DRM backend
  and the same GPU device:

#### Check the Renderer and Rendering Capabilities

  Use utilities like eglinfo to inspect the EGL/GL capabilities of the
  detected GPU.
 
  root@innexis-arm64:~# waylandeglinfo Trying with GLES version 3
  EGL_VERSION = 1.5
 
  EGL_VENDOR = Mesa Project
 
  EGL_EXTENSIONS = EGL_ANDROID_blob_cache EGL_ANDROID_native_fence_sync
  EGL_EXT_buffer_age EGL_EXT_config_select_group
  EGL_EXT_image_dma_buf_import EGL_EXT_image_dma_buf_import_modifiers
  EGL_EXT_present_opaque EGL_EXT_surface_compression
  EGL_EXT_swap_buffers_with_damage EGL_KHR_cl_event2
  EGL_KHR_config_attribs EGL_KHR_context_flush_control
  EGL_KHR_create_context EGL_KHR_create_context_no_error
 
  EGL_KHR_fence_sync EGL_KHR_get_all_proc_addresses
  EGL_KHR_gl_colorspace EGL_KHR_gl_renderbuffer_image
  EGL_KHR_gl_texture_2D_image EGL_KHR_gl_texture_3D_image
  EGL_KHR_gl_texture_cubemap_image EGL_KHR_image_base
  EGL_KHR_no_config_context EGL_KHR_reusable_sync
  EGL_KHR_surfaceless_context EGL_KHR_swap_buffers_with_damage
  EGL_EXT_pixel_format_float EGL_KHR_wait_sync
  EGL_MESA_configless_context EGL_MESA_drm_image EGL_MESA_gl_interop
  EGL_MESA_image_dma_buf_export EGL_MESA_query_driver
  EGL_MESA_x11_native_visual_id EGL_WL_bind_wayland_display
  EGL_WL_create_wayland_buffer_from_image EGL_CLIENT_APIS = OpenGL
  OpenGL_ES
 
  GL_VERSION: OpenGL ES 3.1 Mesa 24.3.4
 
  GL_RENDERER: virgl GL_EXTENSIONS:
 
  GL_EXT_blend_minmax, GL_EXT_multi_draw_arrays,
  GL_EXT_texture_compression_s3tc, GL_EXT_texture_compression_dxt1,

#### Retrieve Detailed DRM Device Information

  Use the drm_info utility to query detailed information about the
  VirtIO-GPU DRM device, including driver details, device ID, supported
  framebuffer sizes, information about the corresponding connectors,
  encoders, CRTCs, and planes.
 
  root@innexis-arm64:~# drm_info /dev/dri/card0 Node: /dev/dri/card0
 
  ├───Driver: virtio_gpu (virtio GPU) version 0.1.0
 
  │ ├───DRM_CLIENT_CAP_STEREO_3D supported
 
  │ ├───DRM_CLIENT_CAP_UNIVERSAL_PLANES supported
 
  │ ├───DRM_CLIENT_CAP_ATOMIC supported
 
  │ ├───DRM_CLIENT_CAP_ASPECT_RATIO supported
 
  │ ├───DRM_CLIENT_CAP_WRITEBACK_CONNECTORS supported
 
  │ ├───DRM_CLIENT_CAP_CURSOR_PLANE_HOTSPOT not supported
 
  │ ├───DRM_CAP_DUMB_BUFFER = 1
 
  │ ├───DRM_CAP_VBLANK_HIGH_CRTC = 1
 
  │ ├───DRM_CAP_DUMB_PREFERRED_DEPTH = 0
 
  │ ├───DRM_CAP_DUMB_PREFER_SHADOW = 0
 
  │ ├───DRM_CAP_PRIME = 3
 
  │ ├───DRM_CAP_TIMESTAMP_MONOTONIC = 1
 
  │ ├───DRM_CAP_ASYNC_PAGE_FLIP = 0
 
  │ ├───DRM_CAP_CURSOR_WIDTH = 64
 
  │ ├───DRM_CAP_CURSOR_HEIGHT = 64
 
  │ ├───DRM_CAP_ADDFB2_MODIFIERS = 0
 
  │ ├───DRM_CAP_PAGE_FLIP_TARGET = 0
 
  │ ├───DRM_CAP_CRTC_IN_VBLANK_EVENT = 1
 
  │ ├───DRM_CAP_SYNCOBJ = 1
 
  │ ├───DRM_CAP_SYNCOBJ_TIMELINE = 1
 
  │ └───DRM_CAP_ATOMIC_ASYNC_PAGE_FLIP not supported
 
  ├───Device: PCI 1af4:1050
 
  │ └───Available nodes: primary, render
 
  ├───Framebuffer size
 
  │ ├───Width: \[32, 8192\]
 
  │ └───Height: \[32, 8192\]
 
  ├───Connectors
 
  │ └───Connector 0
 
  │ ├───Object ID: 34
 
  │ ├───Type: virtual
 
  │ ├───Status: connected
 
  │ ├───Physical size: 480×270 mm
 
  │ ├───Subpixel: unknown
 
  │ ├───Encoders: {0}
 
  │ ├───Modes
 
  │ │ ├───[1920×1080@75.00](mailto:1080@75.00) preferred driver nhsync
  nvsync
 
  │ │ ├───[5120×2160@50.00](mailto:2160@50.00) driver phsync pvsync
  64:27
 
  │ │ ├───[4096×2160@50.00](mailto:2160@50.00) driver phsync pvsync
  256:135
 
  │ │ ├───[3840×2160@60.00](mailto:2160@60.00) driver phsync pvsync 16:9
 
  │ │ ├───[3840×2160@59.94](mailto:2160@59.94) driver phsync pvsync 16:9
 
  │ │ ├───[3840×2160@50.00](mailto:2160@50.00) driver phsync pvsync 16:9

<table style="width:100%;">
<colgroup>
<col style="width: 7%" />
<col style="width: 8%" />
<col style="width: 30%" />
<col style="width: 8%" />
<col style="width: 8%" />
<col style="width: 8%" />
<col style="width: 26%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p>│</p>
</blockquote></th>
<th>│</th>
<th>├───<a href="mailto:1440@60.00">1920×1440@60.00</a></th>
<th>driver</th>
<th>nhsync</th>
<th>pvsync</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1080@50.00">2560×1080@50.00</a></td>
<td>driver</td>
<td>phsync</td>
<td>pvsync</td>
<td>64:27</td>
</tr>
<tr class="even">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1392@59.99">1856×1392@59.99</a></td>
<td>driver</td>
<td>nhsync</td>
<td>pvsync</td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1344@60.00">1792×1344@60.00</a></td>
<td>driver</td>
<td>nhsync</td>
<td>pvsync</td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1152@60.00">2048×1152@60.00</a></td>
<td>driver</td>
<td>phsync</td>
<td>pvsync</td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1200@59.88">1920×1200@59.88</a></td>
<td>driver</td>
<td>nhsync</td>
<td>pvsync</td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1080@60.00">1920×1080@60.00</a></td>
<td>driver</td>
<td>nhsync</td>
<td>nvsync</td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1080@50.00">1920×1080@50.00</a></td>
<td>driver</td>
<td>phsync</td>
<td>pvsync</td>
<td>16:9</td>
</tr>
<tr class="even">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1200@60.00">1600×1200@60.00</a></td>
<td>driver</td>
<td>phsync</td>
<td>pvsync</td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1050@59.95">1680×1050@59.95</a></td>
<td>driver</td>
<td>nhsync</td>
<td>pvsync</td>
<td></td>
</tr>
<tr class="even">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1050@59.98">1400×1050@59.98</a></td>
<td>driver</td>
<td>nhsync</td>
<td>pvsync</td>
<td></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>│</p>
</blockquote></td>
<td>│</td>
<td>├───<a href="mailto:1024@60.02">1280×1024@60.02</a></td>
<td>driver</td>
<td>phsync</td>
<td>pvsync</td>
<td></td>
</tr>
<tr class="even">
<td colspan="7"><blockquote>
<p>│ │ ├───<a href="mailto:900@59.89">1440×900@59.89</a> driver nhsync
pvsync</p>
<p>│ │ ├───<a href="mailto:960@60.00">1280×960@60.00</a> driver phsync
pvsync</p>
<p>│ │ ├───<a href="mailto:768@60.02">1360×768@60.02</a> driver phsync
pvsync</p>
<p>│ │ ├───<a href="mailto:768@59.87">1280×768@59.87</a> driver nhsync
pvsync</p>
<p>│ │ ├───<a href="mailto:768@60.00">1024×768@60.00</a> driver nhsync
nvsync</p>
<p>│ │ ├───<a href="mailto:600@60.32">800×600@60.32</a> driver phsync
pvsync</p>
<p>│ │ ├───<a href="mailto:480@60.00">640×480@60.00</a> driver nhsync
nvsync 4:3</p>
<p>│ │ └───<a href="mailto:480@59.94">640×480@59.94</a> driver nhsync
nvsync</p>
<p>│ └───Properties</p>
<p>│ ├───"DPMS": enum {On, Standby, Suspend, Off} = Off</p>
<p>│ ├───"link-status": enum {Good, Bad} = Good</p>
<p>│ ├───"non-desktop" (immutable): range [0, 1] = 0</p>
<p>│ ├───"TILE" (immutable): blob = 0</p>
<p>│ ├───"CRTC_ID" (atomic): object CRTC = 0</p>
<p>│ └───"EDID" (immutable): blob = 36</p>
<p>├───Encoders</p>
<p>│ └───Encoder 0</p>
<p>│ ├───Object ID: 35</p>
<p>│ ├───Type: virtual</p>
<p>│ ├───CRTCS: {0}</p>
<p>│ └───Clones: {0}</p>
<p>├───CRTCs</p>
<p>│ └───CRTC 0</p>
<p>│ ├───Object ID: 33</p>
<p>│ ├───Legacy info</p>
<p>│ │ └───Gamma size: 0</p>
<p>│ └───Properties</p>
<p>│ ├───"ACTIVE" (atomic): range [0, 1] = 0</p>
<p>│ ├───"MODE_ID" (atomic): blob = 0</p>
<p>│ ├───"OUT_FENCE_PTR" (atomic): range [0, UINT64_MAX] = 0</p>
<p>│ └───"VRR_ENABLED": range [0, 1] = 0</p>
<p>└───Planes</p>
<p>└───Plane 0</p>
<p>├───Object ID: 31</p>
<p>├───CRTCs: {0}</p>
<p>├───Legacy info</p>
<p>│ ├───FB ID: 0</p>
<p>│ └───Formats:</p>
<p>│ └───XRGB8888 (0x34325258)</p>
<p>└───Properties</p>
<p>├───"type" (immutable): enum {Overlay, Primary, Cursor} =</p>
<p>Primary</p>
<p>├───"FB_ID" (atomic): object framebuffer = 0</p>
<p>├───"IN_FENCE_FD" (atomic): srange [-1, INT32_MAX] = -1</p>
</blockquote></td>
</tr>
</tbody>
</table>

###### Run the OpenGL Benchmark

  Run the glmark2-es2-wayland benchmark from the QEMU terminal and view
  GPU usage on the host machine. glmark2-es2-wayland is a benchmark for
  OpenGL (ES) 2.0.

#### Prerequisites

- You are running the image with virtio-gpu support and have launched
  the QEMU Wayland terminal. See

###### [Run the Image With virtio-gpu Support](#run-the-image-with-virtio-gpu-support).

  **Procedure**

1.  From the QEMU Wayland terminal, launch the glmark2-es2-wayland
    > benchmark.

  glmark2-es2-wayland

2.  <img src="media/image3.png" style="width:6.5574in;height:3.56823in" /><img src="media/image4.jpeg" style="width:6.9375in;height:3.94875in" />View
    > the GPU usage on the host machine by running nvtop. The following
    > example shows GPU usage for an NVIDIA GPU:

#### Results

  The GPU usage displays on the host using the QEMU Weston terminal.

##### GPU IP Support

  In this section, you will create a GPU layer that will enable you to
  build an OS image with support for RTL GPU.

###### [Create a New Layer for GPU. 3-20](#_bookmark43)

  [**Include the GPU Layer in the Build**
  **3-23**](#include-the-gpu-layer-in-the-build)
 
  <span id="_bookmark43" class="anchor"></span>**Create a New Layer for
  GPU**
 
  Create a new Yocto project layer to integrate GPU support with Innexis
  Linux. A new layer implementation enables you to create a layer that
  is specific to the GPU IP you want to use with Innexis Linux.

#### Prerequisites

- You have installed Innexis Linux using the Innexis CodeBench
  > installer.

- You have set up the Innexis Linux workspace. See **[Prepare the
  > Workspace for a Build](#prepare-the-workspace-for-a-build)** for
  > details.

#### Procedure

1.  Change directory to the Innexis Linux workspace.

  cd \<innexis-linux-workspace\>

2.  Create a build directory to set up the environment for bitbake.

  source meta-flex/setup-environment -b \<build-dir\> innexis-arm64

3.  Create a new bitbake layer; for example, *\<gpu-layer-name\>*.

  bitbake-layers create-layer --priority 23 ../\<gpu-layer-name\>

4.  Run the following commands to append these lines to
    > *conf/layer.conf*.

  This provides you an override, which should be used to conditionally
  apply all the changes introduced by this layer.

5.  Create a recipe for your GPU user-space libraries, for example,
    > *my-gpu-libs_0.1.bb*, if one is not already available.

  This recipe could provide the virtual targets depending on the
  supported GPU features and the libraries installed by the recipe:

- *virtual/libgl* for OpenGL

- *virtual/libgles1*, *virtual/libgles2* and *virtual/libgles3* for
  > respective OpenGL ES versions

- *virtual/egl* for libEGL

- *virtual/libgbm* for libgbm

  See **[Adding and Modifying Packages and
  Recipes](#adding-and-modifying-packages-and-recipes)** for details on
  creating new layers and recipes.

6.  Create the *\<gpu-layer-name\>/conf/machine/include/gpu.inc* file.
    > Set the preferred providers for the available virtual targets in
    > this *gpu.inc* file to point to the recipe that you have created.

  For example:
 
  The *gpu.inc* file gets included in the machine configuration and
  takes effect globally for the build.

7.  Include your GPU driver in the kernel through the linux-yocto
    > recipe.

  Your GPU driver can be an out-of-tree module, a pre-built installable
  module, or a patch to the kernel source. An example recipe structure
  may look like the following if you are patching the kernel source with
  your GPU driver patch. You can also include a kernel config fragment
  (*my_gpu.cfg*) to make modifications in the kernel configurations
  specific to your GPU driver implementation.

8.  Create the *\<gpu-layer-name\>/conf/local.conf.append* fragment.

#### Results

  The *local.conf.append* fragment becomes a part of *local.conf* in
  your build directory and enables GPU support by default when the layer
  is included in the build using the *setup-environment* script.
 
  You can also add this line as already commented out, and in that case,
  your default build will be done without GPU support. See **[Include
  the GPU Layer in the Build](#include-the-gpu-layer-in-the-build)** for
  details.

###### Include the GPU Layer in the Build

  When you build your Innexis Linux image, include the GPU layer when
  you set up your build environment. This enables you to use your
  implementation of GPU through the rtl-gpu feature.

#### Prerequisites

- You have set up an Innexis Linux workspace.

- You have created a GPU layer in the Innexis Linux workspace. See
  **[Create a New Layer for GPU](#_bookmark43)** for details.

#### Procedure

1.  Change to the Innexis Linux workspace.

  cd \<innexis-linux-workspace\>

2.  Set up the build environment to include the GPU layer.

  source meta-flex/setup-environment -b \<build-dir\> -l
  \<gpu-layer-name\> innexis-arm64

3.  Ensure that the "rtl-gpu" feature is enabled in *conf/local.conf*.

  It will already be enabled in your *local.conf* from the
  *local.conf.append* fragment that you created in the **[Create a New
  Layer for GPU](#_bookmark43)** section.
 
  To deactivate the feature, comment out the USER_FEATURES line.

4.  Proceed with the build as usual.

#### Results

  You can run your custom GPU IP with Innexis Linux. When the GPU layer
  is included in Innexis Linux builds then any Innexis Linux feature, or
  the BSP layer features that can benefit from GPU support, would make
  use of it (for example, machine-learning).
 
  Using the *local.conf* level switch for the GPU enables or removes it
  in the Innexis Linux build.

##### Tracing

  Innexis Linux includes tracing and profiling features, which are
  widely-used techniques for performance analysis. The virtual platform
  BSPs, Innexis Hybrid and ANA, both support these features using
  Perfetto.
 
  **[Perfetto](https://perfetto.dev/docs/)** is an open-source suite of
  tools that combines tracing and profiling to enable you to get
  relevant insights into a system. It shows where resources are being
  used by the system, helps identify the potential changes needed to
  improve performance, and verifies the impact of those changes.

###### [Build Configuration for Perfetto. 3-24](#build-configuration-for-perfetto)

###### [Kernel Tracing 3-24](#kernel-tracing)

###### [User Space Tracing 3-27](#user-space-tracing)

###### Build Configuration for Perfetto

  Tracing is enabled by default in the Innexis Linux build. You can
  control this feature in the *local.conf* file to add or remove the
  feature in the kernel image.
 
  After compiling your image with tracing enabled, the *tracebox* binary
  will be available in the root file system. *Tracebox* is a *busybox*
  version that provides the combined functionality equivalent to the
  Android Open Source Project (AOSP) Perfetto binaries: *traced*,
  *traced_probes*, and *perfetto*.

###### Kernel Tracing

  Kernel tracing with Perfetto lets you capture a trace, visualize it,
  and capture kernel function graphs.

###### [Trace Configuration 3-25](#_bookmark48)

  [**Capture a Trace With Perfetto**
  **3-25**](#capture-a-trace-with-perfetto)
 
  [**Visualize a Trace** **3-26**](#visualize-a-trace)
 
  [**Capture Kernel Function Graphs** **3-26**](#_bookmark52)
 
  <span id="_bookmark48" class="anchor"></span>**Trace Configuration**
 
  Unlike many always-on logging systems, such as the Linux rsyslog and
  Android logcat, in Perfetto all tracing data sources are idle by
  default and record data only when instructed to do so. Data sources
  record data only when one (or more) tracing sessions are active. A
  tracing session is started by invoking the perfetto command-line
  client and passing a configuration specified in the configuration file
  (trace config).
 
  A trace config defines the general behavior of the tracing system.
  This encompasses the maximum duration of the trace, the number of
  in-memory buffers and their sizes, and the maximum size of the output
  trace file. It also includes which data sources to enable and
  configure. For kernel tracing, the behavior covers which ftrace events
  to enable, and for the heap profiler, the target process name and
  sampling rate.
 
  For more details, see the Perfetto [**reference
  documentation**](https://perfetto.dev/docs/concepts/config). The
  following is a simple trace config:

###### Capture a Trace With Perfetto

  To capture a trace with Perfetto, use the Tracebox binary with a trace
  config file and the name of the output file.

#### Procedure

  Run the following command:
 
  tracebox -o \<output_file_name\> --txt -c \<trace_config_file_name\>
 
  For example:
 
  tracebox -o trace_file.perfetto-trace --txt -c
  test/configs/scheduling.cfg

###### Visualize a Trace

  Visualize a captured trace by using Perfetto's dedicated web-based
  user interface.

#### Prerequisites

- You have captured a trace. See [**Capture a Trace With
  > Perfetto**](#capture-a-trace-with-perfetto).

#### Procedure

1.  Open the Perfetto UI in a browser.

  Use the following URL to access the Perfetto UI:
  [**https://ui.perfetto.dev/**](https://ui.perfetto.dev/)

2.  On the left-side navigation menu, click **Open trace file**, and
    > load the captured trace (by default this is at
    > */tmp/trace.perfetto-trace*).

3.  Explore the trace by zooming or panning using the WASD keys on your
    > keyboard and the mouse for expanding process tracks (rows) into
    > their constituent thread tracks.

  Press "?" for further navigation controls.

###### <img src="media/image5.jpeg" style="width:6.7524in;height:1.84896in" />Figure 3-1: Explore the Trace With Perfetto

  <span id="_bookmark52" class="anchor"></span>**Capture Kernel Function
  Graphs**
 
  Kernel function graphs can be useful for kernel tracing. It can show
  you specific kernel functions in the Perfetto UI. You just need to
  enable the function graph in your trace config.
 
  The following kernel configurations are already enabled for function
  tracing in the kernel:

#### Procedure

1.  Add the following fragment in your Perfetto trace config:

2.  Run the trace.

#### Results

  You will see the kernel function graph similar to the following:

<img src="media/image6.jpeg" style="width:7.13281in;height:1.92187in" />

###### User Space Tracing

  In user space, Perfetto enables adding annotations using Perfetto
  tracks. You can also profile applications using the Perfetto SDK.

###### [Add User-Space Annotations 3-28](#_bookmark54)

  [**Profile Applications Using the Perfetto SDK**
  **3-29**](#profile-applications-using-the-perfetto-sdk)
 
  <span id="_bookmark54" class="anchor"></span>**Add User-Space
  Annotations**
 
  Add annotations from user space into the perfetto tracks, so you can
  match changes in user space to changes in the kernel.

#### Procedure

1.  Add ftrace/print to your trace config.

2.  Capture the trace and write to */sys/kernel/tracing/trace_marker*
    > from your user-space application. Use the following format:

  Instant events: I\|\<pid\>\|\<message\>
 
  The following is an example using echo from the bash shell:
 
  echo "I\|\$\$\|Test Begins" \> /sys/kernel/tracing/trace_marker

#### Results

  The user-space annotation is added to your trace. For example: you
  will see the following marker in your trace.

<img src="media/image7.png" style="width:7.13469in;height:1.00396in" />

###### Profile Applications Using the Perfetto SDK

  You can profile user applications with the Perfetto SDK (libperfetto).

#### Prerequisites

- You have built and installed a Yocto Project SDK for the target image.

- You have access to the simple C++ example
  > (*perfetto_example_sdk.cpp*). The source code is available in the
  > Appendix: [**Sample Code for Profiling With
  > Perfetto**](#a.-sample-code-for-profiling-with-perfetto).

#### Procedure

1.  Source the environment setup file from the SDK installation
    > directory.

2.  Copy the C++ example code (*perfetto_example_sdk.cpp*).

3.  Compile the C++ example by linking it against the Perfetto SDK.

4.  Run the example.

  ./perfetto_example_bin

#### Results

  The example creates a trace file and outputs the following trace
  events:

- Draw Game

- Draw Player

  debug info: player number
 
  <img src="media/image8.jpeg" style="width:7.13281in;height:1.92187in" />

##### HDLCD

  HDLCD is an RGB streamer that reads the data from a framebuffer and
  displays on the graphical window created by Innexis-QEMU.

###### [Set Up and Run the Innexis Hybrid Linux Platform With HDLCD 3-30](#_bookmark57)

  [**Build Configuration for HDLCD**
  **3-31**](#build-configuration-for-hdlcd)
 
  <span id="_bookmark57" class="anchor"></span>**Set Up and Run the
  Innexis Hybrid Linux Platform With HDLCD**
 
  HDLCD is a feature specific to Innexis Hybrid, and it is enabled by
  default. However, you can control its availability on your hybrid
  platform with the CONFIG_DISPLAY='hdlcd' option.

#### Prerequisites

- You have installed Innexis Developer Pro and set up an Innexis Hybrid
  workspace. See **[Set Up an
  Innexis](#set-up-an-innexis-hybrid-workspace) [Hybrid
  Workspace](#set-up-an-innexis-hybrid-workspace)** for details.

#### Procedure

1.  Clone the Innexis Hybrid virtual platform.

  \$INNEXIS_DEVPRO_HOME/bin/innexis-clone
  \$INNEXIS_DEVPRO_HOME/platforms/ hybrid/linux example-platform

2.  Change to the *example-platform* directory and confirm that HDLCD is
    > enabled.

  cd example-platform
 
  \$INNEXIS_DEVPRO_HOME/bin/innexis-configure --list \| grep
 
  '^CONFIG_DISPLAY=' CONFIG_DISPLAY='hdlcd'

3.  (Optional) If you want to use the HDLCD display with Innexis-QEMU,
    > then ensure that this feature is enabled in the Innexis Linux
    > build (where it is also enabled by default).

  See **[Build Configuration for
  HDLCD](#build-configuration-for-hdlcd)** for details.

4.  Complete the innexis-arm64 build and boot the image.

  For booting instructions, see [**Run the Innexis Linux Image With
  Innexis Hybrid**](#run-the-innexis-linux-image-with-innexis-hybrid-1).

#### Results

  After it boots, the frambuffer device (such as: */dev/fb0*) will be
  available, and the data written to the framebuffer device appears on
  the display.

###### Build Configuration for HDLCD

  The HDLCD display is enabled by default in the Innexis Linux build, so
  you can use it with Innexis-QEMU. You can control this feature in the
  *local.conf* file to add or remove the corresponding drivers to the
  kernel image.

### IDE Connection Configuration for Innexis Hybrid

  To build, debug, and profile applications for the Innexis Hybrid
  platform, you must connect Innexis Hybrid to the Innexis CodeBench
  IDE.

###### [Set Up Port Forwarding for the Target 3-31](#_bookmark60)

  <span id="_bookmark60" class="anchor"></span>**Set Up Port Forwarding
  for the Target**
 
  Set up port forwarding for the target to make SSH and GDB connections
  from the Innexis CodeBench IDE workflows that are running on your
  host.
 
  **Prerequisites**

- You are running the Innexis Linux development image on the Innexis
  > Hybrid platform using the Questa simulator, and the kernel has
  > booted. For details on running the image, see [**Virtual Platform
  > BSPs**](#virtual-platform-bsps).

  When the kernel boots, the Linux kernel prompt displays in the QEMU
  UART console.

#### Procedure

1.  After the kernel boots, forward a host port (for example, 2222) to
    > the target’s port 22 for the SSH connection.

  Make a note of this host port to specify in the SSH connection in the
  Innexis CodeBench IDE workflows.

2.  Forward a host port (for example, 1234) to the same target port for
    > the GDB connection.

  Make a note of this host port to specify in the Linux GDB Server
  launch target in the Innexis CodeBench IDE workflows.

#### Results

  Innexis Hybrid can connect to the Innexis CodeBench IDE.
 
  To build, debug, and profile applications using the Innexis CodeBench
  IDE, see the following sections:

###### [Create a Project Using an SDK](#create-a-project-using-an-sdk-2)

- [**Build a Project**](#build-a-project)

- [**Debug Applications in the Innexis CodeBench
  > IDE**](#debug-applications-in-the-innexis-codebench-ide)

- [**Profile Applications in the Innexis CodeBench
  > IDE**](#profile-applications-in-the-innexis-codebench-ide)

## Innexis Architecture Native Acceleration

  Innexis™ Architecture Native Acceleration (ANA) software is a
  cloud-based high-speed virtual platform. It provides a simulation
  environment on which a user can model and run custom hardware and
  software. You can boot the Innexis Linux image in the ANA Arm64
  environment.
 
  You can boot the Innexis Linux image in the Innexis ANA environment.
  Use the image files that are included with your product installation
  or generated by performing an OS image build.

###### Table 3-10: Supported Title and Machine Name

<table>
<colgroup>
<col style="width: 54%" />
<col style="width: 45%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Supported Target</strong></p>
</blockquote></th>
<th><strong>Machine Name</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Innexis ANA</td>
<td>ana-arm64-flex</td>
</tr>
</tbody>
</table>

  The following types of image files can be used to quickly boot Innexis
  Linux on the target platform:

- **Prebuilt image files** — The prebuilt image files are included in
  your product installation. You can use these files without performing
  an OS image build. They are located in the
  *\<install-path\>/innexis-linux/*

  *\<version\>/\<machine-name\>/\<version\>/binary* directory.

- **Default image files** — The default image files are the image files
  generated when you run a build using the default settings for BSP.
  This build is called the default build. Performing a default build
  ensures that you can build image files using the Innexis Linux
  development platform.

  You can use the BitBake recipe “development-image” to build your
  image.
 
  After a successful build, you can find the image files in the
  *\<innexis-linux-workspace\>/\<build-dir\>/tmp/
  deploy/images/\<machine-name\>* directory.

###### Table 3-11: Image Files

<table>
<colgroup>
<col style="width: 18%" />
<col style="width: 31%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>File Type</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Prebuilt Image Files</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Default Image Files</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>Image</p>
</blockquote></td>
<td><blockquote>
<p><em>Image</em></p>
</blockquote></td>
<td><blockquote>
<p><em>Image</em></p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>Rootfs</p>
</blockquote></td>
<td><blockquote>
<p><em>development-image.ext4</em></p>
</blockquote></td>
<td><em>development-image-&lt;machine- name&gt;.rootfs.ext4</em></td>
</tr>
</tbody>
</table>

###### [Build Configuration for ANA. 3-33](#build-configuration-for-ana)

###### [Run the Innexis Linux Image in the ANA Arm64 Environment 3-34](#run-the-innexis-linux-image-in-the-ana-arm64-environment)

###### [Features for ANA 3-37](#features-for-ana)

###### [IDE Connection Configuration for Innexis ANA 3-61](#ide-connection-configuration-for-innexis-ana)

### Build Configuration for ANA

  You can enable additional functionality for your target image by
  modifying the build configuration file
  (*\<build-dir\>/conf/local.conf*) before building the target image.
  After modifying the configuration file, proceed with the build.
 
  For more information on building an Innexis Linux image, see [**OS
  Images**](#os-images-1).

#### Default Build

  By default, the following features are enabled in *development-image*:

- Virtualization

- Tracing

- Machine Learning

- On-target application and kernel module development

- Virtio-gpu

- EWAOL

  You cannot turn off EWAOL, but you can turn off the other features by
  modifying the *local.conf* file.

#### Add Extra Space to the Root File System (Optional)

  To increase the free space, if necessary, in the root file system of
  the image being generated, add the following line in *local.conf*:
 
  IMAGE_ROOTFS_EXTRA_SPACE:append = " + \<space-in-KBs-here\>"

### Run the Innexis Linux Image in the ANA Arm64 Environment

  Run the Innexis Linux image in the ANA Arm64 environment. Use the
  image files that are included with your product installation or
  generated by performing an OS image build.

#### Prerequisites

- You have an image you can use, either from the Graviton instance or
  > from an Innexis Linux build.

  For more information about build configuration, see [**Build
  Configuration for ANA**](#build-configuration-for-ana). You can use
  bitbake with the "development-image" recipe to build your image.
 
  To build your image, run the following commands:
 
  cd \<build-dir\>
 
  source setup-environment bitbake development-image
 
  After a build, image files are located in the
  *\<workspace\>/\<build-dir\>/tmp/deploy/images/\<machine- name\>*
  directory. For more information, see [**OS Images**](#os-images-1).

- You have access to the Innexis ANA web development tool.

#### Procedure

1.  Upload custom software to set up the Graviton instance.

    1.  Launch the ANA development tool in your web browser.

    2.  From the side navigation menu, click **Software**, click the
        > **Custom Software** and click **Upload Software**.

<img src="media/image9.png" style="width:6.30448in;height:1.76719in" />

3.  Upload the custom images, kernel Image and rootfs disk, to your
    > Graviton instance.

<img src="media/image10.png" style="width:6.4225in;height:1.8025in" />

2.  Create a new model instance.

    1.  From the side navigation menu, click **Lab Manager**.

    2.  On the Lab Manager page, click **Create** to go to the "Create a
        > new model instance" page.

    3.  Under Instance details, complete the following fields: Software
        > stack: custom

  Kernel Image: *\<uploaded_custom_image_file\>*
 
  Disk Image: *\<uploaded_custom_rootfs\>*
 
  Boot Args:

- serial console: console=ttyAMA0

- root directory: root=/dev/vda

- permissions for rootfs: rw

- disable kernel audit: audit=0

4.  Click **Finish**.

<img src="media/image11.png" style="width:6.37167in;height:3.175in" />

  Your model instance is listed in the **Lab Manager** tab.

3.  Run the model instance.

    1.  From the side navigation menu, click **Lab Manager**.

    2.  On the Lab Manager page, select the check box next to the model
        > instance name.

    3.  Click the **Start** icon (triangle) to run the model instance.

4.  Click the **Serial Console** tab to log into your system.

  <img src="media/image12.jpeg"
  style="width:6.79469in;height:3.39292in" />

#### Results

  On the Lab Manager page, the Status column indicates that the model
  instance is "running".

### Features for ANA

###### [VirtIO-GPU Support for Innexis ANA 3-37](#virtio-gpu-support-for-innexis-ana)

###### [EWAOL 3-56](#ewaol)

###### [On-Target Development and Debugging 3-57](#on-target-development-and-debugging)

###### [Tracing in ANA 3-61](#tracing-in-ana)

##### VirtIO-GPU Support for Innexis ANA

  This section provides an overview of the support for VirtIO-GPU
  acceleration for OpenGL and Vulkan on the Innexis Linux BSP for ANA.
  This integration enables hardware-accelerated rendering and compute
  shader workloads on Innexis ANA, reducing CPU overhead and improving
  graphics rendering performance.
 
  VirtIO-GPU is a paravirtualized graphics adapter that enables virtual
  machines to efficiently use host-side GPU resources. When Innexis ANA
  is hosted on EC2 instances powered by AWS Graviton2, it has access to
  the **[Nvidia
  T4G](https://www.nvidia.com/en-us/data-center/tesla-t4/)** GPU, which
  can be used to accelerate the OpenGL and Vulkan APIs within the
  Innexis Linux guest OS.
 
  These APIs can still be used in the guest OS even on instances without
  a GPU. However, in such cases, rendering will not be
  hardware-accelerated and will instead rely on software rendering,
  which uses the virtual CPUs of the VM.
 
  More details on configuration, setup, and troubleshooting will be
  covered in the subsequent sections.

###### [Build Configuration for VirtIO-GPU for ANA 3-38](#build-configuration-for-virtio-gpu-for-ana)

###### [Runtime Verification 3-38](#runtime-verification)

###### [Leverage VirtIO-GPU for Machine Learning 3-55](#leverage-virtio-gpu-for-machine-learning)

###### Build Configuration for VirtIO-GPU for ANA

  The VirtIO-GPU feature is enabled by default. Ensure that the
  following USER_FEATURES line for virtio-gpu is in *local.conf* file:
 
  Enabling virtio-gpu also enables graphics support, including
  Wayland/Weston desktop, and the TensorFlow Lite GPU delegate support
  for the BSP.
 
  For more information on building an image, see **[OS
  Images](#os-images-1)** or **[Run the Innexis Linux Image in the
  ANA](#run-the-innexis-linux-image-in-the-ana-arm64-environment) [Arm64
  Environment](#run-the-innexis-linux-image-in-the-ana-arm64-environment)**.

###### Runtime Verification

  With VirtIO-GPU enabled, you can perform various runtime verification
  tasks using the OpenGL and Vulkan APIs.
 
  **OpenGL** OpenGL is a cross-language, cross-platform API for
  rendering 2D and 3D vector graphics. This API can leverage supported
  GPUs for hardware-accelerated rendering.
 
  **Vulkan** Vulkan is a low-level, cross-platform API designed for 3D
  graphics and compute, offering low overhead and fine-grained control
  over GPU operations.

###### [Use OpenGL With GPU Acceleration 3-39](#use-opengl-with-gpu-acceleration)

  [**Benchmark the GPU Performance**
  **3-43**](#benchmark-the-gpu-performance)
 
  [**Use OpenGL With Software Rendering**
  **3-47**](#use-opengl-with-software-rendering)
 
  [**Benchmark the Software Rasterizer**
  **3-48**](#benchmark-the-software-rasterizer)
 
  [**Use Headless Vulkan with GPU Acceleration**
  **3-50**](#use-headless-vulkan-with-gpu-acceleration)
 
  [**Benchmark Vulkan Performance**
  **3-52**](#benchmark-vulkan-performance)
 
  [**Use Vulkan With a Software Rasterizer**
  **3-53**](#use-vulkan-with-a-software-rasterizer)
 
  [**Benchmark Vulkan With Software Rasterizer**
  **3-54**](#benchmark-vulkan-with-software-rasterizer)

###### Use OpenGL With GPU Acceleration

  Innexis Linux enables OpenGL host offloading by using QEMU emulation
  for the virtio-gpu-gl device. This setup uses the virgl driver - a
  Mesa Gallium component that serializes OpenGL and OpenGL ES commands
  over the VirtIO transport layer. On the host system, libvirglrenderer
  translates these serialized commands into native OpenGL calls. The
  host GPU then processes these native OpenGL calls to render the
  graphics as requested.
 
  **Prerequisites**

- Ensure that 'gpu' is enabled in your Innexis ANA model composition,
  > with 'opengl' mode selected. Refer to the Innexis ANA documentation
  > for details on the model setup.

- The Innexis Linux image is built with the virtio-gpu user feature. See
  > **[Build Configuration for
  > VirtIO-](#build-configuration-for-virtio-gpu-for-ana) [GPU for
  > ANA](#build-configuration-for-virtio-gpu-for-ana)** for details.

#### Procedure

1.  Check for the GPU device and render node.

  After the system boots, verify that the GPU device and its render node
  are available under */dev/dri*. The output should list multiple
  character device nodes, including cardX and renderDXXX.

2.  Identify the Virtio-GPU device.

  The system may also include a DRM device from the VKMS (Virtual Kernel
  Mode Setting) driver, which serves as a fallback for a virtual
  connector when Virtio-GPU is not available. To determine which GPU
  device node corresponds to Virtio-GPU over PCI, you can look through
  sysfs.
 
  This indicates that card1 is the character device node for Virtio-GPU
  in this case.

3.  Check the Weston output device.

  Weston, the Wayland compositor on Innexis Linux, uses the Virtio-GPU
  device over VKMS when available. Run the following command to
  determine the active GPU:
 
  <img src="media/image13.jpeg"
  style="width:6.74792in;height:3.96646in" />On the Innexis ANA Lab
  Manager page, you can see the Weston desktop on the **Virtual
  Display** tab.

4.  Check renderer and rendering capabilities.

  You can use utilities like eglinfo to inspect the EGL/GL capabilities
  of the detected GPU.

5.  Retrieve detailed DRM device information.

  You can use the drm_info utility to query detailed information about
  the Virtio-GPU DRM device, including driver details, device ID,
  supported framebuffer sizes, information about the corresponding
  connectors, encoders, CRTCs, and planes.
 
  root@ewaol-arm64:~# drm_info /dev/dri/card1 Node: /dev/dri/card1
 
  ├───Driver: virtio_gpu (virtio GPU) version 0.1.0
 
  │ ├───DRM_CLIENT_CAP_STEREO_3D supported
 
  │ ├───DRM_CLIENT_CAP_UNIVERSAL_PLANES supported
 
  │ ├───DRM_CLIENT_CAP_ATOMIC supported
 
  │ ├───DRM_CLIENT_CAP_ASPECT_RATIO supported
 
  │ ├───DRM_CLIENT_CAP_WRITEBACK_CONNECTORS supported
 
  │ ├───DRM_CLIENT_CAP_CURSOR_PLANE_HOTSPOT not supported
 
  │ ├───DRM_CAP_DUMB_BUFFER = 1
 
  │ ├───DRM_CAP_VBLANK_HIGH_CRTC = 1
 
  │ ├───DRM_CAP_DUMB_PREFERRED_DEPTH = 0
 
  │ ├───DRM_CAP_DUMB_PREFER_SHADOW = 0
 
  │ ├───DRM_CAP_PRIME = 3
 
  │ ├───DRM_CAP_TIMESTAMP_MONOTONIC = 1
 
  │ ├───DRM_CAP_ASYNC_PAGE_FLIP = 0
 
  │ ├───DRM_CAP_CURSOR_WIDTH = 64
 
  │ ├───DRM_CAP_CURSOR_HEIGHT = 64
 
  │ ├───DRM_CAP_ADDFB2_MODIFIERS = 0
 
  │ ├───DRM_CAP_PAGE_FLIP_TARGET = 0
 
  │ ├───DRM_CAP_CRTC_IN_VBLANK_EVENT = 1
 
  │ ├───DRM_CAP_SYNCOBJ = 1
 
  │ ├───DRM_CAP_SYNCOBJ_TIMELINE = 1
 
  │ └───DRM_CAP_ATOMIC_ASYNC_PAGE_FLIP not supported
 
  ├───Device: PCI 1af4:1050
 
  │ └───Available nodes: primary, render
 
  ├───Framebuffer size
 
  │ ├───Width: \[32, 8192\]
 
  │ └───Height: \[32, 8192\]
 
  ├───Connectors
 
  │ └───Connector 0
 
  │ ├───Object ID: 34
 
  │ ├───Type: virtual
 
  │ ├───Status: connected
 
  │ ├───Physical size: 320×180 mm
 
  │ ├───Subpixel: unknown
 
  │ ├───Encoders: {0}
 
  │ ├───Modes
 
  │ │ ├───[1280×720@75.00](mailto:720@75.00) preferred driver nhsync
  nvsync
 
  │ │ ├───[5120×2160@50.00](mailto:2160@50.00) driver phsync pvsync
  64:27
 
  │ │ ├───[4096×2160@50.00](mailto:2160@50.00) driver phsync pvsync
  256:135
 
  │ │ ├───[3840×2160@60.00](mailto:2160@60.00) driver phsync pvsync 16:9
 
  │ │ ├───[3840×2160@59.94](mailto:2160@59.94) driver phsync pvsync 16:9
 
  │ │ ├───[3840×2160@50.00](mailto:2160@50.00) driver phsync pvsync 16:9
 
  │ │ ├───[1920×1440@60.00](mailto:1440@60.00) driver nhsync pvsync
 
  │ │ ├───[2560×1080@50.00](mailto:1080@50.00) driver phsync pvsync
  64:27
 
  │ │ ├───[1856×1392@59.99](mailto:1392@59.99) driver nhsync pvsync
 
  │ │ ├───[1792×1344@60.00](mailto:1344@60.00) driver nhsync pvsync
 
  │ │ ├───[2048×1152@60.00](mailto:1152@60.00) driver phsync pvsync
 
  │ │ ├───[1920×1200@59.88](mailto:1200@59.88) driver nhsync pvsync
 
  │ │ ├───[1920×1080@60.00](mailto:1080@60.00) driver nhsync nvsync
 
  │ │ ├───[1920×1080@50.00](mailto:1080@50.00) driver phsync pvsync 16:9
 
  │ │ ├───[1600×1200@60.00](mailto:1200@60.00) driver phsync pvsync
 
  │ │ ├───[1680×1050@59.95](mailto:1050@59.95) driver nhsync pvsync
 
  │ │ ├───[1400×1050@59.98](mailto:1050@59.98) driver nhsync pvsync
 
  │ │ ├───[1280×1024@60.02](mailto:1024@60.02) driver phsync pvsync
 
  │ │ ├───[1440×900@59.89](mailto:900@59.89) driver nhsync pvsync
 
  │ │ ├───[1280×960@60.00](mailto:960@60.00) driver phsync pvsync
 
  │ │ ├───[1360×768@60.02](mailto:768@60.02) driver phsync pvsync
 
  │ │ ├───[1280×768@59.87](mailto:768@59.87) driver nhsync pvsync
 
  │ │ ├───[1024×768@60.00](mailto:768@60.00) driver nhsync nvsync
 
  │ │ ├───[800×600@60.32](mailto:600@60.32) driver phsync pvsync
 
  │ │ ├───[640×480@60.00](mailto:480@60.00) driver nhsync nvsync 4:3
 
  │ │ └───[640×480@59.94](mailto:480@59.94) driver nhsync nvsync
 
  │ └───Properties
 
  │ ├───"DPMS": enum {On, Standby, Suspend, Off} = Off
 
  │ ├───"link-status": enum {Good, Bad} = Good
 
  │ ├───"non-desktop" (immutable): range \[0, 1\] = 0
 
  │ ├───"TILE" (immutable): blob = 0
 
  │ ├───"CRTC_ID" (atomic): object CRTC = 0
 
  │ └───"EDID" (immutable): blob = 36
 
  ├───Encoders
 
  │ └───Encoder 0
 
  │ ├───Object ID: 35
 
  │ ├───Type: virtual
 
  │ ├───CRTCS: {0}
 
  │ └───Clones: {0}
 
  ├───CRTCs
 
  │ └───CRTC 0
 
  │ ├───Object ID: 33
 
  │ ├───Legacy info
 
  │ │ └───Gamma size: 0
 
  │ └───Properties
 
  │ ├───"ACTIVE" (atomic): range \[0, 1\] = 0
 
  │ ├───"MODE_ID" (atomic): blob = 0
 
  │ ├───"OUT_FENCE_PTR" (atomic): range \[0, UINT64_MAX\] = 0
 
  │ └───"VRR_ENABLED": range \[0, 1\] = 0
 
  └───Planes

└───Plane 0

  ├───Object ID: 31
 
  ├───CRTCs: {0}
 
  ├───Legacy info

<table>
<colgroup>
<col style="width: 93%" />
<col style="width: 4%" />
<col style="width: 2%" />
</colgroup>
<thead>
<tr class="header">
<th><p>├───"FB_ID" (atomic): object framebuffer = 0</p>
<p>├───"IN_FENCE_FD" (atomic): srange [-1, INT32_MAX] =</p></th>
<th>-1</th>
<th rowspan="2"></th>
</tr>
<tr class="odd">
<th>├───"CRTC_ID" (atomic): object CRTC = 0</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>├───"CRTC_X" (atomic): srange [INT32_MIN, INT32_MAX]</td>
<td>=</td>
<td>0</td>
</tr>
<tr class="even">
<td>├───"CRTC_Y" (atomic): srange [INT32_MIN, INT32_MAX]</td>
<td>=</td>
<td>0</td>
</tr>
<tr class="odd">
<td>├───"CRTC_W" (atomic): range [0, INT32_MAX] = 0</td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

###### Benchmark the GPU Performance

  Use GLMark2 to benchmark the GPU performance.

#### Procedure

  Run the glmark2-es2-wayland command.
 
  root@ewaol-arm64:~# glmark2-es2-wayland
 
  =======================================================
 
  glmark2 2023.01
 
  =======================================================
 
  OpenGL Information GL_VENDOR: Mesa
 
  GL_RENDERER: virgl (NVIDIA T4G/PCIe) GL_VERSION: OpenGL ES 3.1 Mesa
  24.3.4
 
  Surface Config: buf=32 r=8 g=8 b=8 a=8 depth=32 stencil=0 samples=0
  Surface Size: 800x600 windowed
 
  =======================================================
 
  \[build\] use-vbo=false: FPS: 199 FrameTime: 5.033 ms \[build\]
  use-vbo=true: FPS: 200 FrameTime: 5.024 ms
 
  \[texture\] texture-filter=nearest: FPS: 200 FrameTime: 5.023 ms
  \[texture\] texture-filter=linear: FPS: 394 FrameTime: 2.540 ms
  \[texture\] texture-filter=mipmap: FPS: 200 FrameTime: 5.025 ms
  \[shading\] shading=gouraud: FPS: 200 FrameTime: 5.015 ms \[shading\]
  shading=blinn-phong-inf: FPS: 199 FrameTime: 5.035 ms \[shading\]
  shading=phong: FPS: 199 FrameTime: 5.031 ms
 
  \[shading\] shading=cel: FPS: 199 FrameTime: 5.034 ms
 
  \[bump\] bump-render=high-poly: FPS: 199 FrameTime: 5.032 ms \[bump\]
  bump-render=normals: FPS: 5507 FrameTime: 0.182 ms \[bump\]
  bump-render=height: FPS: 5341 FrameTime: 0.187 ms
 
  \[effect2d\] kernel=0,1,0;1,-4,1;0,1,0;: FPS: 5698 FrameTime: 0.176 ms
 
  \[effect2d\] kernel=1,1,1,1,1;1,1,1,1,1;1,1,1,1,1;: FPS: 5633
  FrameTime:

178. ms

  \[pulsar\] light=false:quads=5:texture=false: FPS: 5281 FrameTime:
  0.189 ms \[desktop\]
  blur-radius=5:effect=blur:passes=1:separable=true:windows=4: FPS: 2322
  FrameTime: 0.431 ms
 
  \[desktop\] effect=shadow:windows=4: FPS: 3154 FrameTime: 0.317 ms
  \[buffer\] columns=200:interleave=false:update-dispersion=0.9:update-
  fraction=0.5:update-method=map: FPS: 99 FrameTime: 10.139 ms
  \[buffer\] columns=200:interleave=false:update-dispersion=0.9:update-
  fraction=0.5:update-method=subdata: FPS: 181 FrameTime: 5.542 ms
  \[buffer\] columns=200:interleave=true:update-dispersion=0.9:update-
  fraction=0.5:update-method=map: FPS: 99 FrameTime: 10.134 ms \[ideas\]
  speed=duration: FPS: 196 FrameTime: 5.116 ms
 
  \[jellyfish\] \<default\>: FPS: 199 FrameTime: 5.049 ms \[terrain\]
  \<default\>: FPS: 155 FrameTime: 6.471 ms \[shadow\] \<default\>: FPS:
  3906 FrameTime: 0.256 ms \[refract\] \<default\>: FPS: 180 FrameTime:
  5.568 ms
 
  \[conditionals\] fragment-steps=0:vertex-steps=0: FPS: 5598 FrameTime:
  0.179 ms
 
  \[conditionals\] fragment-steps=5:vertex-steps=0: FPS: 5619 FrameTime:
  0.178 ms
 
  \[conditionals\] fragment-steps=0:vertex-steps=5: FPS: 5481 FrameTime:
  0.182 ms
 
  \[function\] fragment-complexity=low:fragment-steps=5: FPS: 5595
  FrameTime:

179. ms

  \[function\] fragment-complexity=medium:fragment-steps=5: FPS: 5608
  FrameTime: 0.178 ms
 
  \[loop\] fragment-loop=false:fragment-steps=5:vertex-steps=5: FPS:
  5449 FrameTime: 0.184 ms
 
  \[loop\] fragment-steps=5:fragment-uniform=false:vertex-steps=5: FPS:
  5626 FrameTime: 0.178 ms
 
  \[loop\] fragment-steps=5:fragment-uniform=true:vertex-steps=5: FPS:
  5515 FrameTime: 0.181 ms
 
  =======================================================
 
  glmark2 Score: 2563
 
  =======================================================

#### Results

  During execution, various surfaces and objects are rendered. The
  following are examples:
 
  <img src="media/image14.jpeg"
  style="width:7.17719in;height:4.22187in" />

<img src="media/image15.jpeg"
style="width:6.83542in;height:4.02083in" />

  <img src="media/image16.jpeg"
  style="width:7.17719in;height:4.22187in" />

<img src="media/image17.jpeg"
style="width:6.83542in;height:4.02083in" />

  <img src="media/image18.jpeg"
  style="width:7.17719in;height:4.22187in" />

###### Use OpenGL With Software Rendering

  Innexis Linux supports OpenGL even when the platform does not have a
  dedicated GPU. Without a GPU, CPU-based software rendering is used
  instead, and the output is routed to the VKMS virtual connector.
 
  You can also force software rasterization on a GPU-enabled platform,
  if needed, and get a display too. For CPU-based rendering, the
  LLVMpipe software rasterizer is used. LLVMpipe is a highly optimized
  Mesa Gallium driver that uses LLVM for just-in-time (JIT) compilation
  of shaders. Unlike a pure CPU-based software rasterizer, LLVMpipe
  translates graphics operations into machine code on the fly,
  significantly improving performance.

#### Prerequisites

- To use software rendering, do one of the following:

  - Omit the GPU selection from the Innexis ANA model composition. Refer
    > to Innexis ANA documentation for details on the model setup.

  - Force software rasterization by setting the following environment
    > variables:

#### Procedure

1.  Check the Weston output device.

  If the Innexis ANA model has no GPU, then Weston renders to the VKMS
  virtual device.

2.  Check the active renderer.

  Run the following command to determine the OpenGL renderer in use:
 
  This shows that the Mesa Gallium LLVMpipe driver is being used.

###### Benchmark the Software Rasterizer

  Use GLMark2 to benchmark the software rasterizer.

#### Procedure

  Run the glmark2-es2-wayland command.
 
  Surface Config: buf=32 r=8 g=8 b=8 a=8 depth=32 stencil=0 samples=0
  Surface Size: 800x600 windowed
 
  =======================================================
 
  \[build\] use-vbo=false: FPS: 478 FrameTime: 2.092 ms \[build\]
  use-vbo=true: FPS: 464 FrameTime: 2.156 ms
 
  \[texture\] texture-filter=nearest: FPS: 1156 FrameTime: 0.866 ms
  \[texture\] texture-filter=linear: FPS: 1065 FrameTime: 0.939 ms
  \[texture\] texture-filter=mipmap: FPS: 758 FrameTime: 1.319 ms
  \[shading\] shading=gouraud: FPS: 290 FrameTime: 3.448 ms \[shading\]
  shading=blinn-phong-inf: FPS: 272 FrameTime: 3.687 ms \[shading\]
  shading=phong: FPS: 229 FrameTime: 4.369 ms
 
  \[shading\] shading=cel: FPS: 238 FrameTime: 4.215 ms
 
  \[bump\] bump-render=high-poly: FPS: 109 FrameTime: 9.219 ms \[bump\]
  bump-render=normals: FPS: 871 FrameTime: 1.149 ms \[bump\]
  bump-render=height: FPS: 886 FrameTime: 1.130 ms
 
  \[effect2d\] kernel=0,1,0;1,-4,1;0,1,0;: FPS: 549 FrameTime: 1.822 ms
  \[effect2d\] kernel=1,1,1,1,1;1,1,1,1,1;1,1,1,1,1;: FPS: 244
  FrameTime: 4.113
 
  ms
 
  \[pulsar\] light=false:quads=5:texture=false: FPS: 885 FrameTime:
  1.130 ms \[desktop\]
  blur-radius=5:effect=blur:passes=1:separable=true:windows=4: FPS:
 
  96 FrameTime: 10.444 ms
 
  \[desktop\] effect=shadow:windows=4: FPS: 260 FrameTime: 3.856 ms
  \[buffer\] columns=200:interleave=false:update-dispersion=0.9:update-
  fraction=0.5:update-method=map: FPS: 229 FrameTime: 4.381 ms
  \[buffer\] columns=200:interleave=false:update-dispersion=0.9:update-
  fraction=0.5:update-method=subdata: FPS: 230 FrameTime: 4.356 ms
  \[buffer\] columns=200:interleave=true:update-dispersion=0.9:update-
  fraction=0.5:update-method=map: FPS: 233 FrameTime: 4.299 ms \[ideas\]
  speed=duration: FPS: 336 FrameTime: 2.978 ms
 
  \[jellyfish\] \<default\>: FPS: 192 FrameTime: 5.233 ms \[terrain\]
  \<default\>: FPS: 10 FrameTime: 108.862 ms \[shadow\] \<default\>:
  FPS: 250 FrameTime: 4.001 ms \[refract\] \<default\>: FPS: 22
  FrameTime: 46.644 ms
 
  \[conditionals\] fragment-steps=0:vertex-steps=0: FPS: 579 FrameTime:
  1.729 ms \[conditionals\] fragment-steps=5:vertex-steps=0: FPS: 541
  FrameTime: 1.849 ms \[conditionals\] fragment-steps=0:vertex-steps=5:
  FPS: 539 FrameTime: 1.858 ms \[function\]
  fragment-complexity=low:fragment-steps=5: FPS: 560 FrameTime: 1.786 ms
 
  \[function\] fragment-complexity=medium:fragment-steps=5: FPS: 525
  FrameTime: 1.906 ms
 
  \[loop\] fragment-loop=false:fragment-steps=5:vertex-steps=5: FPS: 517
  FrameTime: 1.935 ms
 
  \[loop\] fragment-steps=5:fragment-uniform=false:vertex-steps=5: FPS:
  548 FrameTime: 1.825 ms
 
  \[loop\] fragment-steps=5:fragment-uniform=true:vertex-steps=5: FPS:
  516 FrameTime: 1.939 ms
 
  =======================================================
 
  glmark2 Score: 443
 
  =======================================================
 
  Observe the frames per second (FPS) and final score compared to
  GPU-accelerated benchmarking.

###### Use Headless Vulkan with GPU Acceleration

  Innexis Linux provides *experimental* support for Vulkan command
  serialization over the Virtio-GPU transport. Some of the Vulkan
  extensions reported by the Virtio-GPU may not function as expected;
  rendering to the display does not work with Nvidia GPUs on the host,
  and issues might arise when running the Vulkan conformance tests.
  However, general compute shader workloads and offscreen rendering have
  been demonstrated to work fine.
 
  The Vulkan command serialization over Virtio-GPU is enabled by the
  gfxstream-experimental Vulkan driver, installed as a separate Vulkan
  Installable Client Driver (ICD). Vulkan supports multiple ICDs
  concurrently, with the Vulkan loader library responsible for detecting
  available drivers on the system. The gfxstream- experimental driver
  was introduced with the release of Mesa 24.3.0. It is fairly recent,
  and it has
 
  issues with Nvidia drivers due to their inconsistent dmabuf support.
  QEMU facilitates this workflow using the virtio-gpu-rutabaga device
  emulation. Although virtio-gpu-rutabaga is supposed to support both
  Vulkan and OpenGL (using the Zink OpenGL-on-Vulkan driver) on Linux
  guests, the combination of QEMU, gfxstream and Zink also has issues
  with Nvidia GPUs. As a result, for accelerating OpenGL-based
  applications, Innexis Linux currently recommends using the
  virglrenderer, as described in **[Use
  OpenGL](#use-opengl-with-gpu-acceleration) [With GPU
  Acceleration](#use-opengl-with-gpu-acceleration)**.

#### Prerequisites

- Ensure that 'gpu' is enabled in your Innexis ANA model composition,
  with 'vulkan' mode selected. Refer to the Innexis ANA documentation
  for details on the model setup.

- The Innexis Linux image is built with the virtio-gpu user feature. See
  **[Build Configuration for
  VirtIO-](#build-configuration-for-virtio-gpu-for-ana) [GPU for
  ANA](#build-configuration-for-virtio-gpu-for-ana)** for details.

#### Procedure

1.  Check for the GPU device and render node.

  After the system boots, verify that the GPU device and its render node
  are available under */dev/dri*. The output should list multiple
  character device nodes, including cardX and renderDXXX.

2.  Check the Vulkan capabilities of the GPU.

  VIRTGPU_PARAM_EXPLICIT_DEBUG_NAME
 
  MESA: info: virtgpu backend not enabling
  VIRTGPU_PARAM_CREATE_FENCE_PASSING
 
  MESA: info: virtgpu backend not enabling
  VIRTGPU_PARAM_CREATE_GUEST_HANDLE
 
  ========== VULKANINFO
 
  ==========
 
  Vulkan Instance Version: 1.3.275
 
  Instance Extensions: count = 10
 
  -------------------------------
 
  VK_EXT_debug_report : extension revision 10
 
  VK_EXT_debug_utils : extension revision 2
  VK_KHR_external_fence_capabilities : extension revision 1
  VK_KHR_external_memory_capabilities : extension revision 1
  VK_KHR_external_semaphore_capabilities : extension revision 1
  VK_KHR_get_physical_device_properties2 : extension revision 2
  VK_KHR_portability_enumeration : extension revision 1 VK_KHR_surface :
  extension revision 25
 
  VK_KHR_wayland_surface : extension revision 6
  VK_LUNARG_direct_driver_loading : extension revision 1
 
  Instance Layers: count = 1
 
  --------------------------
 
  VK_LAYER_KHRONOS_validation Khronos Validation Layer 1.3.275 version 1
 
  Devices:
 
  ======== GPU0:
 
  apiVersion = 1.3.0
 
  driverVersion = 545.23.6.0 vendorID = 0x10de
 
  deviceID = 0x1eb4
 
  deviceType = PHYSICAL_DEVICE_TYPE_DISCRETE_GPU
 
  deviceName = NVIDIA T4G
 
  driverID = DRIVER_ID_NVIDIA_PROPRIETARY
 
  driverName = NVIDIA
 
  driverInfo = 545.23.06
 
  conformanceVersion = 1.3.6.0
 
  deviceUUID = 62c1b7cb-8e7f-b0a6-9538-17abdf7bbc07 driverUUID =
  4dc7d163-33e4-5c19-9065-8e7dbc672099
 
  This output confirms that the Nvidia T4G from the host is being used
  when exercising the gfxstream Vulkan ICD.

###### Benchmark Vulkan Performance

  Use vkmark, the Vulkan benchmarking suite, to measure various aspects
  of Vulkan performance. For now, it is only supported in headless mode.

#### Procedure

  Run vkmark.
 
  root@ewaol-arm64:~# vkmark --winsys=headless
 
  MESA: info: virtgpu backend not enabling
  VIRTGPU_PARAM_EXPLICIT_DEBUG_NAME MESA: info: virtgpu backend not
  enabling VIRTGPU_PARAM_CREATE_FENCE_PASSING MESA: info: virtgpu
  backend not enabling VIRTGPU_PARAM_CREATE_GUEST_HANDLE
 
  =======================================================
 
  vkmark 2025.01
 
  =======================================================
 
  Vendor ID: 0x10DE
 
  Device ID: 0x1EB4 Device Name: NVIDIA T4G Driver Version: 2286272896
 
  Device UUID: 42967c2338dc7459b26de58b7e6469e2
 
  =======================================================
 
  \[vertex\] device-local=true: FPS: 1936 FrameTime: 0.517 ms \[vertex\]
  device-local=false: FPS: 2126 FrameTime: 0.470 ms \[texture\]
  anisotropy=0: FPS: 2053 FrameTime: 0.487 ms \[texture\] anisotropy=16:
  FPS: 2051 FrameTime: 0.488 ms \[shading\] shading=gouraud: FPS: 2034
  FrameTime: 0.492 ms
 
  \[shading\] shading=blinn-phong-inf: FPS: 2040 FrameTime: 0.490 ms
  \[shading\] shading=phong: FPS: 1945 FrameTime: 0.514 ms
 
  \[shading\] shading=cel: FPS: 2035 FrameTime: 0.491 ms \[effect2d\]
  kernel=edge: FPS: 2055 FrameTime: 0.487 ms \[effect2d\] kernel=blur:
  FPS: 2053 FrameTime: 0.487 ms \[desktop\] \<default\>: FPS: 2041
  FrameTime: 0.490 ms \[cube\] \<default\>: FPS: 1929 FrameTime: 0.518
  ms \[clear\] \<default\>: FPS: 9277 FrameTime: 0.108 ms
 
  =======================================================
 
  vkmark Score: 2582
 
  =======================================================

###### Use Vulkan With a Software Rasterizer

  In the absence of a dedicated GPU in the Innexis ANA model, Innexis
  Linux automatically falls back
 
  to a software-based Vulkan implementation. Even on models equipped
  with a GPU, you can force the use of a CPU-based rasterizer by setting
  the VK_DRIVER_FILES environment variable. While the software
 
  Vulkan rasterizer is capable of rendering to a display on platforms
  with GPU (opengl selection) and display support, this section focuses
  on headless configurations for a direct performance comparison with
  the Virtio-GPU accelerated setup.
 
  Software-based Vulkan rendering is powered by the Mesa Lavapipe
  driver. Like the LLVMpipe Mesa OpenGL driver, Lavapipe leverages LLVM
  for just-in-time compilation, which makes it more optimized than a
  purely CPU-bound implementation.

#### Prerequisites

- To use software rendering, do one of the following:

  - Omit the 'gpu' selection from the Innexis ANA model composition.
    > Refer to Innexis ANA documentation for details on the model setup.

  - Force software rasterization by setting the following environment
    > variables:

  export VK_DRIVER_FILES=/usr/share/vulkan/icd.d/lvp_icd.aarch64.json

#### Procedure

1.  Check the Vulkan capabilities of the software rasterizer.

  Run vulkaninfo without arguments to display detailed information about
  the Vulkan API version, supported extensions, and device properties of
  the Lavapipe driver.
 
  VK_EXT_headless_surface : extension revision 1
  VK_EXT_surface_maintenance1 : extension revision 1
  VK_EXT_swapchain_colorspace : extension revision 5
  VK_KHR_device_group_creation : extension revision 1
  VK_KHR_external_fence_capabilities : extension revision 1
  VK_KHR_external_memory_capabilities : extension revision 1
  VK_KHR_external_semaphore_capabilities : extension revision 1
  VK_KHR_get_physical_device_properties2 : extension revision 2
  VK_KHR_get_surface_capabilities2 : extension revision 1
  VK_KHR_portability_enumeration : extension revision 1 VK_KHR_surface :
  extension revision 25 VK_KHR_surface_protected_capabilities :
  extension revision 1 VK_KHR_wayland_surface : extension revision 6
  VK_LUNARG_direct_driver_loading : extension revision 1
 
  Instance Layers: count = 1
 
  --------------------------
 
  VK_LAYER_KHRONOS_validation Khronos Validation Layer 1.3.275 version 1
 
  Devices:
 
  ======== GPU0:
 
  apiVersion = 1.3.296
 
  driverVersion = 0.0.1
 
  vendorID = 0x10005
 
  deviceID = 0x0000
 
  deviceType = PHYSICAL_DEVICE_TYPE_CPU deviceName = llvmpipe (LLVM
  19.1.6, 128 bits) driverID = DRIVER_ID_MESA_LLVMPIPE
 
  driverName = llvmpipe
 
  driverInfo = Mesa 24.3.4 (LLVM 19.1.6)
 
  conformanceVersion = 1.3.1.1
 
  deviceUUID = 6d657361-3234-2e33-2e34-000000000000 driverUUID =
  6c6c766d-7069-7065-5555-494400000000

2.  Review the output to ensure that the software rasterizer is active
    > and that the supported features match your expectations.

###### Benchmark Vulkan With Software Rasterizer

  Run vkmark in headless mode, under the software rasterizer
  configuration, to compare its performance against the Virtio-GPU
  accelerated setup.

#### Procedure

  Run vkmark.
 
  root@ewaol-arm64:~# vkmark --winsys=headless
 
  =======================================================
 
  vkmark 2025.01
 
  =======================================================
 
  Vendor ID: 0x10005
 
  Device ID: 0x0
 
  Device Name: llvmpipe (LLVM 19.1.6, 128 bits) Driver Version: 1

Device UUID: 32342e332e3461616161616161616161

  =======================================================
 
  \[vertex\] device-local=true: FPS: 561 FrameTime: 1.783 ms \[vertex\]
  device-local=false: FPS: 563 FrameTime: 1.776 ms \[texture\]
  anisotropy=0: FPS: 1388 FrameTime: 0.720 ms \[texture\] anisotropy=16:
  FPS: 1 FrameTime: 1000.000 ms \[shading\] shading=gouraud: FPS: 325
  FrameTime: 3.077 ms
 
  \[shading\] shading=blinn-phong-inf: FPS: 316 FrameTime: 3.165 ms
  \[shading\] shading=phong: FPS: 266 FrameTime: 3.759 ms
 
  \[shading\] shading=cel: FPS: 268 FrameTime: 3.731 ms \[effect2d\]
  kernel=edge: FPS: 536 FrameTime: 1.866 ms \[effect2d\] kernel=blur:
  FPS: 224 FrameTime: 4.464 ms \[desktop\] \<default\>: FPS: 546
  FrameTime: 1.832 ms \[cube\] \<default\>: FPS: 3487 FrameTime: 0.287
  ms \[clear\] \<default\>: FPS: 2241 FrameTime: 0.446 ms
 
  =======================================================
 
  vkmark Score: 824
 
  =======================================================

#### Results

  The benchmark results indicate that the performance with the Lavapipe
  software rasterizer is significantly lower than that achieved with
  Virtio-GPU acceleration.

###### Leverage VirtIO-GPU for Machine Learning

  You can use VirtIO-GPU within machine learning (ML) applications on
  Innexis ANA. When the virtio-gpu user feature is enabled in the
  Innexis Linux build, the TensorFlow Lite GPU delegate is also enabled
  as part of the ML support. This delegate leverages the OpenGL ES API,
  which is accelerated by the Virtio-GPU.
 
  On Innexis ANA, Virtio-GPU exposes the host's Nvidia T4G capabilties
  to the guest OS. The TFLite GPU delegate converts the standard
  TensorFlow Lite model into an optimized computational graph.
  Operations that can benefit from parallel execution (such as matrix
  multiplication, convolutions, and activation functions) on the GPU are
  converted into OpenGL ES compute shaders. By offloading these
  operations
 
  to the GPU, inference performance is improved and CPU usage is
  reduced.

#### Procedure

1.  To use Virtio-GPU within ML applications, ensure that an
    > OpenGL-capable GPU is selected in the device model.

2.  Confirm that the correct GPU device is selected for inference.

  For example, if the Virtio-GPU DRM device is identified as
  */dev/dri/card1* (see **[Use OpenGL
  With](#use-opengl-with-gpu-acceleration) [GPU
  Acceleration](#use-opengl-with-gpu-acceleration)**), configure Innexis
  Linux ML demos to use this device by using the option
 
  --compute=gpu and setting the appropriate environment variable:
 
  export FLEXML_RENDER_NODE="/dev/dri/card1"
 
  For more information, see [**Machine Learning**](#machine-learning).

##### EWAOL

  The Edge Workload Abstraction and Orchestration Layer (EWAOL) project
  provides users with a standards- based framework using containers for
  the deployment and orchestration of applications on edge platforms.
  EWAOL is the reference implementation for Scalable Open Architecture
  For Embedded Edge (SOAFEE); it is an industry initiative led by Arm to
  leverage the benefits of cloud-native software development and provide
  solutions to the challenges of real-time and functional safety in
  automotive systems.
 
  EWAOL is provided as the meta-ewaol repository, which includes
  metadata for building EWAOL distribution images using the Yocto
  Project. The Innexis Linux reference BSP for the Innexis Architecture
  Native Acceleration (ANA) guest provides a seamless integration with
  meta-ewaol. The chosen EWAOL version
 
  is 2.0.0 and the integration supports the baremetal EWAOL system
  architecture for this release. For more information on SOAFEE and
  EWAOL see
  [**https://meta-ewaol.docs.soafee.io/en/latest/**](https://meta-ewaol.docs.soafee.io/en/latest/)

###### [Build Configuration for EWAOL. 3-56](#_bookmark80)

  <span id="_bookmark80" class="anchor"></span>**Build Configuration for
  EWAOL**
 
  The Innexis ANA BSP is set to build with the EWAOL baremetal system
  architecture integration by default. There is no user input needed to
  build it.

##### On-Target Development and Debugging

  Innexis Linux supports on-target user application development.

###### [Build Configuration for On-Target Development and Debugging 3-57](#build-configuration-for-on-target-development-and-debugging)

###### [Test the Development Environment 3-58](#test-the-development-environment)

###### [Compile the User Space Application 3-58](#compile-the-user-space-application)

###### [Debug an Application on the Target 3-59](#debug-an-application-on-the-target)

###### [Compile a Kernel Module 3-59](#compile-a-kernel-module)

###### Build Configuration for On-Target Development and Debugging

  On-target application and kernel development is enabled by default.
  You can enable debugging by modifying the *local.conf*.
 
  For on-target application and kernel development, you can see the
  following lines in the *local.conf* file:
 
  EXTRA_IMAGE_FEATURES:append = " kerneldev-pkgs target-sdk"
 
  This includes important development packages in the rootfs, such as
  binutils, make, gcc, libstdc++ etc along with the kernel source code.
 
  To enable user application debugging add the following to your
  *local.conf*:
 
  EXTRA_IMAGE_FEATURES:append = " tools-debug"
 
  This includes gdb and strace in the generated rootfs. After modifying
  the file, build the image. For more information on building an Innexis
  Linux image, see [**OS Images**](#os-images-1).

###### Test the Development Environment

  When you have logged into the system, you can test the development
  environment by verifying the presence of the following tools: GCC,
  Make, and include files.

#### Prerequisites

- You have built and booted the OS image with support for on-target user
  > application development. See

  **[Build Configuration for On-Target Development and
  Debugging](#build-configuration-for-on-target-development-and-debugging)**
  for more details.

#### Procedure

1.  Check for GCC.

  gcc -v

2.  Check for Make.

  make -v

3.  Verify the include files available on the target.

  ls /usr/include

#### Results

  The commands return the gcc and GNU Make versions., as well as the
  include files.

###### Compile the User Space Application

  Compile the user space application on the target.

#### Prerequisites

- You have built and booted the OS image with support for on-target user
  > application development. See

  **[Build Configuration for On-Target Development and
  Debugging](#build-configuration-for-on-target-development-and-debugging)**
  for more details.

- You have validated the tools on your system as described in [**Test
  > the Development Environment**](#test-the-development-environment).

#### Procedure

1.  Copy the source code to the target.

2.  Run the following command to edit the application source.

  vi \<source_code_file\>.c

3.  Compile the application.

  gcc -o \<executable_name\> \<source_code_file\>.c -l \<libraries to
  compile against\>

###### Debug an Application on the Target

  Debug an application using gdb.

#### Prerequisites

- You have built and booted the OS image with support for on-target user
  > application debugging. See

  **[Build Configuration for On-Target Development and
  Debugging](#build-configuration-for-on-target-development-and-debugging)**
  for more details.

#### Procedure

1.  Build the application with debugging support.

  gcc -o \<executable_name\> -g \<source files\>

2.  Debug with gdb.

  gdb \<executable_name\>
 
  gdb will read the symbols and take you into the gdb prompt.

3.  Set a breakpoint.

  (gdb) break \<source_file\>:\<line_number\>

4.  Run the program.

  (gdb) run
 
  Execution halts at the breakpoint you set.

5.  Resume execution.

  (gdb) continue

###### Compile a Kernel Module

  Compile and validate a kernel module.

#### Prerequisites

- You have built an OS image with support for on-target kernel module
  > development.
  > See**[Build](#build-configuration-for-on-target-development-and-debugging)
  > [Configuration for On-Target Development and
  > Debugging](#build-configuration-for-on-target-development-and-debugging)**
  > for more details.

- You have prepared the kernel source before starting development.

  cd /usr/src/kernel && make scripts prepare modules_prepare
 
  After the module preparation is complete, ensure that you change your
  current directory back; otherwise, you can end up tainting the kernel
  source.

#### Procedure

1.  Specify the path to the kernel source and define the compiler in
    > your makefile. The following is a simple Makefile:

  Edit *\<kernel_module_name\>* for your kernel module.

2.  Copy your kernel module source code to the rootfs.

3.  Edit the kernel module source code.

  vi \<kernel_module\>.c

4.  Add the kernel module name to your Makefile and compile it.

  make

5.  After compiling the kernel module, validate it.

    1.  Load the kernel module.

  insmod kernel_module.ko

2.  View the kernel debug prints.

  dmesg \| tail

##### Tracing in ANA

  Innexis Linux includes tracing and profiling features, which are
  widely-used techniques for performance analysis. The virtual platform
  BSPs, Innexis Hybrid and ANA, both support these features using
  Perfetto.
 
  For details on build configuration, kernel, and user-space tracing,
  see **[Tracing](#tracing)** in the **[Features for
  Innexis](#features-for-innexis-hybrid)
  [Hybrid](#features-for-innexis-hybrid)** section.

### IDE Connection Configuration for Innexis ANA

  To build, debug, and profile applications for the Innexis ANA
  platform, you must connect ANA to the Innexis CodeBench IDE.

###### [Set Up the ANA Graviton Instance to Connect to the Innexis CodeBench IDE 3-61](#_bookmark89)

  <span id="_bookmark89" class="anchor"></span>**Set Up the ANA Graviton
  Instance to Connect to the Innexis CodeBench IDE**
 
  Set up the ANA Graviton model instance to connect to the Innexis
  CodeBench IDE to debug and profile applications on ANA.
 
  **Prerequisites**

- ANA is booted with the latest image on the Graviton instance.

- Innexis CodeBench is installed on the Linux host.

- The SDK is built and installed on the Innexis CodeBench IDE.

- The Linux host has access to the Innexis ANA Graviton chamber URL.

#### Procedure

1.  Note down the static IP address, Access URL, gateway, subnet, free
    > TCP port, and SSH port forwarding information for the model
    > instance from the Graviton chamber.

    1.  On the Lab Manager page, click the running model instance.

    2.  Click the **General** tab.

  The static IP address, gateway, and subnet are under the **Network
  Information** section. The Access URL, SSH port, and TCP port are in
  the **Devices and Ports Access** section.

2.  Configure the IP address and netmask for a network interface on the
    > running model instance using the **Serial Console** on the
    > Graviton chamber.

3.  Add a default gateway to your system's routing table.

  route add default gw \<gateway-ip-address\>
 
  These changes will be lost upon restarting the guest OS. To make these
  persistent for the image in use, create a configuration file
  (*/etc/systemd/network/10-static-enp1s0.network*) and add the
  following contents:

#### Results

  You can use the network and port information you collected in Step 1
  to connect the ANA Graviton instance to the Innexis CodeBench IDE.
 
  The Access URL is used to access the model instance from the Internet.
  The external port against target port SSH 22 is used to create a
  connection to the Innexis CodeBench IDE. The free TCP port will be
  used by the Innexis CodeBench IDE to connect to the GDB server on the
  target.
 
  To build, debug, and profile applications using the Innexis CodeBench
  IDE, see the following sections:

###### [Create a Project Using an SDK](#create-a-project-using-an-sdk-2)

- [**Build a Project**](#build-a-project)

- [**Debug Applications in the Innexis CodeBench
  IDE**](#debug-applications-in-the-innexis-codebench-ide)

- [**Profile Applications in the Innexis CodeBench
  IDE**](#profile-applications-in-the-innexis-codebench-ide)

# Adding and Modifying Packages and Recipes

  Customize your project by adding new packages. Add packages to builds
  with recipes. Recipes are organized into layers.

###### [Innexis Linux Layout 4-1](#innexis-linux-layout)

###### [Layers. 4-2](#_bookmark94)

###### [Recipes 4-6](#_bookmark99)

###### [Modify an Existing Package (Adding a Patch) 4-12](#_bookmark106)

###### [Use a Custom BusyBox Configuration 4-14](#use-a-custom-busybox-configuration-1)

###### [Rebuild a Package for a Project That Uses a Cached Binary Mirror 4-15](#rebuild-a-package-for-a-project-that-uses-a-cached-binary-mirror)

## Innexis Linux Layout

  The Innexis Linux build system supports organization of metadata into
  multiple layers. Layers provide a practical way to partition work and
  facilitate maintenance and reuse of metadata.
 
  An Innexis Linux installation consists of the following elements:

- Metadata

- Configuration and setup utilities
  (*\<innexis-linux-workspace\>/meta-flex/scripts*)

- OE-Core (*\<innexis-linux-workspace\>/oe-core*) and Bitbake
  (*\<innexis-linux-workspace\>/bitbake*) components

- Board support files

- Reference images

- Sources

  The following table describes some components of a typical Innexis
  Linux installation:

###### Table 4-12: Installation Components

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 66%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Component</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>oe-core</td>
<td>The OpenEmbedded (OE) core metadata. It contains support for x86,
PowerPC, Arm®, and MIPS architectures, qemu-emulated machines, and
common recipes most developers need.</td>
</tr>
<tr class="even">
<td>meta-oe</td>
<td>A collection of layers from the OE core community.</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 66%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Component</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>meta-flex</td>
<td><blockquote>
<p>Defines common attributes of the distribution and local Innexis
Linux-specific overrides.</p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>(Optional) machine layer(s)</p>
</blockquote></td>
<td>Contains machine configuration, kernel, and boot loader
recipes.</td>
</tr>
</tbody>
</table>

  The following table summarizes the file types and extensions in the
  build system.

###### Table 4-13: Build System Files and Extensions

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 66%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>File Type</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Extension</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>Append File</p>
</blockquote></td>
<td><blockquote>
<p><em>.bbappend</em></p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>Configuration File</p>
</blockquote></td>
<td><blockquote>
<p><em>.conf</em></p>
</blockquote></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>Recipe</p>
</blockquote></td>
<td><blockquote>
<p><em>.bb</em></p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>Class</p>
</blockquote></td>
<td><blockquote>
<p><em>.bbclass</em></p>
</blockquote></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>Task</p>
</blockquote></td>
<td><blockquote>
<p><em>.bb</em></p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>Include File</p>
</blockquote></td>
<td><em>.inc</em></td>
</tr>
</tbody>
</table>

  **Related Topics**
 
  [**Layers**](#_bookmark94)
 
  <span id="_bookmark94" class="anchor"></span>**Layers**
 
  If you want to add a new application to a project, it is recommended
  to add it to a new layer rather than appending it to an existing
  layer. You do not need to create a new layer for *each* new
  application you create. Layers can be used to group related software
  packages together.
 
  To create a layer, create a new directory that contains at least a
  *conf* and optionally a *recipes* directory. It can also contain other
  directories as needed. See **[Table
  4-14](#table-4-14-common-layer-directories)** for examples.

###### Table 4-14: Common Layer Directories

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 51%" />
<col style="width: 24%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Directory Name</strong></p>
</blockquote></th>
<th><strong>Description</strong></th>
<th><strong>Mandatory</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>classes</em></td>
<td>Add user-defined classes to this directory.</td>
<td><blockquote>
<p>No</p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p><em>conf</em></p>
</blockquote></td>
<td><blockquote>
<p>Use this when you are creating a</p>
</blockquote>
<p>custom platform or modifying your platform configuration.</p></td>
<td>Yes</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 51%" />
<col style="width: 24%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Directory Name</strong></p>
</blockquote></th>
<th><strong>Description</strong></th>
<th><strong>Mandatory</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>recipes/&lt;recipe&gt;</em></td>
<td><p>Place <strong><a href="#simple-recipe-file">Simple Recipe
File</a></strong> and/or <strong><a href="#_bookmark106">Modify an</a>
<a href="#_bookmark106">Existing Package (Adding a Patch)</a></strong>
that describe or modify recipes in this directory.</p>
<p>For some layers, recipes are broken up. Rather than having a single
<em>recipes</em> directory, there will be directories such as
<em>recipes-kernel</em> or <em>recipes- graphics</em>. For proper
configuration, the BBFILES variable in the layer configuration file will
need to be set accordingly.</p></td>
<td>Yes</td>
</tr>
<tr class="even">
<td><p><em>recipes/&lt;recipe&gt;/</em></p>
<p><em>&lt;recipe-basename&gt;</em></p>
<p>where <em>&lt;recipe- basename&gt;</em> should match the name</p>
<p>of the <em>recipe</em> or <em>bbappend</em> file that the source
files are used in.</p></td>
<td><p>Put any local sources that are associated with the recipe or
append file here.</p>
<p>For example, if you have a busybox recipe in your layer that contains
a</p>
<p><em>busybox_2.2.1.bbappend</em> file in its <em>recipes</em>
directory and you have source files that are local, you must place them
in the <em>recipes/ busybox/busybox-2.2.1</em> directory. You must also
add this directory to the search path by using the FILESEXTRAPATHS
variable in the bbappend file.</p></td>
<td>No</td>
</tr>
<tr class="odd">
<td><em>site</em></td>
<td>Use to specify GNU autotools site information based on GNU
configurations.</td>
<td>No</td>
</tr>
</tbody>
</table>

  <span id="_bookmark96" class="anchor"></span>**Create a Layer**
 
  As a best practice, you should create a new layer when you are adding
  packages or recipes.
 
  **Prerequisites**

- You have created the project directory. For details, refer to [**Set
  Up the Build Environment**](#set-up-the-build-environment).

#### Procedure

1.  Check existing layers. You must ensure that a layer with the same
    > name does not exist.

2.  In the project directory, create a directory for your layer. For
    > example:

3.  Create a *conf* directory within your layer:

  mkdir -p mylayer/conf

4.  Inside the *conf* directory, create a *layer.conf* file. The
    > following file demonstrates the required syntax:

5.  Create a *recipes* directory within your layer:

  mkdir -p mylayer/recipes

6.  For each recipe that you want to create or modify, create a
    > *\<recipe_name\>* directory inside your

  *recipes* directory.

7.  Add content to your layer. See [**Simple Recipe
    > File**](#simple-recipe-file).

#### Results

  Now that you have created your layer, you must enable it. See
  [**Enable a Layer**](#_bookmark97).
 
  <span id="_bookmark97" class="anchor"></span>**Enable a Layer**
 
  The *bblayers.conf* file, generated during initial configuration,
  includes a list of layers in the BBLAYERS variable. BitBake adds the
  contents of each layer to the build. You can enable your layer during
  configuration.

#### Prerequisites

- A layer has been created. See [**Create a Layer**](#_bookmark96).

#### Procedure

1.  Edit the *bblayers.conf* file in the
    > *\<innexis-linux-workspace\>/\<build-dir\>/conf* directory.

2.  Add the *layer* directory to the BBLAYERS variable.

3.  After you have enabled your layer, prioritize it. See [**Prioritize
    > a Layer**](#prioritize-a-layer).

#### Examples

  The following shows an example of a custom layer being added to the
  *bblayer.conf* file. The custom layer is
  */home/user/myproject/mylayer*.

### Prioritize a Layer

  Each layer has a priority value that controls the precedence in case
  there are recipe files with the same name in multiple layers. Higher
  priority number indicates higher precedence.
 
  If there are multiple versions of a single recipe, the priority of the
  layer supersedes the version of the recipe. For example: A
  lower-version of a recipe in a higher-priority layer is used in
  preference to a higher-version of a recipe in a lower-priority layer.
  To force a specific version to be used, use the PREFERRED_VERSION
  recipe variable:
 
  PREFERRED_VERSION\_\<recipename\> = "\<version\>"

#### Prerequisites

- A layer has been created and enabled. See **[Create a
  > Layer](#_bookmark96)** and [**Enable a Layer**](#_bookmark97).

#### Procedure

  To specify the layer’s priority, use the BBFILE_PRIORITY variable in
  your *layer.conf* file:
 
  BBFILE_PRIORITY := "6"

#### Related Topics

###### [Use a Custom BusyBox Configuration](#use-a-custom-busybox-configuration-1)

  <span id="_bookmark99" class="anchor"></span>**Recipes**
 
  A recipe is a set of instructions that describes what needs to be done
  to retrieve the source code for
 
  some application, apply any necessary patches, provide any additional
  files (such as init scripts), compile it, install it, and generate
  binary packages. The end result is a set of binary packages that you
  can install on your target device and possibly some intermediate
  files, such as libraries and headers, which can be used when building
  other applications.
 
  The following table contains some basic recipes for common packages
  built with most BSPs.

###### Table 4-15: BitBake Recipes

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 75%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Recipe</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>development-image</p>
</blockquote></td>
<td><blockquote>
<p>Creates a basic BSP that includes the following image features:</p>
</blockquote>
<ul>
<li><blockquote>
<p>debug-tweaks</p>
</blockquote></li>
<li><blockquote>
<p>codebench-debug</p>
</blockquote></li>
<li><blockquote>
<p>ssh-server-openssh</p>
</blockquote></li>
<li><blockquote>
<p>tools-profile.</p>
</blockquote></li>
</ul></td>
</tr>
<tr class="even">
<td><blockquote>
<p>virtual/bootloader</p>
</blockquote></td>
<td>Builds the boot loader.</td>
</tr>
<tr class="odd">
<td>virtual/kernel</td>
<td>Builds the kernel image for the target.</td>
</tr>
<tr class="even">
<td>busybox</td>
<td>Builds the busybox application.</td>
</tr>
</tbody>
</table>

  For more information on layers, see the section, “Writing a New
  Recipe”, in the latest Yocto Project documentation at the following
  web address:
  [**https://docs.yoctoproject.org/5.0.3/ref-manual/index.html**](https://docs.yoctoproject.org/5.0.3/ref-manual/index.html)

###### [Simple Recipe File 4-7](#simple-recipe-file)

###### [Package Groups 4-8](#package-groups)

###### [Add Recipe Artifacts to the Image 4-8](#_bookmark103)

###### [Create a HelloDemo Package 4-9](#_bookmark104)

###### [Append Files 4-11](#append-files)

### Simple Recipe File

  The following recipe file builds an application from a single local
  file. The file lists the source file in the SRC_URI variable. It also
  defines the do_compile and do_install tasks.

### Package Groups

  A package group is a special recipe that is often used to group
  packages together. For example, the
 
  task-base recipe in
  *\<innexis_linux_install\>/oe-core/meta/recipes-core/tasks* groups
  base packages together to create a basic root file system.
 
  For more information on layers, see section, “Customizing Images Using
  Custom Package Groups” in the latest Yocto Project documentation at
  the following web address:

###### <https://docs.yoctoproject.org/5.0.3/ref-manual/index.html>

  **Related Topics**
 
  [**Create a HelloDemo Package**](#_bookmark104)
 
  [**Modify an Existing Package (Adding a Patch)**](#_bookmark106)
 
  <span id="_bookmark103" class="anchor"></span>**Add Recipe Artifacts
  to the Image**
 
  Recipes create objects, often binary programs and/or libraries that
  you want to add to your final root file system image. You can also
  customize an image using this method.
 
  **Prerequisites**

- You have created a build or project directory. For details, refer to
  [**Set Up the Build Environment**](#set-up-the-build-environment).

#### Procedure

1.  Edit *local.conf* for BitBake to add the recipe’s binary output to
    > the image:

  CORE_IMAGE_EXTRA_INSTALL += "package_name"

2.  Rebuild the target:

  bitbake development-image

#### Related Topics

###### [Modify an Existing Package (Adding a Patch)](#_bookmark106)

  **[Rebuild a Package for a Project That Uses a Cached Binary
  Mirror](#rebuild-a-package-for-a-project-that-uses-a-cached-binary-mirror)
  [Adding and Modifying Packages and
  Recipes](#adding-and-modifying-packages-and-recipes)**
 
  <span id="_bookmark104" class="anchor"></span>**Create a HelloDemo
  Package**
 
  To add a new software application or library to your image, you need
  to write a recipe for it. In this example, you add a “hellodemo”
  recipe to a project for a target running Linux.

#### Procedure

1.  Navigate to the project directory. For example:

  cd myproject

2.  Add the following directories to your layer for the new application.
    > See [**Simple Recipe File**](#simple-recipe-file):

  In this example, *mylayer* is the layer directory for the hellodemo
  application.

3.  Create *hellodemo.c* and place it in
    > *mylayer/recipes/hellodemo/hellodemo-1.0*:

4.  Create a *hellodemo_1.0.bb* recipe file for the hellodemo
    > application and place it in *mylayer/recipes/ hellodemo/*.

  In this recipe, the \${PN} variable is the package name, \${PV} is the
  package version, and \${D} is the image or destination directory.
  Refer to the Yocto Project documentation for a complete description of
  recipe file syntax.

5.  Add the layer to the *bblayers.conf* file.

6.  Use bitbake to build the image:

  bitbake development-image

#### Results

  This puts the *hellodemo* application in */usr/bin* in the root file
  system.

#### Related Topics

###### [Set Up the Build Environment](#set-up-the-build-environment) [Build the Target Image](#build-the-target-image)

### Append Files

  Append files extend or modify existing recipes.
 
  Create an append file when you want to modify a recipe that is part of
  another layer, especially when that layer is provided by another
  entity, such as a vendor. Like patch files, append files let you
  maintain changes to a recipe separately from the original recipe.
  Append files have the same syntax and capabilities as a recipe, but
  they have the *.bbappend* file extension.
 
  **Format**
 
  Append files have the following restrictions:

- File name for the *.bbappend* file must match the file name of the
  recipe to which the append is being applied. If your recipe is
  *hello.bb*, create a *hello.bbappend*. To get a list of all the
  recipes in your project, run the command **bitbake -s**.

- Append files should reside in a *\<user_layer\>/recipes/\<recipe\>*
  directory.

- Append files can contain any variable that you want to modify.

- Use variable assignment operators to modify the value of variables
  that are in the *\<recipe\>.bb* file that the *\<recipe\>.bbappend*
  file modifies.

- If an append file overrides a configuration file or adds a new patch,
  it must set the FILESEXTRAPATHS variable.

  The *\<recipe\>.bbappend* file has the following format:

#### Parameters

- For a list of parameters (variables, methods, and so on) that you can
  add to a .*bbappend* file, consult the Yocto Project documentation.

  For more information on layers, see section, “Appending Other Layers
  Metadata With Your Layer” in the latest Yocto Project documentation at
  the following web address:
  **[https://docs.yoctoproject.org/5.0.3/](https://docs.yoctoproject.org/5.0.3/ref-manual/index.html)
  [ref-manual/index.html](https://docs.yoctoproject.org/5.0.3/ref-manual/index.html)**

#### Examples

  The following example is from
  */meta-flex/recipes/busybox/busybox_1.2x.2.bbappend*:
 
  The Innexis Linux installation includes complex examples of using
  *\<recipe\>.bbappend* that involve a
 
  large number of recipes. For example, the
  */oe-core/meta/recipes-devtools/python* directory contains several
  different recipes (*.bb* files). As an example, to modify the
  *python-native_2.7.2.bb* recipe, you must create
 
  a */recipes/python* directory in your layer and add a
  *python-native_2.7.2.bbappend* file that contains the following text:

#### Related Topics

###### [Adding and Modifying Packages and Recipes](#adding-and-modifying-packages-and-recipes) [Layers](#_bookmark94)

  <span id="_bookmark106" class="anchor"></span>**Modify an Existing
  Package (Adding a Patch)**
 
  You have a completed build, but you want to change something in it,
  perhaps a code correction or add an additional application. To add
  changes to an existing package, you create a *\<recipe\>.bbappend*
  file. This is a file that contains instructions for any updates or
  patches for your layer.
 
  For example, assume an application called hellodemo (previously
  defined in **[Create a HelloDemo](#_bookmark104)
  [Package](#_bookmark104)**) needs an update. You want to change the
  string from hello world to Hello Demo. The new code would be as
  follows:
 
  The package developer creates a patch using the new source file and
  names it *hellodemo‑1.0.patch*. Assume you have an initial layer
  containing the recipe for the initial version of hellodemo:
 
  mylayer/recipes/hellodemo/hellodemo_1.0.bb

#### Procedure

1.  Create a new layer directory (for example, *hotfix*) with a
    > *recipes/hellodemo* subdirectory.

  mkdir -p hotfix/recipes/hellodemo/hellodemo
 
  This configures *hotfix* as a layer that you can add to your build.

2.  Copy the patch over to the new layer.

  cp hellodemo-1.0.patch hotfix/recipes/hellodemo/hellodemo

3.  Create the *hotfix/recipes/hellodemo/hellodemo_1.0.bbappend* file.

4.  Enable your user layer. See [**Enable a Layer**](#_bookmark97).

5.  Rebuild:

    - To rebuild only the package:

    - To rebuild everything:

#### Results

  This puts the updated *hellodemo* application in */usr/bin* in your
  root file system.

#### Related Topics

###### [Adding and Modifying Packages and Recipes](#adding-and-modifying-packages-and-recipes)

## Use a Custom BusyBox Configuration

  It is relatively simple to build with a custom user-supplied busybox
  configuration. The method outlined in this section will result in a
  non-volatile change to your busybox configuration. Simply editing
  *defconfig*
 
  or *.config* in your work directory will result in your busybox
  configuration being overwritten the next time something changes, and
  it will rebuild busybox.

#### Prerequisites

- A *local.conf* file exists for your project. See [**Set Up the Build
  Environment**](#set-up-the-build-environment).

#### Procedure

1.  After setting up your BitBake environment, run the following:

  bitbake -c menuconfig busybox

2.  Make your changes to the busybox menuconfig.

  Before exiting menuconfig, scroll down to the last option and select
  **Save Configuration to Alternate File** and give it an absolute path
  of */tmp/.my-defconfig*. If you do not do this, your *config* file
  will be overwritten the next time you build busybox.

3.  Create a layer directory and copy *my-defconfig* to *my-layers*:

4.  Update the layer configuration file and add the layer directory to
    > BBLAYERS.

5.  Remove the local copy of the cached binary to ensure that BitBake
    > rebuilds it from the source:

  bitbake -c cleansstate busybox

6.  Rebuild using the bitbake command:

  bitbake busybox

#### Results

  This creates package files for busybox that will be installed in the
  image, as long as the image requires busybox.
 
  The logs for building busybox are in the following directory:

#### Related Topics

###### [Adding and Modifying Packages and Recipes](#adding-and-modifying-packages-and-recipes)

## Rebuild a Package for a Project That Uses a Cached Binary Mirror

  If your project is set up to use a cached binary mirror and you want
  to rebuild a recipe for a project that has a valid cached binary file,
  you must remove the local copy of the cached binary before rebuilding.

#### Prerequisites

- A project that is configured to use a cached binary mirror. See
  > [**Shared State Caches**](#shared-state-caches).

#### Procedure

1.  Remove the local copy of the cached binary to ensure that it will be
    > built from the source when you rebuild:

2.  Rebuild the package using bitbake:

  bitbake \<recipe for package\>

#### Results

  This rebuilds the package files that will be installed in the image,
  as long as the image requires the package.

#### Related Topics

###### [Modify an Existing Package (Adding a Patch)](#_bookmark106) [Adding and Modifying Packages and Recipes](#adding-and-modifying-packages-and-recipes)

# Application Development

  Innexis Linux provides a customization and integration platform to
  satisfy the unique requirements of embedded projects. It supports the
  use of the Yocto Project Software Development Kit (SDK) to create,
  build, debug, and trace applications for Innexis Linux. You can use
  the Yocto Project SDK with the Innexis CodeBench IDE. The platform
  developer generates the Yocto Project SDK and then provides it to the
  application developer for installation.

###### [Software Development Kit 5-1](#software-development-kit)

###### [Managing Embedded Linux SDKs 5-2](#managing-embedded-linux-sdks)

###### [Innexis CodeBench IDE 5-7](#innexis-codebench-ide)

## Software Development Kit

  The standard Yocto Project SDKs include the cross-development
  toolchain, libraries, headers, symbols, and an environment setup
  script. They contain all the necessary metadata that the Innexis
  CodeBench IDE requires.
 
  SDKs are packaged as self-extracting Bourne shell scripts (*.sh*) to
  enable the installation of the SDKs. You can install them natively on
  Linux hosts.

###### [Build a Yocto Project SDK 5-1](#build-a-yocto-project-sdk)

  [**SDK Build Customization** **5-2**](#sdk-build-customization)

### Build a Yocto Project SDK

  Build a Yocto Project SDK for a target image by running the
  do_populate_sdk task against the image. By default, the resulting SDK
  includes a toolchain but does not include host tools.
 
  **Prerequisites**

- The build environment is set up for the target machine.

#### Procedure

1.  (Optional) Edit your build’s *local.conf* file.

  If you want to include host tools like autoconf, then before building
  the image, comment out or delete the following lines:

2.  Build the SDK.

  For example, to build the SDK for development-image, run one of the
  following commands:

#### Results

  The Yocto Project SDK installer script (*.sh*) is created in
  *tmp/deploy/sdk* relative to the build directory. You can use this to
  install the SDK.
 
  To install the Yocto Project SDK, see [**Install the SDK Using the
  Innexis CodeBench
  IDE**](#install-the-sdk-using-the-innexis-codebench-ide).

#### Related Topics

###### [Set Up the Build Environment](#set-up-the-build-environment)

### SDK Build Customization

  You can build additional packages and install them on the host (or
  native) or target areas of the constructed Yocto Project SDK using
  examples in the *conf/local.conf* file in the project build directory.
 
  To add host or native packages, such as build tools, see the example
  in the *local.conf* file:
 
  For target packages, development headers, and so on, you can either
  add them directly into development- image, as the image is the
  baseline for the SDK target sysroot, or you can add them explicitly.
  See the example in the *local.conf* file:

## Managing Embedded Linux SDKs

  You can install an SDK using the Innexis CodeBench IDE or the
  command-line interface.
 
  After installing the SDK, do not modify the name or location of the
  SDK’s directory. The application project build may show errors if you
  use a manually-relocated SDK. Instead, reinstall the SDK at the
  required location.

###### [Install the SDK Using the Innexis CodeBench IDE 5-3](#install-the-sdk-using-the-innexis-codebench-ide)

###### [Install the SDK From the Command Line 5-4](#install-the-sdk-from-the-command-line)

###### [Uninstall the Yocto Project SDK Using Innexis CodeBench 5-5](#uninstall-the-yocto-project-sdk-using-innexis-codebench)

###### [Add an Existing SDK to the Innexis CodeBench IDE 5-6](#add-an-existing-sdk-to-the-innexis-codebench-ide)

### Install the SDK Using the Innexis CodeBench IDE

  You can install, update, and uninstall a Yocto Project SDK from within
  the Innexis CodeBench IDE.
 
  You do not have to exit the IDE environment and switch to an external
  command-line tool to install an SDK before using it in the IDE.
  Installing an SDK through Innexis CodeBench makes it available when
  creating a new application project.

#### Prerequisites

- The Innexis CodeBench IDE is installed.

- A Yocto Project SDK installer is available on the host
  (*sdk-x86_64-innexis-linux-\<version\>.\<timestamp\>-
  development-image-\<machine-name\>.sh*).

- Your host meets the following requirements:

  - 6 GB of disk space is available on the host for an SDK built with
    > default features. An SDK built with additional features requires
    > more disk space for its installation.

  - The Yocto Project SDK installer has execution permissions.

  - Python 2 or Python 3 is installed on the host.

  - XZ Utils is installed on the host.

  - The Linux kernel version is v3.2.0 or later.

#### Procedure

1.  Launch the Innexis CodeBench IDE, and from the main menu, choose
    > **Help** \> **Install Innexis Linux SDK**.

2.  Click **Browse** to select the SDK installer location, or manually
    > type the location of the SDK installer. The file browser filters
    > for the *\*.sh* files.

3.  (Optional) Uncheck “Use default destination” to specify a
    > non-default path to install the SDK. You can specify a new
    > location or an existing location to install the SDK.

  The default location is
  *~/innexis-linux/sdk/\<version\>.\<timestamp\>/development-image-\<machine-
  name\>*.

4.  Click **Install** to start the installation.

5.  Click **OK** in the Success dialog box.

#### Results

  The SDK is installed in the specified directory, and the installation
  path is automatically added to the list of SDK search paths in the
  Innexis CodeBench IDE preferences. You can now use the SDK to develop
  application projects.

### Install the SDK From the Command Line

  Install the Yocto Project SDK on a Linux host operating system using
  the SDK installer script (*.sh*).

#### Prerequisites

- A Yocto Project SDK installer is available on the host
  (*sdk-x86_64-innexis-linux-\<version\>.\<timestamp\>-
  development-image-\<machine-name\>.sh*).

- Your Linux host operating system meets the requirements as specified
  in the Prerequisites section of

###### [Install the SDK Using the Innexis CodeBench IDE](#install-the-sdk-using-the-innexis-codebench-ide).

  **Procedure**

1.  Run the Yocto Project SDK installer (*.sh*) without any parameters.

  ./sdk-x86_64-innexis-linux-\<version\>.\<timestamp\>-development-image-
 
  \<machine-name\>.sh

2.  When prompted, specify the location of the directory in which to
    > install the SDK, or press Enter to install the SDK in the default
    > directory.

3.  Accept the confirmation message to continue with the installation.

  If the directory already exists, the installer displays a warning that
  existing files will be overwritten before proceeding.

#### Results

  The installer extracts the SDK in the directory you specified.
 
  You can now add the SDK to the Innexis CodeBench IDE for application
  project development. See **[Add
  an](#add-an-existing-sdk-to-the-innexis-codebench-ide) [Existing SDK
  to the Innexis CodeBench
  IDE](#add-an-existing-sdk-to-the-innexis-codebench-ide)** for more
  details.

### Uninstall the Yocto Project SDK Using Innexis CodeBench

  Uninstall the Yocto Project SDK from within the Innexis CodeBench IDE.

#### Prerequisites

- The Yocto Project SDK is installed and available in the Innexis
  > CodeBench IDE. It should be listed in the SDK lookup directories.

#### Procedure

1.  Launch the Innexis CodeBench IDE, and from the main menu, choose
    > **Help** \> **Install Innexis Linux SDK**.

2.  Select one of the installed SDKs from the list, and click
    > **Uninstall**.

3.  Click **Yes** in the confirmation window to begin the uninstallation
    > process. The uninstallation completes.

4.  Close the Install Innexis Linux SDK dialog box.

#### Results

  The SDK is removed from the file system and from the SDK lookup
  directories.

### Add an Existing SDK to the Innexis CodeBench IDE

  The Innexis CodeBench IDE automatically detects an SDK installed in
  the default directory. However, if you installed an SDK using the
  command line at a non-default path, then you must add it in the
  **Preferences** menu of the Innexis CodeBench IDE.
 
  By adding the SDK, options and graphical user interface (GUI) controls
  needed to create new C/C++ application projects based on the installed
  SDK become available in the Innexis CodeBench IDE.
 
  The following rules determine the SDKs listed in the Innexis CodeBench
  IDE:

- The IDE displays the SDK in *~/innexis-linux/sdk*, which is the
  default search path for the host.

- The IDE automatically searches and displays any SDK installed up to
  two levels deep under all search paths.

- The IDE searches and displays valid *cb-mbs-options-\** and
  *environment-setup-\** files in valid SDK directories.

#### Prerequisites

- The Innexis CodeBench IDE is installed.

- An SDK compatible with the version of the Innexis CodeBench IDE is
  > installed on the host. The version information in the installer file
  > name must match the version of the Innexis CodeBench IDE.

#### Procedure

1.  Launch the Innexis CodeBench IDE.

2.  Navigate to the **Window** \> **Preferences** dropdown on the main
    > menu bar. The Preferences dialog box opens.

3.  Navigate to the **Innexis Linux** \> **Innexis Linux SDK** section
    > from the left-hand list in the Preferences dialog box.

4.  Click **Add** to browse to the SDK installation directory, and add
    > the SDK search path.

5.  Click **Apply and Close** in the Preferences dialog box.

#### Results

  The SDK is added to the Innexis CodeBench IDE, and you can use it in
  application development workflows.

## Innexis CodeBench IDE

  You can use the Yocto Project Software Development Kits (SDKs) to
  create, build, debug, and profile application projects in the Innexis
  CodeBench IDE.

###### [Create a Project Using an SDK 5-7](#create-a-project-using-an-sdk-2)

###### [Create a Makefile Project Using an SDK 5-8](#create-a-makefile-project-using-an-sdk)

###### [Build a Project 5-9](#build-a-project)

###### [Debug Applications in the Innexis CodeBench IDE 5-9](#debug-applications-in-the-innexis-codebench-ide)

###### [Profile Applications in the Innexis CodeBench IDE 5-10](#profile-applications-in-the-innexis-codebench-ide)

###### [(Windows) Profile Applications in the Innexis CodeBench IDE 5-12](#windows-profile-applications-in-the-innexis-codebench-ide)

### Create a Project Using an SDK

  Create an application project using a Yocto Project SDK in the Innexis
  CodeBench IDE.

#### Prerequisites

- An SDK is available in the Innexis CodeBench IDE. See **[Managing
  > Embedded Linux SDKs](#managing-embedded-linux-sdks)** for details.

- You have configured your platform to connect to the Innexis CodeBench
  > IDE.

###### [IDE Connection Configuration for Innexis Hybrid](#ide-connection-configuration-for-innexis-hybrid)

- [**IDE Connection Configuration for Innexis
  > ANA**](#ide-connection-configuration-for-innexis-ana)

  **Procedure**

1.  Launch the Innexis CodeBench IDE.

  The IDE opens with the **Welcome** tab displayed.

2.  Choose **File** \> **New** \> **C Project** or **File** \> **New**
    > \> **C++ Project** to create a new project.

3.  Type a name for the project.

4.  Under Project Type, expand the **Executable** category, select an
    > example project, and click **Next**.

5.  In the Innexis CodeBench Configuration window, select SDK, and click
    > **Next**. (Optional) In this step, you can also provide a target
    > connection as follows:

    1.  Click **New** adjacent to the “Target connection” dropdown list.

    2.  In the New Connection window, select SSH Only, then click
        > **Next**.

    3.  In the Host name, provide the target IP address as “localhost”,
        > then click **Finish** to close the window.

6.  In the Debug Settings window, check “Create debug launch
    > configuration”.

7.  Click **Add** adjacent to the “Launch target” dropdown list to add
    > the Linux GDB Server launch target.

    1.  In the New Launch Target window, select Linux GDB Server, and
        > click **Next**.

    2.  In the New Linux GDB Server Target window, provide the target IP
        > address as “localhost” in the Host address field.

    3.  In the Port field, provide the host port that you forwarded for
        > the GDB connection to the target (for example, 1234).

    4.  Check the “This target allows remote access (e.g. via SSH)”
        > check box to allow remote access.

    5.  Select your target connection from the Connection dropdown list
        > and click the **Connection settings** link below the
        > Connection field.

  In the **Subsystem** tab of “Properties for the Ssh Shells” dialog
  box, change the Port value to the host port that you forwarded to the
  target’s port 22 for the SSH connection (for example, 2222). Click
  **Apply and Close**.

6.  In the New Linux GDB Server Target window, click **Finish**.

<!-- -->

8.  Click **Finish** in the Debug Settings window.

#### Results

  The compiler settings and the sysroot are automatically set to match
  the selected SDK. You can now build this application project created
  using the SDK.

### Create a Makefile Project Using an SDK

  You can create a Makefile project for Innexis Linux using an SDK that
  you choose in the Innexis CodeBench IDE. To create this, you must use
  the “Makefile Project for Innexis Linux” project type in the Innexis
  CodeBench IDE. This project type becomes available in the IDE after
  you install an SDK.

#### Prerequisites

- An SDK is available in the Innexis CodeBench IDE. See **[Managing
  > Embedded Linux SDKs](#managing-embedded-linux-sdks)** for details.

#### Procedure

1.  Launch the Innexis CodeBench IDE.

  The IDE opens with the **Welcome** tab displayed.

2.  Choose **File** \> **New** \> **C Project** or **File** \> **New**
    > \> **C++ Project** to create a new project.

3.  Type a name for the project.

4.  Under Project Type, expand the “Embedded Linux Development”
    > category, select “Makefile Project for Innexis Linux”, and click
    > **Next**.

  The Innexis CodeBench Configuration dialog box opens.

5.  On the SDK Selection page, select the SDK you want to use, and then
    > click **Finish**.

#### Results

  The Innexis CodeBench IDE creates a project with a Makefile and a
  sample source file that contains compiler flags from the selected SDK.
 
  Before you build your project, you can update the source files. For
  more information on how to add files to your project, refer to
  “Creating and Using a Makefile Project” in the *Innexis CodeBench IDE
  User’s Manual*.

### Build a Project

  Build an application project based on an SDK using the Innexis
  CodeBench IDE.

#### Prerequisites

- You have created an application project as shown in **[Create a
  Project Using an SDK](#create-a-project-using-an-sdk-2)** or a
  Makefile project as shown in [**Create a Makefile Project Using an
  SDK**](#create-a-makefile-project-using-an-sdk).

#### Procedure

  Open the Innexis CodeBench IDE, right-click the project name in the
  Project Explorer view, and click **Build Project**.

#### Results

  The project starts building, and you can monitor the progress in the
  **Console** tab.

### Debug Applications in the Innexis CodeBench IDE

  Use the Innexis CodeBench IDE to debug applications after building
  them.

#### Prerequisites

- You have built the application as shown in [**Build a
  Project**](#build-a-project).

#### Procedure

1.  In the Project Explorer view, right-click the project name and
    > choose **Debug As** \> **Innexis CodeBench Application**.

2.  In the Edit Configuration window, click **Debug**.

3.  In the Enter Password window, type your user ID and password for the
    > target, and then click **OK**.

4.  If prompted to confirm the perspective switch, click **Switch**.

#### Results

  The Innexis CodeBench IDE starts a debugging session with the
  application running on the target with the previously-specified
  settings. Debug the application by applying breakpoints and step
  operations as needed. You can monitor the output in the **Console**
  tab.

### Profile Applications in the Innexis CodeBench IDE

  Perform tracing and analysis in the Innexis CodeBench IDE using the
  Innexis CodeBench Analyzer tool.
 
  This procedure shows the basic workflow in the IDE by running a sample
  application set up as a managed C/C++ project to generate an analysis
  session.
 
  For more information about performance analysis in the Innexis
  CodeBench IDE, see “Getting Started With Remote Tracing” in the
  *Innexis CodeBench Analyzer Launcher Manual*. Further details on
  creating Innexis CodeBench Analyzer launch configurations are in the
  following subsections:

- “Creating a Profiling Configuration for Tracing an Application”

- “Creating a Profiling Configuration to Attach to a Process”

- “Creating a Profiling Configuration for a Disconnected Application”

- “Creating a Profiling Configuration to Attach to a Process on a
  Disconnected System”

  **Prerequisites**

- A Yocto Project SDK is installed.

- A target device is set up for tracing. For more information on target
  > setup, see the *Innexis CodeBench Analyzer LTTng Manual*.

- The Innexis CodeBench IDE is open.

#### Procedure

1.  Create the managed application as follows:

    1.  Choose **File** \> **New** \> **C++ Project**.

    2.  Choose a project type, for example, **Executable** \> **Analyzer
        > Parallel-Speed C++ Project**, and name the project.

    3.  In the Innexis CodeBench Configuration window, select the SDK,
        > and then click **Next**.

    4.  In the Debug Settings window, uncheck the “Create debug launch
        > configuration” option, then click **Finish**.

2.  Right-click the project and choose **Build Project**.

3.  Create a profiling configuration for tracing the application as
    > follows:

    1.  In the Project Explorer, right-click the project, and choose
        > **Profile As** \> **Innexis CodeBench Analyzer**.

  The Profile Configurations dialog box opens with a new profile launch
  created for the project.

2.  Select or create a valid SSH connection as “localhost” to your
    > target using the **New** button adjacent to the Connection field.

3.  Click the **Connection settings** link below the Connection field.

  In the **Subsystem** tab of “Properties for the Ssh Shells” dialog
  box, change the Port value to the host port that has been forwarded to
  the target’s port 22 for the SSH connection (for example, 2222).

4.  Click **Apply and Close**.

<!-- -->

4.  Click **Profile**.

#### Results

- The Innexis CodeBench IDE switches to the Analyzer perspective.

- The Innexis CodeBench Analyzer tool generates a session with the Linux
  > Application Profiling session template.

- When profiling completes on the target, the Innexis CodeBench Analyzer
  tool imports the data into the session.

- The agents on the session sheet display the results.

  For more information about the Innexis CodeBench Analyzer tool, see
  the *Innexis CodeBench Analyzer User Guide*.

### (Windows) Profile Applications in the Innexis CodeBench IDE

  Perform tracing and analysis in the Innexis CodeBench IDE using the
  Innexis CodeBench Analyzer tool on a Windows host.
 
  For more information about performance analysis in the Innexis
  CodeBench IDE, see “Getting Started With Remote Tracing” in the
  *Innexis CodeBench Analyzer Launcher Manual*. Further details on
  creating Innexis CodeBench Analyzer launch configurations are in the
  following subsections:

- “Creating a Profiling Configuration for Tracing an Application”

- “Creating a Profiling Configuration to Attach to a Process”

- “Creating a Profiling Configuration for a Disconnected Application”

- “Creating a Profiling Configuration to Attach to a Process on a
  Disconnected System”

  **Prerequisites**

- A target device is set up for tracing. For more information on target
  > setup, see the *Innexis CodeBench Analyzer LTTng Manual*.

- A C/C++ binary file is available on the target device.

- The Innexis CodeBench IDE is open.

#### Procedure

1.  Open the Profile Configurations dialog box by choosing **Run** \>
    > **Profile Configurations**. Then select Innexis CodeBench
    > Analyzer.

2.  Click the **New launch configuration** button.

3.  In the **Main** tab, do the following:

    1.  Specify an SSH connection to the target where you run the
        > application.

        - Select or create a valid SSH connection with your target IP
          > using the **New** button adjacent to the Connection field.

        - Click the **Connection settings** link below the Connection
          > field.

        - In the **Subsystem** tab of “Properties for the Ssh Shells”
          > dialog box, change the Port value to the host port that has
          > been forwarded to the target’s port 22 for the SSH
          > connection (for example, 2222).

    2.  Uncheck "Use a project to specify target C/C++ Application".

    3.  Check the box for "Skip download to target path".

    4.  In the "Remote file path for C/C++ Application", provide the
        > absolute remote path of the application available on the
        > target device.

4.  Click **Apply and Close**.

5.  In the Innexis CodeBench Analyzer perspective, create an Innexis
    > CodeBench project by choosing **File**

  \> **New** \> Innexis CodeBench Analyzer **Project**.

6.  Right-click the project and then choose **New Session**. The Innexis
    > CodeBench Analyzer Session dialog box opens.

7.  Select a launch configuration, and then click **Next**.

8.  Select a default session template and click **Finish**.

9.  Right-click the session and click **Profile**.

#### Results

  When profiling completes on the target, the Innexis CodeBench Analyzer
  tool imports the data into the session.
 
  The agents on the session sheet display the results. For more
  information about the Innexis CodeBench Analyzer tool, see the
  *Innexis CodeBench Analyzer User Guide*.

# Kernel and Kernel Module Debugging

  You can use the Innexis CodeBench software to perform kernel and
  kernel module debugging. In the following sections, you will set up a
  target, perform kernel debugging, create and debug a kernel module, as
  well as debug a kernel module that is already placed and loaded on the
  target.

###### [Kernel Debugging 6-1](#kernel-debugging)

###### [Kernel Module Debugging 6-3](#kernel-module-debugging)

## Kernel Debugging

  Debug a running Linux kernel from the Innexis CodeBench IDE. Kernel
  debugging is unlike GNU/Linux application debugging, in that it
  requires the use of an External Embedded Server launch target rather
  than the user-space GDB server utility.

###### [Debug a Linux Kernel 6-1](#debug-a-linux-kernel)

### Debug a Linux Kernel

  You can debug a running Linux kernel from the Innexis CodeBench IDE.

#### Prerequisites

- You have built the target image (development-image) with the debugging
  > feature enabled.

  To build an image with debugging enabled, uncomment the following line
  in *\<innexis-linux-build-dir\>/ conf/local.conf*:
 
  \# USER_FEATURES += "flex-debugging"

- You have built the kernel from source. If the kernel was built using
  > cached binaries, ensure to rebuild it as follows from the Innexis
  > Linux build directory:

  bitbake development-image

- You have added the --wait_for_debugger option to the ‘launcher’
  > command in the *config/generated/ platform-common.conf* file
  > available in the Innexis Hybrid workspace.

- You are running the Innexis Linux development image on the Innexis
  Hybrid platform using the Questa simulator. You will see the following
  message on the QEMU UART console:

  Connected to Terminal on TCP Port 4444 of localhost

- You have forwarded a host port, (for example, 2222) to the target’s 22
  port, for an SSH connection.

- The Innexis CodeBench tool is running on the same host on which the
  kernel is built.

- You have enabled debugging in your compiler options.

  You can use your normal procedure to build the kernel, but setting up
  to debug the Linux kernel differs from debugging a kernel module,
  because there is no associated project for the debug launch
  configuration.

#### Procedure

1.  In Innexis CodeBench, choose **Run** \> **Debug Configurations**,
    > then create a new debug launch configuration as follows:

    1.  Select CodeBench Kernel Image (Attach) as the debug
        > configuration type, and click the **New launch configuration**
        > icon in the upper left corner of the dialog box.

    2.  In the **Main** tab, leave the Project field empty.

    3.  In the Kernel image field, type or browse to the path of the
        > *vmlinux* file in the kernel build directory.

  You can find the *vmlinux* file at the following location relative to
  the Innexis Linux project’s build directory:
 
  *tmp/deploy/images/innexis-arm64/*

4.  In the Kernel source field, type or browse to the path of the kernel
    > sources directory.

  You can find kernel sources at the following location relative to the
  Innexis Linux project’s build directory:
 
  */tmp/work-shared/innexis-arm64/kernel-source*

2.  To specify debugger settings, switch to the **Debugger** tab.

3.  <span id="bookmark128" class="anchor"></span>Select or create an
    > External Embedded Server launch target as follows:

    1.  Click **Add** in the **Debugger** tab of the Debug
        > Configurations page.

    2.  Select the External Embedded Server launch target, and click
        > **Next**.

    3.  (Optional) Edit the name of the launch target.

    4.  Enter the port 1234, and click **Finish**.

  The new launch target displays in the **Debugger** tab.

4.  Click **Apply** and then **Debug**.

  The debug session starts. The probe halts the kernel running on the
  target. When the target is in suspended state, you can create
  breakpoints and debug the kernel.

###### <img src="media/image19.jpeg"
style="width:5.43333in;height:3.62667in" />Figure 6-2: Debug Session

## Kernel Module Debugging

  Debug a Linux kernel module from the Innexis CodeBench IDE. Similar to
  kernel debugging, kernel module debugging also requires the use of an
  External Embedded Server launch target rather than the user-space GDB
  server utility.

###### [Build a Kernel Module Project 6-3](#build-a-kernel-module-project)

  [**Debug a Linux Kernel Module**
  **6-5**](#debug-a-linux-kernel-module)

### Build a Kernel Module Project

  You can use the Linux Kernel Module Project wizard to build a kernel
  module.

#### Prerequisites

- You have enabled the debugging feature in your target image.

  Uncomment the following line in
  *\<innexis-linux-build-dir\>/conf/local.conf* when building images for
  debugging:
 
  \# USER_FEATURES += "flex-debugging"

- You have built the kernel from source. If the kernel was built using
  > cached binaries, ensure that you rebuild as follows from the Innexis
  > Linux build folder:

  bitbake development-image

- You have built the SDK using the same build directory and installed
  > it. To build the SDK, run the following command:

  bitbake development-image -c populate_sdk
 
  To install the SDK, see [**Install the SDK Using the Innexis CodeBench
  IDE**](#install-the-sdk-using-the-innexis-codebench-ide).

- You have added the --wait_for_debugger option to the ‘launcher’
  > command in the *config/generated/ platform-common.conf* file
  > available in the Innexis Hybrid workspace.

- You are running the Innexis Linux development image on the Innexis
  > Hybrid platform using the Questa simulator. You will see the
  > following message on the QEMU UART console:

  Connected to Terminal on TCP Port 4444 of localhost

- You have resumed the kernel. To do this, type ‘c’ in the QEMU monitor
  > console. You can see the Linux kernel prompt in the QEMU UART
  > console after the kernel boots.

- You have forwarded a host port, (for example, 2222) to the target’s 22
  > port, for an SSH connection.

- The Innexis CodeBench IDE is running on the same host on which the
  kernel is built.

#### Procedure

1.  Open the C Project wizard to create a new C project.

2.  Name the project, expand Kernel Development, select Linux Kernel
    > Module Project, and then click

###### Next.

3.  Select the Innexis Linux SDK that you built, as specified in the
    > Prerequisites section, with the “flex- debugging” feature, and
    > click **Next**.

4.  In the Debug Settings page that opens, do the following:

    1.  Add the launch target for your debug interface. Refer to Step
        > **[3](#bookmark128)** of [**Debug a Linux
        > Kernel**](#debug-a-linux-kernel).

    2.  Click **Finish**.

5.  Right-click the created project, and click **Build Project** to
    > build the kernel module project with a sample module
    > implementation.

#### Results

  The Innexis CodeBench editor may display some errors and warnings but
  the kernel module builds successfully.
 
  The sample module code is a functional character driver module. It
  contains a generated makefile that is configured to use the kernel
  source tree you specified while creating the project. The sample sets
  the
 
  appropriate build variables in the project and creates a kernel debug
  configuration to connect to the target. Although the errors and
  warnings do not impact the IDE functionality, you can suppress them as
  follows:

- In the Innexis CodeBench editor, right-click a question mark, and
  select “Preferences...”

- Uncheck “Report problems as you type”.

- Navigate to Code Analysis.

- Uncheck all items, and click **Apply and Close**.

### Debug a Linux Kernel Module

  You can debug a Linux kernel module from the Innexis CodeBench IDE.

#### Prerequisites

- You have set up the target.

- You have built a kernel module project. See the Prerequisites of
  **[Build a Kernel Module Project](#build-a-kernel-module-project)**
  for details.

#### Procedure

1.  Choose **Run** \> **Debug Configurations**, and open the
    > newly-created debug configuration under CodeBench Kernel Module,
    > and do the following:

    1.  Create an SSH connection “localhost” using the Connection field.

    2.  Click the “Connection settings” link below the Connection field.

    3.  In the **Subsystem** tab of “Properties for Ssh Shells” dialog
        > box, change the Port value to the host port that you forwarded
        > to the target’s port 22 for the SSH connection.

    4.  Click **Apply and Close**.

    5.  Ensure the following:

        - All the check boxes under Startup options are checked.

        - The Kernel module field specifes the correct kernel module
          > name.

        - The Kernel image field specifies the correct path of the
          > *vmlinux* file from the installed SDK.

        - The Kernel source field specifies the correct path of kernel
          > sources from the installed SDK.

    6.  Click the **Debugger** tab. Ensure that the appropriate
        > toolchain and launch target are selected, as explained in Step
        > **[3](#bookmark128)** of [**Debug a Linux
        > Kernel**](#debug-a-linux-kernel).

    7.  Click **Apply** to activate the **Debug** button.

    8.  Click **Debug** to launch the debug session on the target.

  A popup dialog box displays and prompts you to enter your user ID and
  password for the target. Type your credentials and click **OK**. If
  you are launching the debug connection for the first time, it prompts
  you to add the target into the list of trusted hosts.

9.  Ensure that the breakpoint in the initialization function is hit.

<!-- -->

2.  Resume the kernel and run the following commands on the target
    > serial console:

3.  In the kernel module code, add breakpoints in the following
    > functions:

- chardrv_open

- chardrv_read

- chardrv_write

- chardrv_release

4.  Read the device using the **cat /dev/chardrv0** command, and ensure
    > that breakpoints in the following functions are hit:

- chardrv_open

- chardrv_read

- chardrv_release

  Verify that the following message prints on the serial console:
 
  \[ 1342.877645\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 4096
 
  \[ 1342.890182\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 8192
 
  \[ 1342.901452\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 12288
 
  \[ 1342.912878\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 16384
 
  \[ 1342.924373\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 20480
 
  \[ 1342.935100\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 24576
 
  \[ 1342.945004\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 28672
 
  \[ 1342.954865\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 32768
 
  \[ 1342.964724\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 36864
 
  \[ 1342.974582\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 40960
 
  \[ 1342.984474\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 45056
 
  \[ 1342.994307\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 49152
 
  \[ 1343.004110\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 53248
 
  \[ 1343.014040\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 57344
 
  \[ 1343.023910\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 61440
 
  \[ 1343.033799\] Read function for chardrv has been called.Number of
  bytes read = 4096, position = 65536
 
  \[ 1343.043676\] chardrv: Attempted read exceeded buffer length \[
  1343.049362\] chardrv device has been closed

5.  Run the command **echo 4 \> /dev/chardrv0**, and ensure that
    > breakpoints in the following functions are hit:

- chardrv_open

- chardrv_write

- chardrv_release

6.  Verify that the following message prints on the serial console:

#### Results

  You have successfully debugged a kernel module.

# Machine Learning

  The Machine Learning (ML) feature is designed to help developers
  create, deploy, and manage machine learning applications on Innexis
  Linux. It provides pre-integrated libraries for TensorFlow Lite,
  enhanced with a range of additional features and tools to assist in
  creating and managing ML applications. This feature is part of Innexis
  CodeBench in the form of an Innexis Linux ML layer and an Innexis
  CodeBench IDE plugin.

###### [Features and Benefits 7-1](#features-and-benefits)

###### [Acceleration and Instrumentation 7-3](#acceleration-and-instrumentation)

###### [Getting Started With ML 7-3](#getting-started-with-ml)

###### [Using ML in an Application 7-5](#using-ml-in-an-application)

###### [Task Library API Reference 7-8](#task-library-api-reference)

###### [Working With TensorFlow Lite Models 7-16](#working-with-tensorflow-lite-models)

###### [Hardware Acceleration 7-34](#hardware-acceleration)

###### [Performance Analysis and Optimization 7-37](#performance-analysis-and-optimization)

###### [Example Applications 7-39](#example-applications)

## Features and Benefits

  ML simplifies the process of developing and deploying machine learning
  based on TensorFlow Lite by extending and integrating the Task Library
  with new features that leverage the Innexis Linux platform and tools.
 
  The following diagram shows the components of ML. The core of the
  system is the OSS components, shown in gray:

###### <img src="media/image20.jpeg"
style="width:7.16344in;height:3.92344in" />Figure 7-3: Machine Learning Components

  **TensorFlow Lite**
 
  **TensorFlow Lite Task Library**
 
  TensorFlow Lite[1](#_bookmark136) is a lightweight model interpreter
  belonging to the open source TensorFlow suite of machine learning
  technologies. It efficiently enables a machine learning model to
  perform inference operations on some given input data, producing
  results as its outputs.
 
  TensorFlow Lite consumes and produces arrays of numbers in operation.
  Most applications require preprocessing of data before it can be
  passed as input to an interpreter, and post-processing of the output
  results into a usable format. To simplify implementation, these data
  processing steps can be taken care of by the TensorFlow Lite Task
  Library, which is another member of the TensorFlow family of
  technologies. It can be found in the “tflite-support” package. This
  library is a wrapper for TensorFlow Lite and configures some typical
  pre- and post-processing pipelines around the interpreter, based on
  specifications contained in metadata attached to the model. The
  metadata describes the exact inputs and outputs for the model and
  allows the Task Library to configure pipelines to convert output and
  input data to and from standard formats respectively.
 
  This simplifies the use of TensorFlow Lite and saves development
  effort.
 
  The ML layer further simplifies the process of developing and
  deploying machine learning based on TensorFlow Lite by extending and
  integrating the Task Library with new features that leverage the
  Innexis Linux platform and tools.
 
  These two TensorFlow libraries have been pre-built and validated on
  the Innexis virtual or hybrid platforms, and they are fully usable to
  application developers from the Innexis CodeBench development
  environment.
 
  <span id="_bookmark136" class="anchor"></span>1 TensorFlow, the
  TensorFlow logo and any related marks are trademarks of Google Inc.
 
  There is no requirement to use the same build systems as the open
  source TensorFlow packages. Numerous examples are included to show you
  how to build, launch, and debug in the Innexis CodeBench environment.
  Templates are provided from which developers can start their own
  projects.
 
  ML is compatible with a range of off-the-shelf models from
  repositories such as TensorFlow Hub, provided they carry appropriate
  metadata. It is also compatible with tools such as TensorFlow Lite
  Model Maker that can generate and embed appropriate metadata. For
  models produced by other means, the ML
 
  layer includes an XML editor within Innexis CodeBench along with a
  schema supporting easy creation and editing of metadata, templates to
  get started easily, and documentation describing the metadata
  requirements and format.

## Acceleration and Instrumentation

  The libraries have been optimally configured for supported platforms,
  including allowing for simplified use of hardware acceleration where
  available. This feature is called using a simple API and avoids the
  complexities of enabling hardware acceleration directly through the
  open-source libraries.
 
  Furthermore, the libraries have been instrumented to return
  performance information that can be visualized and analyzed by
  developers using the Innexis CodeBench Analyzer tool included with
  Innexis CodeBench. Detailed information about the performance
  breakdown of inference, preprocessing and post-processing operations
  can be displayed on a time axis and correlated with other system
  performance metrics such as CPU and core utilization, processes and
  threads, and RAM usage. This delivers system
 
  insights that can help you optimize the performance of ML applications
  and diagnose performance issues.

## Getting Started With ML

  This section covers enabling the ML feature for Innexis Linux and
  running an example ML application using the Innexis CodeBench IDE.
  Building and running ML requires both Innexis Linux and the
  corresponding BSP components to be correctly installed and configured.

###### [Build Innexis Linux With ML 7-3](#build-innexis-linux-with-ml)

  [**Set Up the SDK for Innexis CodeBench**
  **7-4**](#set-up-the-sdk-for-innexis-codebench)

### Build Innexis Linux With ML

  Build an Innexis Linux image with support for ML using the Innexis
  CodeBench IDE.
 
  **Prerequisites**

- You have installed Innexis Linux using the Innexis CodeBench
  > installer.

- You have set up an Innexis Linux workspace. See **[Prepare the
  > Workspace for a Build](#prepare-the-workspace-for-a-build)** for
  > details.

#### Procedure

1.  Run the *setup-environment* script with the -l 'machine-learning'
    > option to include the ML layer in the build layers.

  source meta-flex/setup-environment -b \<build_dir\> -l
  'machine-learning'
 
  \<machine-name\>
 
  See **[Set Up the Build Environment](#set-up-the-build-environment)**
  for more details.

2.  Edit the *conf/local.conf* file in the newly created build
    > directory.

  By default, this file should contain the following USER_FEATURES line
  that enables ML:
 
  USER_FEATURES += "machine-learning"
 
  If you need to deactivate ML in the build, comment this line out. If
  optional hardware acceleration is required, enable the appropriate
  options in this file. See **[Hardware
  Acceleration](#hardware-acceleration)** for details.

3.  Build the OS image.

  bitbake development-image

#### Results

- This generates the OS images to be used with your target under
  *\<build_dir\>/tmp/deploy/images/\<bsp- name\>*

- To boot this image on your target platform, refer to the relevant
  sections in [**Virtual Platform BSPs**](#virtual-platform-bsps).

### Set Up the SDK for Innexis CodeBench

  The Yocto SDK contains the dev and debug packages of the system's root
  file system components. This allows you to compile, link, and debug
  your ML applications before deploying them on the target platform.

#### Prerequisites

- You have built the Innexis Linux image with the ML feature.

- You have installed the Innexis CodeBench IDE using the Innexis
  > CodeBench installer.

#### Procedure

1.  Build the Yocto SDK for the Innexis Linux image you previously
    > built.

  bitbake -c populate_sdk development-image
 
  This SDK will be used with the Innexis CodeBench IDE. The SDK
  installation script will be generated as follows:
 
  *sdk-x86_64-innexis-linux-\<version\>.\<timestamp\>-development-image-\<machine-name\>.sh*
 
  See **[Software Development Kit](#software-development-kit)** for more
  information.

2.  Install the generated SDK.

  See **[Install the SDK Using the Innexis CodeBench
  IDE](#install-the-sdk-using-the-innexis-codebench-ide)** for details.

#### Results

  The installed SDK enables you to create new projects and build the ML
  applications using the SDK from within the Innexis CodeBench IDE.

## Using ML in an Application

  This section explains the basics of using ML to integrate machine
  learning into an application, then to deploy and run it.
 
  For a full walkthrough of building and deploying one of the sample
  applications, see the Appendix:

###### [Sample Application Walkthrough](#sample-application-walkthrough).

  Adding ML support to an application requires the following:

- The application build settings to be updated to correctly process the
  > header files and find the libraries required for the ML
  > functionality.

- One or more TensorFlow Lite models, which will be used to perform the
  > ML inference.

- Additional code to invoke the ML inference, and to interpret the
  > results.

###### [Application Build Settings 7-5](#application-build-settings)

###### [Writing Code to Perform Inferences 7-6](#writing-code-to-perform-inferences)

###### [Run Applications From the Innexis CodeBench IDE 7-7](#run-applications-from-the-innexis-codebench-ide)

### Application Build Settings

  If you have started writing your application based on a provided ML
  project template, then the build settings will already be set up
  correctly. The ML project templates are available by selecting
  **File** \> **New C++**
 
  \> **Project** in the Innexis CodeBench IDE and choosing one of the ML
  templates.
 
  If you are adding ML functionality to an existing application, add the
  following options to your project:
 
  In the **Project** \> **C/C++ Build** \> **Settings** dialog box, add
  the following libraries from **Tool** \> **Settings** \>
 
  ***\<Linux C++ Linker group\>*** \> **Libraries**:

- tflite-support

- tensorflow-lite

- dl

- rt

- lttng-ust

### Writing Code to Perform Inferences

  Inference uses machine learning models on a dataset to generate a
  prediction. You can perform inferences with or without using the task
  library.

#### ML Models

  A TensorFlow model exported in the “tflite” format will be needed to
  perform ML inference.
 
  The TensorFlow Lite Task Library supports several categories of model,
  including image classification and object detection. If the model you
  wish to use does not fit into one of these categories, you can extend
  the library with custom tasks using the base Task Library framework.
  These custom tasks will then benefit from the features of ML, such as
  instrumentation. Alternatively, you can use the core TensorFlow Lite
  library to perform inference, and manually pre-process and
  post-process the data sent to and returned from inference. For more
  information about finding and deploying a model, refer to the section
  **[Working](#working-with-tensorflow-lite-models) [With TensorFlow
  Lite Models](#working-with-tensorflow-lite-models)**.

#### Inference Using the Task Library

  Select a Task Library class appropriate for the model and your
  application use case. See
  **[https://](https://www.tensorflow.org/lite/inference_with_metadata/task_library/overview#supported_tasks)
  [www.tensorflow.org/lite/inference_with_metadata/task_library/overview#supported_tasks](https://www.tensorflow.org/lite/inference_with_metadata/task_library/overview#supported_tasks)**
  for a list of currently supported categories.
 
  Creating an instance of the class typically involves building an
  options structure specific to the inference class, and then calling a
  factory method BuildFromOptions() on the inference class.
 
  For example, if you have an image classification model, you would
  create an instance of the tflite::task::vision::ImageClassifier class
  by first creating and configuring an ImageClassifierOptions class, and
  calling ImageClassifier::BuildFromOptions(), which would return a new
  instance of the inference class. To perform inference and receive the
  results, see the documentation for the inference class you have
  chosen. For the ImageClassifier example above, there is an API
  Classify() which takes an image to classify,
 
  and returns a ClassificationResult instance. The details will vary
  depending on the category of inference used; see
  **<https://www.tensorflow.org/lite/inference_with_metadata/task_library/overview>**
  for details.

#### Inference Without Using the Task Library

  A TensorFlow model can be loaded directly into the application and the
  TensorFlow Lite interpreter, along with any delegates, can be created
  manually. See the TensorFlow documentation beginning with
  **[https://](https://www.tensorflow.org/lite/guide/inference)
  [www.tensorflow.org/lite/guide/inference](https://www.tensorflow.org/lite/guide/inference)**
  for further details.
 
  In this case, the application will only need to be linked against the
  tensorflow-lite library, but none of the features of ML, such as
  instrumentation support and XNNPACK, will be available to the
  application.

### Run Applications From the Innexis CodeBench IDE

  After you have successfully built your application, it must be
  deployed to the target before it can be run.

#### Prerequisites

- Your application has been adapted to use the ML feature, as explained
  > in [**Application Build Settings**](#application-build-settings),
  > and builds successfully.

- The model is already deployed to the target and registered in the
  > Model Cache. This step is already done for the sample applications.
  > See the section **[Working With TensorFlow Lite
  > Models](#working-with-tensorflow-lite-models)** for details on how
  > to deploy custom models.

- Any other artifacts required by the application at runtime are
  > deployed to the target file system.

- The Innexis CodeBench IDE is up and running.

#### Procedure

1.  Choose **Run As** \> **Run Configurations** in the Project Explorer.

2.  In the “Create, manage and run configurations” dialog, select the
    > **Debugger** tab and then the

  **Startup** sub-tab.
 
  Set the “Remote path” field to the location where the application
  should be copied.
 
  This sets the location of the executable on the target board. Ensure
  that you choose a location that has executable rights.

3.  Make any other configuration changes appropriate for your
    > application.

  For example, you can add in any command-line parameters and target
  connection configurations

4.  Click **Apply**, then **Run** to launch the application.

#### Results

  The custom application is downloaded to the target and gets executed.

## Task Library API Reference

  This section provides reference information for Task Library API
  functions that have either been modified or added by ML. For the
  remainder of the Task Library API, see the TensorFlow documentation.

###### [Task Library Classes 7-9](#task-library-classes)

###### [SemlAccelerationConfig 7-11](#semlaccelerationconfig)

###### [BaseTaskApi 7-15](#basetaskapi)

### Task Library Classes

  In each Task Library class, the CreateFromOptions() factory method has
  the following additional parameters.

###### model key

  A string which is the filename of the model, without the *.tflite*
  extension, to use for inference. If not available in the default model
  cache */flex-ml/demo_models*, update the model cache location as
  described in [**Modify the Model Cache**](#modify-the-model-cache).
 
  **config** A pointer to a SemlAccelerationConfig class, to configure
  the various ways inference can be accelerated. This configuration will
  be used in preference to any similar choices made in the options
  parameter. Pass in nullptr if not needed.
 
  **Modified Task Library Classes**
 
  The following is a list of modified Task Library classes:

###### ImageClassifier

###### ImageEmbedder

###### ImageSegmenter

###### ObjectDetector

###### AudioClassifier

###### BertQuestionAnswerer

SemlAccelerationConfig

### SemlAccelerationConfig

  To configure the inference acceleration choices you want to use, you
  must do the following:

- Instantiate the class
  > tflite::task::core::seml::SemlAccelerationConfig.

- Configure the options as shown in the following sections.

- Pass a pointer to the SemlAccelerationConfig object in the call to
  > CreateFromOptions() as documented in

###### [Task Library Classes](#task-library-classes).

###### [SetComputeMode 7-12](#_bookmark148)

###### [SetCpuThreads 7-13](#setcputhreads)

###### [SetExternalDelegateLibPath 7-14](#setexternaldelegatelibpath)

###### [SetExternalDelegateOptions 7-15](#setexternaldelegateoptions)

  <span id="_bookmark148" class="anchor"></span>**SetComputeMode**
 
  Configures whether the task should attempt to accelerate an ML
  inference, using instruction set extensions in the CPU architecture.
  It might be the case that only certain operations within a model can
  be accelerated; if acceleration cannot be applied to some operations,
  the CPU reference mode is used as
 
  a fallback for those operations.
 
  **Usage**
 
  void SetComputeMode(ComputeMode mode);

#### Parameters

###### mode

  Specifies the preferred acceleration mode for this model.

- ***ComputeMode::kCPUReference*** — Uses portable CPU-based code, for
  > maximum compatibility with models.

- **ComputeMode::kCPUOptimized** — Use CPU instruction set extensions,
  > such as Arm NEON or AVX/SSE on x86, if available. Might not be
  > compatible with all models, and might not be supported on some
  > platforms, for example 32-bit Arm. If unavailable, the application
  > will fall back to kCPUReference.

  ComputeMode::kCPUOptimized is the default behavior.

- ***ComputeMode::kGPU*** — Uses the GPU if available. Might not be
  > compatible with all models.

- ***ComputeMode::kExternal*** — Use an external delegate. The library
  > to use must be set with SetExternalDelegateLibPath().

#### Return Values

  None

##### SetCpuThreads

  Provides the option to set a preference for the number of threads to
  use for the CPU compute modes. The default behavior is one thread per
  processor available on the target.

#### Usage

  absl::Status SetCpuThreads(int threads);

#### Parameters

###### threads

  The number of threads to use. Call with 0 for the default behavior.

#### Return Values

  A status object with a standard error, or “Ok” if successful.

##### SetExternalDelegateLibPath

  Sets the external delegate library to apply to the model. This
  automatically sets the compute mode to kExternal.

#### Usage

  void SetExternalDelegateLibPath(const std::string
  &external_delegate_lib_path);

#### Parameters

###### external_delegate_lib_path

  The full library path including file name.

#### Return Values

  None

##### SetExternalDelegateOptions

  Sets the options to supply to the external delegate library when it is
  initialized.

#### Usage

  void SetExternalDelegateOptions(const std::map\<std::string,
  std::string\> &external_delegate_options);

#### Parameters

- ***external_delegate_options***

  The map of options to use. The keys should be option names, and the
  values should be the corresponding option values.

#### Return Values

  None

### BaseTaskApi

  The following APIs have been added to the TensorFlow Lite Task Library
  in the “tflite::task::core::BaseTaskApi” class.

###### [SetBenchmarkMode 7-16](#_bookmark153)

  <span id="_bookmark153" class="anchor"></span>**SetBenchmarkMode**
 
  Configures a benchmarking mode, where the inference is to be repeated
  several times, and the timing statistics printed to stdout. Pre- and
  post-processing steps are not repeated. This API is intended for use
  during development in conjunction with the example applications.
 
  **Usage**
 
  void SetBenchmarkMode(int warmups, int iterations);

#### Arguments

###### warmups

  The number of times the inference should be repeated before the timing
  is started for the subsequent iterations.

###### iterations

  The number of times to repeat the inference while timing information
  is being collected.

#### Return Values

  None

## Working With TensorFlow Lite Models

  Machine learning models contain a description of how input data will
  be processed to produce an output analysis; for example, how an image
  will be processed to detect an object within it, and how the location
  of that object will be returned.
 
  In this product, TensorFlow Lite models are used for ML processing on
  the target platform. A TensorFlow Lite model can be created from
  TensorFlow models as shown in
  [**https://www.tensorflow.org/lite/convert**](https://www.tensorflow.org/lite/convert).
  For a general introduction to TensorFlow and ML models, see
  [**https://www.tensorflow.org/learn**](https://www.tensorflow.org/learn).
 
  You can find a wide range of TensorFlow Lite models that are available
  to use with various licenses from sites such as
  [**https://www.kaggle.com/models?framework=tfLite**](https://www.kaggle.com/models?framework=tfLite).

###### [Load a Model 7-17](#load-a-model)

  [**Modify the Model Cache** **7-17**](#modify-the-model-cache)
 
  [**Working With Metadata** **7-18**](#working-with-metadata)
 
  [**Model Metadata XML Reference**
  **7-20**](#model-metadata-xml-reference)

### Load a Model

  ML features use a location on the root file system of the target image
  as a model cache. A freshly
 
  created Innexis Linux image with the ML feature enabled defines the
  default model cache path as */flex-ml/ demo_models*, and it has been
  populated with all the models required by ML example applications.
 
  See the "List of Examples" in the **[Example
  Applications](#example-applications)** section for a list of these
  demos. The applications using the ML TensorFlow Lite Task Library will
  use the model cache to get the required models.
 
  **Procedure**
 
  To load a model from the model cache into an interpreter, pass its
  name without the *.tflite* suffix to the appropriate
  CreateFromOptions() functions.
 
  See **[Task Library API Reference](#task-library-api-reference)** for
  more information.

### Modify the Model Cache

  To update the model cache, put your *.tflite* model files in the model
  cache directory. The models must be at the model cache location on the
  target file system. You can modify the model cache path for
  applications being run on the command line and for those on the IDE.

#### Procedure

1.  If you are deploying an application directly on the target, change
    > the default path for the model cache by defining the environment
    > variable "FLEXML_MODEL_CACHE_PATH" to point to a new path on the
    > file system:

  export FLEXML_MODEL_CACHE_PATH="/custom_models/"
 
  The shell updates the model cache path to use the models from the new
  location.

2.  If you are deploying the application using the Innexis CodeBench
    > IDE, change the application environment by doing the following:

    1.  In the Innexis CodeBench IDE, choose **Run** \> **Debug
        > Configurations** to open the Debug Configurations dialog box.

    2.  Switch to the **Environment** tab.

    3.  In the Environment Variable dialog box, click **Add**. Then in
        > the New Environment Variable dialog box, type
        > "FLEXML_MODEL_CACHE_PATH" in the Name field and
        > */custom_models/* in the Value field.

    4.  Click **OK** and then **Apply** to launch the application.

  <img src="media/image21.jpeg"
  style="width:6.43125in;height:3.54375in" />
 
  The IDE updates the model cache path to use the models from the new
  location.

### Working With Metadata

  TensorFlow Lite files may optionally contain metadata describing how
  the underlying inference should be used. The metadata contains both
  human-readable documentation and details of the input and output of
  the model. This helps the TensorFlow Lite Task Library process the
  input sent by a user application to the model in the correct format,
  such as an image captured from a camera. It also helps to process the
  data output from the model into something easily usable by the
  application. For example, matching the image classification outputs
  with a list of labels and sorting in order of confidence.
 
  The metadata is typically created and applied to the *.tflite* file by
  a Data Scientist using the Python API. See

###### <https://www.tensorflow.org/lite/convert/metadata#adding_metadata>.

  In some cases, there may be times when a *.tflite* file does not
  contain any metadata, or the metadata needs to be corrected, or the
  metadata of one *.tflite* file needs to be used by a different,
  retrained version of that model. The tooling supplied with Innexis
  CodeBench allows the metadata embedded in a *.tflite* file to be
  extracted into separate files, which can then be edited. If a model
  does not have embedded metadata, new metadata files can be created.
  The modified metadata files can then be used with the original
  *.tflite* file on the target and will take precedence over the
  embedded metadata.

###### [Extract or Create Metadata From a Model 7-19](#_bookmark158)

###### [Editing Metadata in the Innexis CodeBench IDE 7-20](#editing-metadata-in-the-innexis-codebench-ide)

###### [Deploying Metadata on the Target 7-20](#_bookmark160)

  <span id="_bookmark158" class="anchor"></span>**Extract or Create
  Metadata From a Model**
 
  The Innexis CodeBench IDE provides commands to extract or create
  metadata from *.tflite* files to editable XML files, along with an XML
  editor.
 
  **Prerequisites**

- You have launched the Innexis CodeBench IDE.

#### Procedure

1.  In the Project Explorer, right-click a *.tflite* file that has
    > metadata.

  The menu options **Extract metadata** and **Create new metadata** will
  be available.

2.  Choose what you want to do to the metadata.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>If you want to...</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Do the following:</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><blockquote>
<p>Extract metadata</p>
</blockquote></td>
<td><blockquote>
<p>Choose <strong>Extract metadata</strong>.</p>
</blockquote></td>
</tr>
<tr class="even">
<td><blockquote>
<p>Create new metadata</p>
</blockquote></td>
<td><blockquote>
<p>Choose <strong>Create new metadata</strong>.</p>
</blockquote></td>
</tr>
</tbody>
</table>

3.  Select a folder for the output, and within this selected folder, a
    > new folder named "*\<model_name\>.meta*" will be created.

  If you extracted metadata, the new folder contains the following
  files:

- **\_metadata.xml** — An XML representation of the metadata. You can
  > edit this with the installed XML editor, or external tools.

- **\_metadata_schema.xsd** — The XML schema for the *\_metadata.xml*
  > file. The XML editor will use this to validate that the XML and any
  > edits made to it are valid and will be understood

  by the target device. It will also be used to provide hints to the
  structure, documentation, and auto-completion.

- **\_tensor_info.xml** — Additional information about the input and
  > output tensors of the core model: their types, shapes, and any
  > quantization information. This is for informational use only. Any
  > changes to this file will be ignored.

- **Any associated files packed into the model** — These are typically
  > text files of lists of labels, CSV files (for score calibration),
  > extra documentation files, and so on, and may be edited within the
  > Innexis CodeBench IDE or with external tools.

  If you created new metadata, the new folder contains the following
  files:

- \_metadata.xml

- \_tensor_info.xml

- full schema

#### Results

  The destination folder is created with XML metadata and associated
  files.
 
  When sending these files to use as external metadata on target
  devices, the files *\_metadata_schema.xsd*
 
  and *\_tensor_info.xml* may be omitted as they are not used for
  inference processing.

##### Editing Metadata in the Innexis CodeBench IDE

  The XML structure maps onto the original FlatBuffer schema provided
  with the TensorFlow Lite Task Library. See **[Model Metadata XML
  Reference](#model-metadata-xml-reference)** for details.
 
  The FlatBuffer schema is available at the following location:

###### [https://github.com/tensorflow/tflite-support/blob/133228616ca14e1b64c03f6a0ea8610f41a60783/](https://github.com/tensorflow/tflite-support/blob/133228616ca14e1b64c03f6a0ea8610f41a60783/tensorflow_lite_support/metadata/metadata_schema.fbs) [tensorflow_lite_support/metadata/metadata_schema.fbs](https://github.com/tensorflow/tflite-support/blob/133228616ca14e1b64c03f6a0ea8610f41a60783/tensorflow_lite_support/metadata/metadata_schema.fbs)

  <span id="_bookmark160" class="anchor"></span>**Deploying Metadata on
  the Target**
 
  External metadata folders can be transferred to the target along with
  models using scp or any other preferred means. The directory
  containing the *\_metadata.xml* file (usually called
  *\<model_filename\>.meta*) should first be compressed into a *.zip*
  file using any suitable tool on the host machine, then placed on the
  target with the model files. See **[Modify the Model
  Cache](#modify-the-model-cache)** for more details.
 
  When a model is loaded by the Task Library, it will check if a
  *\<model\>.meta* folder exists, and if it does, whether it contains a
  *\_metadata.xml* file. If it does, the library will read it and use
  the metadata information in this folder in preference to any metadata
  information embedded in the *.tflite* file.
 
  If this folder does not exist, or does not contain a *\_metadata.xml*
  file, then the library instead falls back to using the model’s
  embedded metadata if it exists.

### Model Metadata XML Reference

  This section is based on the metadata schema from TensorFlow.
 
  For more details on the TensorFlow metadata schema, see the following
  URL:
  **[https://github.com/tensorflow/tflite-support/blob/133228616ca14e1b64c03f6a0ea8610f41a60783/](https://github.com/tensorflow/tflite-support/blob/133228616ca14e1b64c03f6a0ea8610f41a60783/tensorflow_lite_support/metadata/metadata_schema.fbs)
  [tensorflow_lite_support/metadata/metadata_schema.fbs](https://github.com/tensorflow/tflite-support/blob/133228616ca14e1b64c03f6a0ea8610f41a60783/tensorflow_lite_support/metadata/metadata_schema.fbs)**
 
  The schema is copyrighted by the TensorFlow authors, and it is
  licensed under the Apache v2.0 license, which is available at the
  following location:

###### <http://www.apache.org/licenses/LICENSE-2.0>

  The following sections may be present in the metadata.

###### [ModelMetadata 7-22](#_bookmark162)

###### [SubGraphMetadata 7-23](#subgraphmetadata)

###### [TensorMetadata 7-24](#tensormetadata)

###### [TensorGroup 7-25](#tensorgroup)

###### [Stats 7-26](#stats)

###### [ProcessUnit 7-27](#processunit)

###### [Content 7-31](#_bookmark169)

  <span id="_bookmark162" class="anchor"></span>**ModelMetadata**
 
  Standard model description format.
 
  **Attributes**
 
  **name** — The name of the model.
 
  **description** — The model description in schema.
 
  **version** — The version of the model specified by model creators.
 
  **author** — The person who creates this model. **license** — The
  licenses that may apply to this model. **Children**
 
  **SubGraphMetadataList** — Metadata of all the subgraphs of the model,
  of type SubGraphMetadata. The
 
  first is assumed to be the main subgraph.
 
  **AssociatedFileList** — A list of associated files of this model,
  each of type AssociatedFile.

##### SubGraphMetadata

  Details about what the subgraph does.

#### Attributes

  name — The name of the subgraph.
 
  description — The details about what the subgraph does.

#### Children

  **InputMetadataList** — Metadata of all input tensors used in this
  subgraph, each of type TensorMetadata.
 
  **OutputMetadataList** — Metadata of all output tensors used in this
  subgraph, each of type TensorMetadata.
 
  **InputTensorGroupList** — Metadata of all input tensor groups used in
  this subgraph, each of type TensorGroup.
 
  **OutputTensorGroupList** — Metadata of all output tensor groups used
  in this subgraph, each of type TensorGroup.
 
  **InputProcessUnitList** — Input process units of the subgraph. Some
  models may have complex pre- and post-processing logics where the
  process units do not work on one tensor at a time, but instead like a
  TensorFlow Lite graph. For example, in the MobileBert model the inputs
  are ids, mask, or segment ids, and the outputs are end logits and
  start logits.
 
  The pre-processing converts the query string and the context string to
  the model input, and the post- processing converts the model output to
  the answer string. Each entry is of type ProcessUnit.
 
  **OutputProcessUnitList** — Output process units of the subgraph, each
  of type ProcessUnit.
 
  **AssociatedFileList** — A list of associated files of this subgraph,
  each of type AssociatedFile.

##### TensorMetadata

  Detailed information of an input or output tensor.

#### Attributes

  **name** — Name of the Tensor. **description** — Description of the
  Tensor. **Children**
 
  **DimensionNameList** — A list of names of the dimensions in this
  tensor. The length of dimension_names
 
  needs to match the number of dimensions in this tensor.
 
  **Content** — The content that represents this tensor.
 
  **ProcessUnitList** — The process units that are used to process the
  tensor out-of-graph, each of type ProcessUnit.
 
  **Stats** — The statistics of the tensor values.
 
  **AssociatedFileList** — A list of associated files of this tensor,
  each of type AssociatedFile.

##### TensorGroup

  Metadata of a group of tensors.

#### Attributes

  **name** — Name of tensor group.

#### Children

  **TensorNameList** — Names of the tensors to group together,
  corresponding to TensorMetadata.name.

##### Stats

  Statistics to describe a tensor.

#### Children

  **MaxList** — Per-channel maximum value of the tensor.
 
  **MinList** — Per-channel minimum value of the tensor.
 
  If there is only one value in MaxList or MinList, the value will be
  propagated to all channels.

##### ProcessUnit

  A process unit that is used to process the tensor out-of-graph.

#### Children

  One of the following options:

- RegexTokenizerOptions

- SentencePieceTokenizerOptions

- BertTokenizerOptions

- ScoreThresholdingOptions

- ScoreCalibrationOptions

- NormalizationOptions

#### RegexTokenizerOptions

  Splits strings by the occurrences of delim_regex_pattern and converts
  the tokens into ids. For example:
 
  The tokens after split are: "Words", "words", "words", "". The tokens
  can then be converted into ids according to the vocab_file.

###### Attributes

  **delim_regex_pattern** — The regular expression used to split the
  string.

###### Children

  **VocabFileList** — The vocabulary files used to convert tokens into
  ids. Each is of type AssociatedFile.

#### SentencePieceTokenizerOptions

  Performs SentencePiece tokenization as described in
  tf.text.SentencepieceTokenizer. See the following resource for more
  details:

###### [https://github.com/tensorflow/text/blob/master/docs/api_docs/python/text/](https://github.com/tensorflow/text/blob/master/docs/api_docs/python/text/SentencepieceTokenizer.md) [SentencepieceTokenizer.md](https://github.com/tensorflow/text/blob/master/docs/api_docs/python/text/SentencepieceTokenizer.md)

###### Children

  **sentencePiece_model** — The SentencePiece model files used in the
  SentencePieceTokenizer. Type: AssociatedFile.
 
  **vocab_file** — The optional vocabulary model files used in the
  SentencePieceTokenizer. Type: AssociatedFile.

#### BertTokenizerOptions

  Performs Bert tokenization as described in tf.text.BertTokenizer. See
  the following resource for more details:

###### <https://github.com/tensorflow/text/blob/master/docs/api_docs/python/text/BertTokenizer.md> Children

  **vocab_file** — The vocabulary files used in the BertTokenizer. Type:
  AssociatedFile.

#### ScoreThresholdingOptions

  Performs thresholding on output tensor values to filter out
  low-confidence results.

###### Attributes

  **global_score_threshold** — The recommended global threshold below
  which results are considered low- confidence and should be filtered
  out. Type: floating-point number.

#### ScoreCalibrationOptions

  Options to perform score calibration on an output tensor through
  sigmoid functions. One of the main purposes of score calibration is to
  make scores across classes comparable so that a common threshold can
  be used for all output classes. This is meant for models producing
  class predictions as output, for example, image classification or
  detection models.
 
  For each index in the output tensor, the following functions are
  applied:
 
  \`f(x) = scale / (1 + e^-(slope\*g(x)+offset))\` if \`x \> min_score\`
  or if no \`min_score\` has been specified
 
  \`f(x) = default_score\` otherwise or if no scale, slope and offset
  have been specified Where:
 
  scale, slope, offset and (optional) min_score are index-specific
  parameters.
 
  g(x) is an index-independent transform among those defined in
  ScoreTransformationType.
 
  default_score is an index-independent parameter.
 
  An AssociatedFile with type TENSOR_AXIS_SCORE_CALIBRATION specifying
  the index-specific parameters must be associated with the
  corresponding TensorMetadata for score calibration to be applied.

###### Attributes

  **default_score** — The default calibrated score to apply if the
  uncalibrated score is below min_score, or if no parameters were
  specified for a given index.
 
  **score_transformation** — One of the following values:

- **IDENTITY** — Identity function: g(x) = x

- **LOG** — Log function: g(x) = log(x)

- **INVERSE_LOGISTIC** — Inverse logistic function: g(x) = log(x) -
  log(1-x)

#### NormalizationOptions

  Parameters that are used when normalizing the tensor.
 
  “mean” and “std” are normalization parameters. Tensor values are
  normalized on a per-channel basis using the following formula:
 
  (x - mean) / std
 
  If there is only one value in mean or std, propagate the value to all
  channels.
 
  Quantized models share the same normalization parameters as their
  corresponding float models. For example, an image input tensor may
  have the normalization parameter of the following:
 
  mean = 127.5f and std = 127.5f
 
  The image value will be normalized from \[0, 255\] to \[-1, 1\].
 
  Then for quantized models, the image data should be further quantized
  according to the quantization parameters. In the case of uint8, the
  image data will be scaled back to \[0, 255\], while for int8, the
  image data will be scaled to \[-128, 127\].

###### Children

  **MeanList** — Per-channel mean of the possible values used in
  normalization.
 
  **StdList** — Per-channel standard deviation of the possible values
  used in normalization.
 
  <span id="_bookmark169" class="anchor"></span>**Content**
 
  The properties that the content may have, indicating the type of the
  content. A tensor is composed according to one of the following cases:
 
  **Case 1** — The tensor is a single object, such as an image. For
  example, the input of an image classifier, see
  **<https://www.tensorflow.org/lite/examples/image_classification/overview>**
  for details, which is a tensor of shape \[1, 224, 224, 3\]. Dimensions
  1 to 3 correspond to the image. Since dimension 0 is a batch axis
  which can be ignored, "ValueRange" can be left empty.
 
  **Case 2** — The tensor contains multiple instances of the same
  object. For example, the output tensor of detected bounding boxes of
  an object detection model, see
  **[https://www.tensorflow.org/lite/examples/](https://www.tensorflow.org/lite/examples/object_detection/overview)
  [object_detection/overview](https://www.tensorflow.org/lite/examples/object_detection/overview)**
  for details. The tensor shape is \[1, 10, 4\] where the three
  dimensions represent the following:

- **dimension 0** — The batch axis.

- **dimension 1** — The 10 objects detected with the highest confidence.

- **dimension 2** — The bounding boxes of the 10 detected objects.

  Set "range" to the number of dimensions which is {min=2; max=2;} to
  denote that every element in the tensor is an individual content
  object, in this case, a score.
 
  Another example is the pose estimation model; see
  **[https://www.tensorflow.org/lite/examples/](https://www.tensorflow.org/lite/examples/pose_estimation/overview)
  [pose_estimation/overview](https://www.tensorflow.org/lite/examples/pose_estimation/overview)**
  for details. The output tensor of heatmaps is in the shape of \[1, 9,
  9, 17\]. In this case, the four dimensions represent:

- **dimension 0** — The batch axis.

- **dimension 1/2** — The heatmap image.

- **dimension 3** — 17 body parts of a person.

  Even though the last axis is the body part, the real content of this
  tensor is the heatmap. The "range" should be \[min=1; max=2\].
 
  **Case 3** — The tensor contains multiple different objects.
 
  Sometimes a tensor may contain multiple different objects, thus
  different contents. This is very common for regression models. For
  example, a model to predict fuel efficiency, see
  **[https://www.tensorflow.org/](https://www.tensorflow.org/tutorials/keras/regression)
  [tutorials/keras/regression](https://www.tensorflow.org/tutorials/keras/regression)**
  for details.
 
  The input tensor has shape \[1, 9\] which consists of nine features
  such as "Cylinders", "Displacement", "Weight", and so on. In this case
  dimension 1 contains nine different Contents. However, since these
  sub-dimension objects barely need to be specifically processed, their
  contents are not recorded in the metadata. Though the name of each
  dimension can be set through TensorMetadata.dimension_names.

###### Children

  **ValueRange** — The range of dimensions that the content corresponds
  to, specified by the minimum and maximum dimension index.
 
  One of the following, depending on the choice of content:

- BoundingBoxProperties

- AudioProperties

- ImageProperties

#### BoundingBoxProperties

  Properties describing bounding box information.

###### Attributes

  **type** — Indicates how to parse the bounding box dimension values.
  Can be one of the following attributes:

- UNKNOWN — Unspecified.

- BOUNDARIES — Represents the bounding box by using the combination of
  > boundaries, {left, top, right, bottom}. The default order is {left,
  > top, right, bottom}. Other orders can be indicated by
  > BoundingBoxProperties.index.

- UPPER_LEFT — Represents the bounding box by using the upper_left
  > corner, width, and height. The default order is {upper_left_x,
  > upper_left_y, width, height}. Other orders can be indicated by
  > BoundingBoxProperties.index.

- CENTER — Represents the bounding box by using the center of the box,
  > width, and height. The default order is {center_x, center_y, width,
  > height}. Other orders can be indicated by
  > BoundingBoxProperties.index.

  **coordinate_type** — Indicates how to parse the bounding box
  coordinate values. Can be one of the following attributes:

- RATIO — The coordinates are float values from 0 to 1.

- PIXEL — The coordinates are integers.

###### Children

  **IndexList** — A list of integers. Denotes the order of the elements
  defined in each bounding box type. An empty index array represents the
  default order of each bounding box type. For example, to denote the
  default order of BOUNDARIES, {left, top, right, bottom}, the index
  should be {0, 1, 2, 3}. To denote the order {left, right, top,
  bottom}, the order should be {0, 2, 1, 3}.
 
  The index array can be applied to all bounding box types to adjust the
  order of their corresponding underlying elements.

#### AudioProperties

  The properties for audio tensors.

###### Attributes

  **sample_rate** — The sample rate in Hz when the audio was captured.
 
  **channels** — The channel count of the audio.

#### ImageProperties

  The properties for image tensors.

###### Attributes

  **color_space** — The color space of the image. Options:

- UNKNOWN

- RGB

- GRAYSCALE

###### Children

  **ImageSize** — Indicates the default value of image width and height
  if the tensor shape is dynamic. For a fixed-size tensor, this size
  will be consistent with the expected size. Attributes: width and
  height

#### AssociatedFile

  The properties of a file.

###### Attributes

  **name** — Name of this file.
 
  **description** — A description of the file.
 
  **type** — Type of the associated file. There may be special pre- or
  post-processing for some types. For example, in image classification,
  a label file of the output will be used to convert object index into
  string.
 
  Options:

- UNKNOWN — Undefined.

- DESCRIPTIONS — Files such as *readme.txt*.

- TENSOR_AXIS_LABELS — Contains labels that annotate certain axis of the
  tensor. For example, the label file in image classification. Those
  labels annotate the output tensor, such that each value in the output
  tensor is the probability of that corresponding category specified by
  the label.

- TENSOR_VALUE_LABELS — Contains labels that tensor values correspond
  to. For example, in the object detection model, one of the output
  tensors is the detected classes. And each value in the tensor refers
  to the index of label in the category label file.

- TENSOR_AXIS_SCORE_CALIBRATION — Contains sigmoid-based score
  calibration parameters, formatted as CSV. Lines contain for each index
  of an output tensor the scale, slope, offset and (optional) min_score
  parameters to be used for sigmoid fitting (in this order and in
  \`strtof\`-compatible format). A line may

  be left empty to default calibrated scores for this index to
  default_score. In summary, each line should contain zero, three, or
  four comma-separated values.
 
  See the topic **[ScoreCalibrationOptions](#scorecalibrationoptions)**
  for more information.

- VOCABULARY — Contains a list of unique words, such as characters
  separated by "\n" or in lines, that help to convert natural language
  words to embedding vectors.

  **locale** — An optional locale for this associated file, if
  applicable. It is recommended to use an ISO 639-1 letter code (for
  example, "en" for English) that is optionally completed by a
  two-letter region code (for example, "en-US" for US English and
  "en-CA" for Canadian English). You can leverage this to specify
  multiple label files translated in different languages.

## Hardware Acceleration

  The ML feature supports hardware acceleration. This functionality is
  typically used for more complex models and improves performance and
  power efficiency as compared with the same tasks running on CPUs.
 
  This translates to support for Graphics Processing Units (GPUs), as
  other types of accelerators are not currently supported. GPUs can be
  used whenever they have sufficient capability and bandwidth to support
  compute tasks as well as graphics work.
 
  Generally, two components are required to use a hardware acceleration
  device with ML and TensorFlow Lite:

- Drivers and libraries for the acceleration device, from the BSP or
  device vendor.

- A “delegate” library to interface between TensorFlow Lite and the
  device drivers or libraries.

  The ML feature includes components necessary for the following
  hardware acceleration configurations:

- Virtio GPU, through the OpenCL™ or OpenGL ES APIs

- Custom GPU IP, through the OpenCL or OpenGL ES APIs

  For more information, see "Using a GPU". In addition to these, support
  for ML can be extended to other accelerators like TPUs and NPUs, and
  other configurations. Please contact your Siemens account manager if
  you need support for a different accelerator or configuration.

###### [Using a GPU 7-35](#using-a-gpu)

###### [Using Accelerators with External Delegates 7-37](#using-accelerators-with-external-delegates)

### Using a GPU

  ML supports the use of a GPU for accelerating inference through the
  standard GPU delegate included with TensorFlow Lite. This leverages
  OpenCL drivers if they are present. Otherwise, it falls back to OpenGL
  ES drivers. OpenCL is optional but will generally give better
  inference performance at the cost of a longer start-up time. OpenGL ES
  drivers must be present on the target for GPU acceleration to be
  available.

###### [Configuration and Building With GPU Support 7-35](#configuration-and-building-with-gpu-support)

###### [Enabling the GPU Within Applications 7-36](#enabling-the-gpu-within-applications)

##### Configuration and Building With GPU Support

  You must build the GPU delegate with Innexis Linux. ML, when enabled,
  will automatically build and deploy the GPU delegate when any of the
  supported GPU configurations are enabled in the build.
 
  The following configurations are available:
 
  **Virtio GPU** This is a paravirtualized GPU for use with the virtual
  platforms, which allows the guest Innexis Linux OS to use the
  capabilities of the host GPU. It is enabled using the "virtio-gpu"
  user feature in your build's *local.conf* file. For details on the
  target BSP, see the following sections:

###### [VirtIO-GPU Support for Innexis Hybrid](#_bookmark37)

- [**VirtIO-GPU Support for Innexis
  > ANA**](#virtio-gpu-support-for-innexis-ana)

###### Custom GPU IP

  This is the emulated GPU from an RTL IP. If integrated with the
  Innexis Hybrid BSP, both in hardware design and the Innexis Linux
  build, it is available as a GPU device on the target. To integrate
  support for a custom GPU IP with the Innexis Linux BSP, see [**GPU IP
  Support**](#gpu-ip-support). When adding support for a custom GPU IP
  in Innexis Linux, either of OpenGL ES or OpenCL, libgbm, and libEGL
  libraries must be present in the BSP for your target; otherwise, the
  build will fail.

##### Enabling the GPU Within Applications

  To enable GPU within applications, you must use task objects within
  the Task Library.

1.  Configure a SemlAccelerationConfig object by calling the function
    > SetComputeMode() and passing in the option ComputeMode::kGPU.

2.  Pass in a pointer to the configuration object when calling
    > CreateFromOptions() when creating your task object.

  Then you must run the application as root or as a user with access to
  the GPU device.
 
  The GPU delegate accesses the primary GPU device through its DRM
  device node */dev/dri/card0*. This is the render node that the
  delegate attempts to use by default. If you want to use a different
  GPU device (for example, */dev/dri/card1*), set the following
  environment variable to change it:
 
  export FLEXML_RENDER_NODE="/dev/dri/card1"
 
  If your system has OpenCL drivers present but you prefer not to use
  them for inference, set the following environment variable:
 
  export FLEXML_DISABLE_OPENCL=1
 
  Model inference will fail if any of the following occurs:

- The render node is wrong.

- The GPU delegate or prerequisite drivers are not present on your
  > target board.

- The model is not compatible with the requested hardware accelerator.

  To use the GPU delegate directly with a tflite::Interpreter object,
  consult the TensorFlow Lite documentation.

### Using Accelerators with External Delegates

  An external delegate is a library that provides a hardware-specific
  acceleration back-end to TensorFlow Lite. This library is separate
  from the core TensorFlow Lite libraries and can be dynamically loaded,
  enabling accelerators to be added without rebuilding the core
  libraries.
 
  To use an external delegate with a task object, do the following:

- Configure a SemlAccelerationConfig object using the
  > SetExternalDelegateLibPath() and SetExternalDelegateOptions() APIs .

- Pass in a pointer to the configuration object when calling
  > CreateFromOptions() when creating your task object.

  To use an external delegate directly with a tflite::Interpreter
  object, consult the TensorFlow Lite documentation or the documentation
  for the delegate.
 
  Siemens can assist with integration of other accelerator devices on a
  services basis. Please contact your account manager for details.

## Performance Analysis and Optimization

  There are many factors that can impact the performance of an ML
  inference. For example:

- The internal architecture of the model

- The complexity of the pre- and post-processing stages

- The hardware and libraries used for the large amounts of intense
  > mathematical processing; whether it takes place on specialized
  > hardware or CPU, how many CPU threads are in use, and so on

- Other processes running on the target platform at the same time

  It can be a difficult problem to balance the performance of ML
  inferences against the other needs of the running device, but ML
  provides various tools to help analyze and address such issues.

###### [Using Innexis CodeBench Analyzer to Profile ML Inferences 7-37](#using-innexis-codebench-analyzer-to-profile-ml-inferences)

### Using Innexis CodeBench Analyzer to Profile ML Inferences

  Innexis CodeBench Analyzer is a tool provided with the Innexis
  CodeBench IDE that enables you to collect performance data from the
  target based on LTTng instrumentation. This data can then be
  visualized
 
  and analyzed within the tool. In the supplied configuration, the
  extended Task Library of ML will output instrumentation of ML
  activities. Innexis CodeBench Analyzer can then be used to analyze
  this using
 
  the ML Inference Agent. For more information, see the Innexis
  CodeBench Analyzer documentation for guidance on the general use of
  the tool.
 
  **ML Inference Agent**
 
  The purpose of the ML Inference Agent is to show when ML inferences
  are performed and to show their internal operations so their
  performance can be compared to the rest of the system's activity.
 
  An example inference may look like the following:

<img src="media/image22.png" style="width:6.28646in;height:0.48437in" />

  The "Stage" line breaks down the inference activity into several
  stages:

- **Pre-processing** — This stage deals with processing the input data
  to the model into a format the model will understand, based upon the
  model's embedded metadata

- **Inference** — This stage is where the input data is analyzed by the
  model, and the results are generated

- **Post-processing** — This stage takes the raw results from the
  inference stage, and processes them into a more user-friendly format,
  in accordance with the model's metadata

  The "Operation" line shows the individual operations of each inference
  as defined by the model in use. These typically correspond to layers
  in a network and are executed serially. The agent view indicates
  whether each operation was executed on the CPU or by a delegate. A
  delegate is an alternative implementation of one or more operations,
  typically using some form of hardware acceleration. Normal CPU
  operations are colored purple and blue, whereas delegated operations
  are colored with a yellow and red palette, and will show the name of
  the delegate used as part of the operation's label, for example:

<img src="media/image23.png" style="width:5.69271in;height:0.70833in" />

  If any of the model's operations are executed in parallel, additional
  "Operation" lines will be added in an ad-hoc manner. These do not
  correspond to any particular resource allocation but are separated out
  for visual clarity alone. Similarly, if more than one inference is
  being performed at the same time, additional "Stage" and "Operation"
  lines will be added to show the parallel nature of the execution.
 
  The “node locations” mentioned on the “Operation” bars refer to the
  operation node's location within the larger model. To match up this
  information to the model architecture, use a TensorFlow Lite model
  viewing application such as Netron,
  [**https://netron.app/**](https://netron.app/).
 
  For example, the “node location 7” noted here:
 
  <img src="media/image24.png" style="width:4.875in;height:0.54167in" />
 
  matches this operation in the graph:

<img src="media/image25.jpeg"
style="width:7.23052in;height:2.10979in" />

#### System Performance Analysis

  Innexis CodeBench Analyzer can be used to investigate performance
  problems by viewing the properties of the whole system at different
  points in time. The ML agents should be used in concert with the other
  agents, showing different aspects of the system.
 
  For example:

- If a CPU-based inference is too slow, Innexis CodeBench Analyzer can
  > be used to show what other processes are running in the system, and
  > if there is contention for the CPU.

- The ML Inference Agent can be used to check the pre-processing section
  > – if this is noticeably large, investigations can focus on what
  > could be done to reduce this.

- If there are any ML inference stages that may take a long time, this
  > can be investigated further by looking into the model structure.

- Other system-wide factors can affect performance and increase
  > inference times such as RAM or other resource exhaustion, too many
  > other processes running at the same time, and more.

## Example Applications

  Several example applications are available, which can be created in
  the Innexis CodeBench IDE.
 
  To create the sample applications, launch the Innexis CodeBench IDE,
  and choose **File** \> **New** \> **C++ Project**.
 
  The following table lists the examples:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Example</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Models Tested and Included</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ML Image Classifier</td>
<td><blockquote>
<p>Classifies the content of an</p>
</blockquote></td>
<td>Float32 (default):</td>
</tr>
<tr class="even">
<td></td>
<td>image. Model trained on a range</td>
<td><em>mobilenet_v2_1.0_224_1_metad</em></td>
</tr>
<tr class="odd">
<td></td>
<td>of everyday objects.</td>
<td><em>ata_1.tflite</em></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Origin</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>link: <a
href="https://www.kaggle.com/models/tensorflow/mobilenet-v2/tfLite/1-0-224-metadata/1"><strong>https://www.kaggle.com/</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/tensorflow/mobilenet-v2/tfLite/1-0-224-metadata/1"><strong>models/tensorflow/mobilenet-</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/tensorflow/mobilenet-v2/tfLite/1-0-224-metadata/1"><strong>v2/tfLite/1-0-224-metadata/1</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><em>resnet-v2-tflite-101-metadata-</em></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><em>v1.tflite</em></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Original</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>link: <a
href="https://www.kaggle.com/models/tensorflow/resnet-v2/tfLite/101-metadata"><strong>https://www.kaggle.com/</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/tensorflow/resnet-v2/tfLite/101-metadata"><strong>models/tensorflow/resnet-v2/</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/tensorflow/resnet-v2/tfLite/101-metadata"><strong>tfLite/101-metadata</strong></a></td>
</tr>
<tr class="even">
<td><blockquote>
<p>ML Image Segmenter</p>
</blockquote></td>
<td><blockquote>
<p>Segments an image into</p>
</blockquote></td>
<td>Float32:</td>
</tr>
<tr class="odd">
<td></td>
<td><blockquote>
<p>recognized objects, pixel-by-pixel.</p>
</blockquote></td>
<td><em>deeplabv3_1_metadata_2.tflite</em></td>
</tr>
<tr class="even">
<td></td>
<td>Model trained on a range of</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>everyday objects.</td>
<td>Origin</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>link:<a
href="https://www.kaggle.com/models/tensorflow/deeplabv3/tfLite/metadata/2"><strong>https://www.kaggle.com/</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/tensorflow/deeplabv3/tfLite/metadata/2"><strong>models/tensorflow/deeplabv3/</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/tensorflow/deeplabv3/tfLite/metadata/2"><strong>tfLite/metadata/2</strong></a></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>ML Object Detector</p>
</blockquote></td>
<td>Detects the presence of known</td>
<td>Quantized Int8:</td>
</tr>
<tr class="even">
<td></td>
<td>objects within an image</td>
<td><em>mobile_object_localizer_v1_1_m</em></td>
</tr>
<tr class="odd">
<td></td>
<td>and supplies bounding boxes</td>
<td><em>etadata_2.tflite</em></td>
</tr>
<tr class="even">
<td></td>
<td>indicating their location.</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Origin</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>link:<a
href="https://www.kaggle.com/models/google/mobile-object-localizer-v1/tfLite/metadata/2"><strong>https://www.kaggle.com/</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/google/mobile-object-localizer-v1/tfLite/metadata/2"><strong>models/google/mobile-object-</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/google/mobile-object-localizer-v1/tfLite/metadata/2"><strong>localizer-v1/tfLite/metadata/2</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><em>coco_ssd_mobilenet_v1_1.0_qua</em></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><em>nt_2018_06_29_score_calibratio</em></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><em>n.tflite</em></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Original link: <a
href="https://github.com/tensorflow/tflite-support/blob/r0.4.4/tensorflow_lite_support/cc/test/testdata/task/vision/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29_score_calibration.tflite"><strong>https://github.com/</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://github.com/tensorflow/tflite-support/blob/r0.4.4/tensorflow_lite_support/cc/test/testdata/task/vision/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29_score_calibration.tflite"><strong>tensorflow/tflite-support/blob/</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://github.com/tensorflow/tflite-support/blob/r0.4.4/tensorflow_lite_support/cc/test/testdata/task/vision/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29_score_calibration.tflite"><strong>r0.4.4/</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://github.com/tensorflow/tflite-support/blob/r0.4.4/tensorflow_lite_support/cc/test/testdata/task/vision/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29_score_calibration.tflite"><strong>tensorflow_lite_support/cc/test/</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://github.com/tensorflow/tflite-support/blob/r0.4.4/tensorflow_lite_support/cc/test/testdata/task/vision/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29_score_calibration.tflite"><strong>testdata/task/vision/</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://github.com/tensorflow/tflite-support/blob/r0.4.4/tensorflow_lite_support/cc/test/testdata/task/vision/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29_score_calibration.tflite"><strong>coco_ssd_mobilenet_v1_1.0_qu</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://github.com/tensorflow/tflite-support/blob/r0.4.4/tensorflow_lite_support/cc/test/testdata/task/vision/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29_score_calibration.tflite"><strong>ant_2018_06_29_score_calibrat</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://github.com/tensorflow/tflite-support/blob/r0.4.4/tensorflow_lite_support/cc/test/testdata/task/vision/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29_score_calibration.tflite"><strong>ion.tflite</strong></a></td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><blockquote>
<p><strong>Example</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Description</strong></p>
</blockquote></th>
<th><blockquote>
<p><strong>Models Tested and Included</strong></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ML Image Embedder</td>
<td>Calculates a measurement of</td>
<td>Float32:</td>
</tr>
<tr class="even">
<td></td>
<td>similarity between two images</td>
<td><em>mobilenet_v3_small_100_224_e</em></td>
</tr>
<tr class="odd">
<td></td>
<td>based on their detected features.</td>
<td><em>mbedder.tflite</em></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Origin</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>link: <a
href="https://www.kaggle.com/models/google/mobilenet-v3/tfLite/small-100-224-feature-vector-metadata/1"><strong>https://www.kaggle.com/</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/google/mobilenet-v3/tfLite/small-100-224-feature-vector-metadata/1"><strong>models/google/mobilenet-v3/</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/google/mobilenet-v3/tfLite/small-100-224-feature-vector-metadata/1"><strong>tfLite/small-100-224-feature-</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/google/mobilenet-v3/tfLite/small-100-224-feature-vector-metadata/1"><strong>vector-metadata/1</strong></a></td>
</tr>
<tr class="odd">
<td><blockquote>
<p>ML Audio Classifier</p>
</blockquote></td>
<td><blockquote>
<p>Classifies a sound from a given</p>
</blockquote></td>
<td><blockquote>
<p>Quantized Int8: lite-</p>
</blockquote></td>
</tr>
<tr class="even">
<td></td>
<td><blockquote>
<p>audio clip. Model trained on a</p>
</blockquote></td>
<td><blockquote>
<p>model_yamnet_classification_tflit</p>
</blockquote></td>
</tr>
<tr class="odd">
<td></td>
<td><blockquote>
<p>range of everyday sounds.</p>
</blockquote></td>
<td>e_1.tflite</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Origin</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>link: <a
href="https://www.kaggle.com/models/google/yamnet/tfLite/classification-tflite/1"><strong>https://www.kaggle.com/</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/google/yamnet/tfLite/classification-tflite/1"><strong>models/google/yamnet/tfLite/</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/google/yamnet/tfLite/classification-tflite/1"><strong>classification-tflite/1</strong></a></td>
</tr>
<tr class="even">
<td><blockquote>
<p>Bert Question Answerer</p>
</blockquote></td>
<td><blockquote>
<p>Performs tokenization for models</p>
</blockquote></td>
<td><blockquote>
<p><em>mobilebert-tflite-metadata-</em></p>
</blockquote></td>
</tr>
<tr class="odd">
<td></td>
<td><blockquote>
<p>(BERT, Albert, and so on) in</p>
</blockquote></td>
<td><em>v1.tflite</em></td>
</tr>
<tr class="even">
<td></td>
<td><blockquote>
<p>preprocess and returns most</p>
</blockquote></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td><blockquote>
<p>possible answers.</p>
</blockquote></td>
<td>Origin</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>link: <a
href="https://www.kaggle.com/models/tensorflow/mobilebert/tfLite"><strong>https://www.kaggle.com/</strong></a></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/tensorflow/mobilebert/tfLite"><strong>models/tensorflow/mobilebert/</strong></a></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td><a
href="https://www.kaggle.com/models/tensorflow/mobilebert/tfLite"><strong>tfLite</strong></a></td>
</tr>
</tbody>
</table>

###### [Command-Line Options 7-42](#command-line-options)

  [**Switching Demo Models** **7-44**](#switching-demo-models)

### Command-Line Options

  There are command-line options available to all supplied image demos
  and options specific to individual demos.

#### Options Common to All Demos

###### General

  **--compute=(cpu_reference \| cpu_optimized \| gpu)** — Determines the
  compute delegates used for the ML processing. Specifying cpu_reference
  will just use the basic CPU functionality. Specifying cpu_optimized
  will use instruction set extensions if available.
 
  **--cpu_threads=(number)** — Specifies how many execution threads to
  use during inference, applicable only for CPU compute modes.
 
  **--external_delegate_path=(path)** — Specifies the path to an
  external delegate library to load and use for hardware acceleration.
  Overrides the --compute and --cpu_threads settings.
 
  **--external_delegate_options=(string)** — Semicolon-separated list of
  options to pass to the external delegate in the following format:
  "option_name_1:option_value_1;option_name_2:option_value_2;... ".

###### Benchmarking

  **--warmups=(number), --iterations=(number)** — If either of these are
  specified, the demo will be in benchmark mode, and perform the
  inference (--warmups plus --iterations) times. Statistics about the
  inference during the last --iterations number of times will be
  displayed on the console output.

#### Options Specific to Individual Demos

###### ML Image Classifier

  **--image_path=(path)** — The full, absolute path to the image to
  classify. Ignored if --use_camera=1 is set.
 
  **--max_results=(number)** — The maximum number of results to display.
 
  **--score_threshold=(float)** — The minimum score of a result;
  classifications with a score less than this are discarded.
 
  **--class_name_allowlist=(comma-separated list of classes)** — If
  specified, the results will only contain classes that are also in this
  list.
 
  **--class_name_denylist=(comma-separated list of classes)** — If
  specified, the results will not contain classes that are in this list.

###### ML Image Segmenter

  **--image_path=(path)** — The full, absolute path to the image to
  segment. Ignored if use_camera=1 is set.
 
  **--output_mask_png=(path)** — The output *.png* file that will be
  created, showing the image segment classifications.

###### ML Object Detector

  **--image_path=(path)** — The full, absolute path to the image to
  detect objects in. Ignored if -- use_camera=1 is set.
 
  **--output_png=(path)** — The output *.png* file that can be created,
  showing the object bounding boxes.
 
  **--max_results=(number)** — The maximum number of results to display.
 
  **--score_threshold=(float)** — The minimum score of a result;
  detections with a score less than this are discarded.
 
  **--class_name_allowlist=(comma-separated list of classes)** — If
  specified, the results will only contain classes that are also in this
  list.
 
  **--class_name_denylist=(comma-separated list of classes)** — If
  specified, the results will not contain classes that are in this list.

###### ML Image Embedder

  **--first_image_path=(path), --second_image_path=(path)** — The two
  images to compare.
 
  **--l2_normalize=(true \| false)** — If set to true, the feature
  vectors returned from the model will be normalized with L2-norm.
 
  **--quantize=(true \| false)** — If set to true, the feature vectors
  returned from the model will be quantized before similarity is
  calculated.

###### ML Audio Classifier

  **--audio_wav_path=(path)** — Path to an audio file to classify, in
  16-bit PCM WAV format. The *WAV* file must have a single channel and a
  sampling rate that matches the rate expected by the model (per the
  model metadata). If the *WAV* file is longer than what the model
  requires, only the start is used for inference.
 
  **--score_threshold=(float)** — The minimum score of a result;
  classifications with a score less than this are discarded.

###### BERT Question Answerer

  **--question=(text)** — A simple question to infer from a given text.
 
  **--context=(text)** — Paragraph of text for inference.

### Switching Demo Models

  To switch supplied models with custom ones, update the model cache as
  described in the section **[Modify](#modify-the-model-cache) [the
  Model Cache](#modify-the-model-cache)**. All demo models are
  pre-installed into the "*/flex-ml/demo_models/*" directory on the
  target. To switch to another model pre-installed on the target, change
  the model cache path to the new location using the environment
  variable FLEXML_MODEL_CACHE_PATH.

# Sample Application Walkthrough

  This section walks you through how to create, build, deploy, run, and
  profile a sample ML application.

###### [Create a Sample Application............................................................................................................... A-1](#_bookmark181)

  [**Deploy and Run the Sample
  Application.............................................................................................
  A-2**](#_bookmark182)
 
  **[Performing
  Benchmarking..................................................................................................................
  A-3](#performing-benchmarking) [Set Up Profiling Using Innexis
  CodeBench
  Analyzer...........................................................................
  A-3](#set-up-profiling-using-innexis-codebench-analyzer)**
 
  <span id="_bookmark181" class="anchor"></span>**Create a Sample
  Application**
 
  Create a sample ML application using the Innexis CodeBench IDE.
 
  **Prerequisites**

- The Innexis CodeBench IDE has been launched.

- An SDK has been installed as described in [**Set Up the SDK for
  > Innexis CodeBench**](#set-up-the-sdk-for-innexis-codebench).

- Innexis Linux is running on a target platform instance, and it has
  > been configured to allow incoming GDB and SSH connections as
  > described in [**Set Up Port Forwarding for the
  > Target**](#_bookmark60).

#### Procedure

1.  In the Innexis CodeBench IDE, choose **File** \> **New** \> **C++
    > Project**.

2.  Set a project name (assumed to be “image_classifier_demo” in the
    > remainder of this section), then select the project type ML Image
    > Classifier. Click **Next**.

3.  In the Innexis CodeBench configuration section, select the SDK that
    > you installed in the Prerequisites, and check the Innexis
    > CodeBench Analyzer tracing support checkbox.

4.  Complete the rest of the steps as described in **[Create a Project
    > Using an SDK](#create-a-project-using-an-sdk-2)** to get remote
    > connection, compiler settings and sysroot, and so on configured
    > for your project.

5.  Right-click the name of the project and select **Build Project**
    > from the context menu.

#### Results

  You should now have a new project with the following items:
 
  ***src/image_classifier_demo.cc*** — The main source file for the
  application, which implements command- line parameters and makes the
  call to classify a user-supplied image.
 
  ***src/utils/image_utils.cc* and *image_utils.h ***— General purpose
  image reading and writing routines used by the main application code.
 
  ***src/utils/v412_camera.c* and *v412_camera.h ***— Camera scanning
  software designed to interface with a video capture device.
 
  ***test/mobilenet_v2_1.0_224_1_metadata_1.tflite*** — The model used
  during inference. This is already available on the target root file
  system.
 
  ***test/sparrow.jpg*** — An image which the included model can
  classify. This needs to be deployed on the target file system. See
  [**Deploy and Run the Sample Application**](#_bookmark182).
 
  ***Debug/\<project_name\>*** — The built image object file which is
  suitable for downloading to the target.
 
  <span id="_bookmark182" class="anchor"></span>**Deploy and Run the
  Sample Application**
 
  After successfully building the sample application, deploy it to the
  target, and then run it on the target.

#### Prerequisites

- You have created a sample application.

- You have launched the Innexis CodeBench IDE.

#### Procedure

1.  In the Project Explorer, right-click the project name and choose
    > **Debug As** \> Innexis CodeBench

###### Application.

2.  In the Edit Configuration dialog box, choose the **Debugger** tab,
    > then the **Commands** sub-tab.

3.  Click the Add command dropdown and choose **Upload**.

4.  Set the Upload path to the *sparrow.jpg* file in the project test
    > folder, and set the “To” path to "*/run/user/0*", which
    > corresponds to the target environment variable \$XDG_RUNTIME_DIR.
    > Set the Connection to the IP address of your target board, then
    > click **OK**.

5.  Choose the **Arguments** tab, and then paste the following into the
    > Program Arguments field:

    - "--image_path=\$XDG_RUNTIME_DIR/sparrow.jpg", to provide the image
      > path

    - "--compute=gpu", to include GPU support when available. For GPU
      > delegate to work, the required libraries should be present on
      > the target root file system. For details see [**Using a
      > GPU**](#using-a-gpu).

    - For a list of other command-line options that can be used with the
      > image classifier demo, see the

###### [Example Applications](#example-applications).

6.  Click **Apply**, then click **Debug** to launch the program. If you
    > are prompted to switch perspectives, click **Switch**.

#### Results

  The code is downloaded to the target and runs, but stops at the first
  statement in the main() call.

- Standard code execution tasks (step, breakpoints, variable inspection)
  > can be conducted here; clicking the **Resume** button continues the
  > run.

- <img src="media/image26.jpeg" style="width:7.14in;height:0.85125in" />To
  > see the demo output, click the dropdown next to the **Display
  > Selected Console** button from the bottom pane, and choose the GDB
  > Server console.

- In this example, the machine learning prediction predicts the sample
  image is a “junco”, which is a North American sparrow.

- If the argument "–compute=gpu" is selected, and GPU support is
  present, a TensorFlow Lite delegate for the GPU is created and
  reported as such in the output.

## Performing Benchmarking

  The example software includes additional parameters that return
  benchmarks on the run.
 
  **--warmups=X** — Specifies the number of times the inference is run
  before the benchmarking begins.
 
  **--iterations=Y** — Specifies the number of times the inference is
  run during execution.
 
  When the application is run, the total (X+Y) inferences are performed,
  but only statistics from the Y runs are reported.

## Set Up Profiling Using Innexis CodeBench Analyzer

  Use Innexis CodeBench Analyzer to view and profile system-wide
  activity. In this procedure, you will configure and open a performance
  run.

#### Prerequisites

- The Innexis CodeBench IDE is up and running.

- (Windows only) For a host system with high DPI or 4K displays, there
  > is a known issue requiring some additional steps:

1.  Right-click the Innexis CodeBench Analyzer IDE 2025.1.0 icon and
    > select **Properties**.

2.  Click the **Compatibility** tab.

3.  Click **Change high DPI Settings**.

4.  Activate Override high DPI scaling behavior and change it to System.

5.  Click **OK**, close the dialog box, and launch the Innexis CodeBench
    > IDE again.

    - The sample image has been uploaded to the target root file system.
      See **[Deploy and Run the Sample](#_bookmark182)
      [Application](#_bookmark182)** for details.

#### Procedure

1.  In the Innexis CodeBench IDE, choose **File** \> **New** \>
    > **Other** and select Innexis CodeBench Analyzer Project. Click
    > **Next**.

2.  Specify a name for the project and click **Finish**. Then click
    > **Open Perspective** when the dialog box displays.

  This accepts the perspective change to the Innexis CodeBench Analyzer
  view.

3.  In the Innexis CodeBench Analyzer view, choose **File** \> **New**
    > \> **Other** and select Innexis CodeBench Analyzer Session. Click
    > **Next**.

4.  In the Launch Configuration dialog, browse to the project under the
    > Session folder if it is not already selected, then choose **New
    > Launch Configuration**.

5.  Select Innexis CodeBench Analyzer from the list of launch groups,
    > then click the **New** button.

6.  In the **Main** tab, configure the new analyzer session settings as
    > follows:

    - **Connection** — Set to the connection of the target platform as
      > created under **[Create a Sample](#_bookmark181)
      > [Application](#_bookmark181)**.

    - **Toolchain** — Set to the SDK used to build the application.

    - **Project** — Browse to the example project you created in
      > [**Create a Sample Application**](#_bookmark181).

7.  Switch to the **Arguments** tab and set the --image_path option and,
    > optionally, the --compute option for acceleration.

  For example, adding in benchmarking options:

8.  Click **Apply**, then **Close**. In the Launch Configuration dialog,
    > ensure the newly created profiling configuration is selected.
    > Click **Next**, select Empty Session, and then click **Finish**.

#### Results

  The newly created session appears in the Analysis Sessions list.
 
  <img src="media/image27.jpeg"
  style="width:7.18312in;height:2.78437in" />

- Double-clicking the ML Inference Agent adds it to the empty session.
  You can also add other Agents at this point.

- To profile the application, choose **Run** \> **Profile
  Configurations** and select the profiling configuration created
  earlier. Click **Profile** to run the profiling process. This uploads
  the executable and profiling scripts to the target, runs the
  application, and returns the results to Innexis CodeBench Analyzer.

# A. Sample Code for Profiling With Perfetto

  The following source code is for the C++ example
  *perfetto_example_sdk.cpp*. See **[Profile
  Applications](#profile-applications-using-the-perfetto-sdk) [Using the
  Perfetto SDK](#profile-applications-using-the-perfetto-sdk)** for more
  information.
 
  //
 
  ----------------------------------------------------------------------------
 
  --------------------
 
  // SPDX-License-Identifier: MIT
 
  //
 
  ----------------------------------------------------------------------------
 
  --------------------
 
  \#include "perfetto.h"
 
  \#include \<chrono\>
 
  \#include \<fstream\>
 
  \#include \<thread\>
 
  PERFETTO_DEFINE_CATEGORIES(
 
  PERFETTO_CATEGORY(rendering)); PERFETTO_TRACK_EVENT_STATIC_STORAGE();
 
  void InitializePerfetto() { perfetto::TracingInitArgs args;
 
  // The backends determine where trace events are recorded. For this
  example we
 
  // are going to use the in-process tracing service, which only
  includes in-app
 
  // events.
 
  args.backends = perfetto::kInProcessBackend;
 
  perfetto::Tracing::Initialize(args); perfetto::TrackEvent::Register();
 
  }
 
  std::unique_ptr\<perfetto::TracingSession\> StartTracing() {
 
  // The trace config defines which types of data sources are enabled
  for
 
  // recording. In this example we just need the "track_event" data
  source,
 
  // which corresponds to the TRACE_EVENT trace points.
  perfetto::TraceConfig cfg;
 
  cfg.add_buffers()-\>set_size_kb(1024);
 
  auto\* ds_cfg = cfg.add_data_sources()-\>mutable_config();
  ds_cfg-\>set_name("track_event");
 
  auto tracing_session = perfetto::Tracing::NewTrace();
 
  tracing_session-
 
  \>Setup(cfg); tracing_session-
 
  \>StartBlocking();
 
  return tracing_session;
 
  }
 
  void StopTracing(std::unique_ptr\<perfetto::TracingSession\>
  tracing_session)
 
  {
 
  // Make sure the last event is closed for this example.
 
  perfetto::TrackEvent::Flush();
 
  // Stop tracing and read the trace data.
 
  tracing_session-
 
  \>StopBlocking();
 
  std::vector\<char\> trace_data(tracing_session-
 
  \>ReadTraceBlocking());
 
  // Write the result into a file.
 
  // Note: To save memory with longer traces, you can tell Perfetto to
  write
 
  // directly into a file by passing a file descriptor into Setup()
  above.
 
  std::ofstream output;
 
  output.open("example.pftrace", std::ios::out \| std::ios::binary);
 
  output.write(&trace_data\[0\], std::streamsize(trace_data.size()));
 
  output.close();
 
  PERFETTO_LOG(
 
  "Trace written in example.pftrace file. To read this trace in
 
  "
 
  "text form, run \`./tools/traceconv text
 
  example.pftrace\`");
 
  }
 
  void DrawPlayer(int player_number)
 
  {
 
  TRACE_EVENT("rendering", "DrawPlayer", "player_number",
  player_number);
 
  // Sleep to simulate a long computation.
 
  std::this_thread::sleep_for(std::chrono::milliseconds(500));
 
  }
 
  void DrawGame()
 
  {
 
  // This is an example of an unscoped slice, which begins and ends at
  specific
 
  // points (instead of at the end of the current block scope).
 
  TRACE_EVENT_BEGIN("rendering", "DrawGame"); DrawPlayer(1);
 
  DrawPlayer(2); TRACE_EVENT_END("rendering");
 
  }
 
  int main(int, const char\*\*)
 
  {
 
  InitializePerfetto(); auto tracing_session =
 
  StartTracing();
 
  // Give a custom name for the traced process.
 
  perfetto::ProcessTrack process_track =
  perfetto::ProcessTrack::Current();
 
  perfetto::protos::gen::TrackDescriptor desc =
  process_track.Serialize();
 
  desc.mutable_process()-
 
  \>set_process_name("Example");
  perfetto::TrackEvent::SetTrackDescriptor(process_track,
 
  desc);
 
  // Simulate some work that emits trace events.
 
  DrawGame();
 
  StopTracing(std::move(tracing_session)); return

Append File

# Glossary

## Append File

  Append files are files that append build information to a recipe file.
  Information in append files overrides the information in the
  similarly-named recipe file. Append files use the *.bbappend* filename
  suffix.

## Binary Package

  A binary package is a collection of related files, and is the most
  common artifact that a recipe produces. A package contains binary
  files intended for population directly on a target root file system,
  it may also contain documentation, debug files, and development files
  such as headers and libraries.

## BitBake

  BitBake is the build engine that builds an Innexis Linux distribution.
  It is responsible for parsing the metadata, generating a list of tasks
  from it, and then executing those tasks.

## Board Support Package

  The Innexis Linux support code for a given machine. The BSP layer
  contains the recipes and configuration files needed in building
  software to run on the target machine.

## Class

  Classes are files that provide for logic encapsulation and inheritance
  allowing commonly used instructions to be defined once and easily used
  in multiple recipes. Class files end with the *.bbclass* filename
  extension.

## Configuration File

  Configuration information in various *.conf* files provides global
  definitions of variables. The configuration files in the project
  directory drive the key characteristics of the build, binding together
  machine, distribution, and many other key characteristics of the
  entire build. Machine configuration files define variables for
  specific hardware and are only used when building for that target.
  Configuration files end with a *.conf* filename extension. The
  *conf/local.conf* file is the default file for you to place your
  configuration.

## Image

  An image is the result produced when BitBake processes a given
  collection of recipes and related metadata. Images are the binary
  output that runs on specific hardware and for specific use cases.
 
  Layer

## Layer

  A set of metadata including recipes, configuration and class files. A
  layer can extend or override existing functionality, provide
  additional software support for an image type, add a board support
  package (BSP) for additional hardware, or even represent a new image
  type.

## Machine

  The hardware on which the Innexis Linux runs.

## Metadata

  The files that BitBake parses when building an image. Metadata
  includes recipes, classes, and configuration files.

## Package Group

  Arbitrary groups of software recipes. For example, a package group
  could contain the recipes for a company’s proprietary or value-add
  software. A package group is really just another recipe that ends with
  the *.bb* filename extension.

## Project

  This term describes the configuration for building a single custom
  hardware platform and any build outputs.

## Recipe

  A BitBake recipe is a set of instructions for building a related group
  of packages. Recipe metadata describes what tasks need to be performed
  to build an output object, such as a library or an application. These
  tasks include retrieving source code, applying patches, providing
  additional files, compilation, installation, and generating the final
  binary packages. Recipes also describe dependencies for other recipes.
  Recipes use the *.bb* file extension.

## Yocto Project

  The Yocto Project is an open source project that provides a foundation
  for creating an embedded Linux distribution.
