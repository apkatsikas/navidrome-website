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

DId not observe much difference between the two data-wise. ffmpeg had codec info?

parsed about 10 folders:

using taglib parsing took took 1.902329ms

using ffmpeg parsing took took 361.204136ms

prob wont make a big difference to most people?
