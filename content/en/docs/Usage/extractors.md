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

DId not observe much difference between the two data-wise. ffmpeg had codec info? doesnt make it to DB tho i dont think...

parsed about 10 folders:

using taglib parsing took took 1.902329ms

using ffmpeg parsing took took 361.204136ms

prob wont make a big difference to most people?

".mp3":  {typ: "audio/mpeg"}, - TESTED
	".ogg":  {typ: "audio/ogg"}, - TESTED
	".oga":  {typ: "audio/ogg"}, - TESTED
	".opus": {typ: "audio/ogg"}, - TESTED
	".aac":  {typ: "audio/mp4"}, - TESTED FAILED - ffmpeg WORKS - tried Title
	".alac": {typ: "audio/mp4", lossless: true}, WEIRD - TESTED but alac is not typically the extension type for this? - ffmpeg worked when i just changed extension, taglib did not. taglib only worked when extension was .m4a. ffmpeg wont let you create a .alac file
	".m4a":  {typ: "audio/mp4"}, - TESTED
	".m4b":  {typ: "audio/mp4"}, - TESTED
	".flac": {typ: "audio/flac", lossless: true}, - TESTED
	".wav":  {typ: "audio/x-wav", lossless: true}, - TESTED
	".wma":  {typ: "audio/x-ms-wma"}, - TESTED
	".ape":  {typ: "audio/x-monkeys-audio", lossless: true}, - TESTED
	".mpc":  {typ: "audio/x-musepack"}, - TESTED
	".shn":  {typ: "audio/x-shn", lossless: true}, - FAILED couldnt create, couldnt scan in ffmpeg or taglib, couldnt inspect in picard
	".aif":  {typ: "audio/x-aiff"}, - TESTED FAILED - ffmpeg WORKS
	".aiff": {typ: "audio/x-aiff"}, - TESTED
	".m3u":  {typ: "audio/x-mpegurl"}, N/A?
	".pls":  {typ: "audio/x-scpls"}, N/A?
	".dsf":  {typ: "audio/dsd", lossless: true}, - TESTED FAILED - ffmpeg WORKS
	".wv":   {typ: "audio/x-wavpack", lossless: true}, - TESTED
	".wvp":  {typ: "audio/x-wavpack", lossless: true}, WEIRD - TESTED ffmpeg worked when i just changed extension, taglib did not. taglib only worked when extension was .wv. ffmpeg wont let you create a .wvp file
	".tak":  {typ: "audio/tak", lossless: true}, - TESTED FAILED - ffmpeg WORKS
	".mka":  {typ: "audio/x-matroska"}, - TESTED FAILED - ffmpeg WORKS
  