# Technical Reference and Resource Directory for VFX Pipeline R&D

A curated, production-ready directory of standardized open-source scene assets,
multi-channel render passes, deep EXR datasets, camera raw footage, and core
utility tools for VFX pipeline research, development, and benchmarking.

Any contribution is welcome.

# Summary

- [Technical Reference and Resource Directory for VFX Pipeline R&D](#technical-reference-and-resource-directory-for-vfx-pipeline-rd)
- [Summary](#summary)
  - [Standard Production Scene Assets and USD/glTF Datasets](#standard-production-scene-assets-and-usdgltf-datasets)
  - [CG Multi-Channel Render Passes and Compositing Sequences](#cg-multi-channel-render-passes-and-compositing-sequences)
  - [Deep EXR Datasets, Toolsets, and Specifications](#deep-exr-datasets-toolsets-and-specifications)
  - [Cinematography Camera Raw Footage](#cinematography-camera-raw-footage)
  - [Pipeline Standards, Color Management, and Math Utilities](#pipeline-standards-color-management-and-math-utilities)
  - [Pipeline Validation, Real-Time VP, and Tracking Toolsets](#pipeline-validation-real-time-vp-and-tracking-toolsets)
  - [Core Specifications Overview](#core-specifications-overview)

## Standard Production Scene Assets and USD/glTF Datasets

These production-grade datasets are useful for evaluating scene graph scale,
validating USD composition schemas, and stress-testing offline and real-time
rendering engines.

* [Disney Moana Island Scene](https://github.com/usd-wg/assets) - USD/OpenVDB, large-scale geometry, procedural content, and volumetric path-tracing tests.
* [Animal Logic ALab Scene](https://dpel.aswf.io/alab/) - 63.4 GB with 4K textures, skeletal animation, fur workflows, and Hydra rendering tests.
* [Intel 4004 Moore Lane](https://dpel.aswf.io/) - Instanced vegetation and light transport sampling diagnostics.
* [Intel Sponza Base Scene](https://www.intel.com/content/www/us/en/content-details/830833/sponza-base-scene.html) - USD/OBJ architecture scene for GI and PBR stress testing.
* [Intel Sponza glTF 2.0](https://github.com/ludicon/sponza-gltf) - Clean real-time glTF package for WebGL/WebGPU PBR testing.
* [Khronos Sponza Atrium](https://github.com/KhronosGroup/glTF-Sample-Assets/blob/main/Models/Sponza/README.md) - Reference for glTF metallic-roughness texture packing and shading behavior.
* [Pixar Standard Scene Sets](https://openusd.org/release/dl_downloads.html) - Lightweight USD samples for syntax and composition validation.
* [Lowe's Open Builder](https://github.com/matiascodesal/awesome-openusd) - CAD-to-USDZ assets for AR and mobile performance validation.
* [Open Chess Set / MaterialX](https://github.com/AcademySoftwareFoundation/MaterialX) - Useful for lookdev exchange and shader/material graph validation.

## CG Multi-Channel Render Passes and Compositing Sequences

Multi-channel EXR sequences with AOVs, LPEs, and Cryptomattes are essential for
ingestion, lookdev, and compositing pipeline validation.

* [Netflix Sole Mates Dataset (ASWF DPEL)](https://github.com/DigitalProductionExampleLibrary/SoleMates) - 61-frame production shot package with 42 render layers and more than 40 diagnostic/lighting passes in ACEScg.
* [Pixar RenderMan Stirling VFX](https://renderman.pixar.com/stirling-vfx) - Lookdev, lighting, and compositing sample project for Maya, RenderMan, and Nuke.
* [RenderMan Tutorials](https://renderman.pixar.com/learn_tutorials) - Supporting learning material for the Stirling workflows.
* [Hollywood Camera Work Tracking Plates](https://www.hollywoodcamerawork.com/tracking-plates.html) - HD green-screen, matchmove, and witness camera footage with related scene data.
* [CGPress Tracking Plate Reference](https://cgpress.org/archives/free_green_screen_and_vfx_plates_for_personal_training.html) - Additional pointer to free training plates.
* [OpenTimelineIO Open Content Examples](https://github.com/darbyjohnston/otio-oc-examples) - Mixed-format footage for editorial and timeline pipeline testing.
* [ASC StEM2 Sample (ASWF DPEL)](https://aswf-dpel-assets.s3.amazonaws.com/asc-stem2/ASC_StEM2_178_UHD_ST2084_1000nits_Rec2020_Stereo_ProRes4444XQ.mov) - UHD reference clip for finishing and playback validation.

## Deep EXR Datasets, Toolsets, and Specifications

Deep images store variable-length per-pixel sample lists (color, opacity,
depth). They are essential for volumetric compositing and deep holdout workflows.

Official reference images and code:

* [OpenEXR](https://github.com/AcademySoftwareFoundation/openexr) - Primary code repository with deep and multipart support.
* [OpenEXR Images - Beachball Sample Preview](https://raw.githubusercontent.com/AcademySoftwareFoundation/openexr-images/main/Beachball/singlepart.0008.jpg) - Reference image asset example.

Common deep EXR production tools:

* [DeepThinner v2.0](https://github.com/bratgot/DeepThinner) - Nuke plugin for deep data reduction via culling, thresholding, and depth-aware merges.
* exrflatten - Command-line deep ID extraction workflow for flat layer outputs.
* [Exr-IO Cryptomatte Guide](https://superrendersfarm.com/article/exr-io-cryptomatte-guide) - Practical workflow reference for channel extraction into Photoshop.
* TinyEXR.NET - Managed .NET wrapper for single-part, tiled, multipart, and deep EXR loading.
* HDR/EXR 360 Viewer (VS Code extension) - In-editor HDR/EXR inspection support.

## Cinematography Camera Raw Footage

Raw camera originals are useful for debayering research, metadata extraction,
ingestion automation, and codec performance testing.

ARRI camera systems (ARRIRAW and Apple ProRes):

* [ARRI Technical Information PDF](https://www.arri.com/resource/blob/31926/fea9a24f3fe7b77d5f83b49700465f76/2025-03-arri-sample-footage-technical-information-data.pdf)
* ARRI sample footage FTP:
  * Server: ftp2.arri.de
  * Username(s): ALEXA, AMIRA
  * Password: samplefootage

RED Digital Cinema (.R3D):

* [RED Downloads](https://www.red.com/downloads)
* [Sample R3D Files](https://www.red.com/sample-r3d-files)

Sony cinematography (16-bit MXF X-OCN):

* Sony Ci platform downloads are commonly used for Venice 2 ingestion tests.

Blackmagic Design (.braw):

* [Blackmagic RAW SDK and Sample Clips](https://www.blackmagicdesign.com/products/blackmagiccinemacamera/gallery)

## Pipeline Standards, Color Management, and Math Utilities

Pipeline foundations depend on reliable open standards for color, volumetrics,
material interchange, and scene data semantics.

* [OpenColorIO Config ACES](https://github.com/AcademySoftwareFoundation/OpenColorIO-Config-ACES) - Official ACES-oriented OCIO config generation workflows.
* [OpenColorIO Config ACES Releases](https://github.com/analogstudio/OpenColorIO-Config-ACES-releases) - Prebuilt and release-oriented config packages.
* [Colour Science OpenColorIO Configs](https://github.com/colour-science/OpenColorIO-Configs) - Community and research OCIO config variants.
* [OpenVDB Downloads](https://www.openvdb.org/download/) - Volumetric model and toolkit resources.
* [OpenVDB Repository](https://github.com/AcademySoftwareFoundation/openvdb) - Core source and integration reference.
* [OpenVDB Bunny Cloud Artifact](https://artifacts.aswf.io/io/aswf/openvdb/models/bunny_cloud.vdb/1.0.0/bunny_cloud.vdb-1.0.0.zip) - Example volumetric validation asset.
* [MaterialX](https://github.com/AcademySoftwareFoundation/MaterialX) - Material graph and lookdev interchange standard.
* [MaterialX Developer Reference](https://materialx.org/DeveloperReference.html) - API and specification details.
* [MaterialX Releases](https://github.com/AcademySoftwareFoundation/MaterialX/releases) - Versioned binaries and source drops.

## Pipeline Validation, Real-Time VP, and Tracking Toolsets

Practical assets and tooling for live-action integration tests, virtual
production sync, and scene validation.

* [Blender Demo Files](https://www.blender.org/download/demo-files/) - Open film assets and lighting testbeds.
* [Blender Downloads](https://www.blender.org/download/) - Main download portal and related production files.
* [Tracking Toolkit for Blender](https://extensions.blender.org/add-ons/tracking-toolkit/) - OpenXR-based motion controller tracking into Blender viewports.

## Core Specifications Overview

* Color spaces: Linear exchange typically uses ACES AP0 (ACES2065-1), while CG rendering and compositing generally use ACES AP1 (ACEScg).
* Deep hashing: Deep ID workflows often use 32-bit or 64-bit unsigned integer channels for object hash storage directly in EXR streams.
* VP phase alignment: LED volume and camera sync commonly relies on sub-frame phase-locking modeled as N times the native camera frame rate.

