# Flexible Concatenated Archive (FCA)

A flexible container format for embedding multiple files within a single archive file. The FCA format supports version-specific header formats, allowing for extensibility and future enhancements.

![](/fca-icon-256.png)

## Purpose

The Flexible Concatenated Archive (FCA) format is designed to efficiently store and organize multiple embedded files within a single archive. It is optimized for use on extremely low-resource devices, making it ideal for embedded systems, IoT devices, and other constrained environments where memory and processing power are limited.

The format is particularly well-suited for storing collections of related files such as:
- Amiibo dumps (v2 and v3 formats)
- Skylander dumps
- Destiny Infinity dumps
- Lego Dimensions dumps
- Other binary file collections

## Design Goals

The FCA format was designed with the following principles in mind:

- **Simple** - The format is straightforward and easy to understand, with a clear structure that can be implemented with minimal code complexity.

- **Efficient** - The format wastes as little space as possible, avoiding unnecessary padding or overhead. Every byte serves a purpose.

- **Flexible** - The format allows room for growth and future expansion through versioning and dynamic header sizes. Different file types can be stored with type-specific metadata.

- **Identifiable** - The format uses a dedicated file extension (`.fca`) and magic bytes ("FCA") at the beginning of each file for easy identification.

## Overview

FCA files (`.fca` extension) consist of:
- A global header with magic bytes "FCA" and a version number
- One or more embedded files, each with version-dependent headers containing file type and metadata

See [SPEC.md](SPEC.md) for the complete format specification.
