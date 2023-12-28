---
title: Extractors
linkTitle: Extractors
date: 2023-12-27
weight: 100
description: >
  Information on the extractors used for metadata scanning
---

## Scanner
Metadata is derived from audio files via Scanner. There are two types of Extractors for the scanner, using TagLib or ffmpeg.

Can be configured via [configuration options](/docs/usage/configuration-options/#advanced-configuration) using `Scanner.Extractor`.

## TagLib
TagLib is default.

## Ffmpeg
Ffmpeg supports .tak, TagLib does not.
