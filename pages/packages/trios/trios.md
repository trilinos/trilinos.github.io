---
title: Trios
permalink: trios.html
folder: packages
---

Welcome to the Trios Home

The Trios (Trilinos I/O Support) package provides libraries to support the development of distributed data services on HPC platforms. Simply put, a data service is a separate (possibly parallel) application that performs data-processingoperations on behalf of an actively running scientific application. A data service allows the application to “offload” operations that could potentially hinder the scalability of the main parallel application. Use cases include, for example, include data staging for bursty I/O operations, real-time debugging support, statistics gathering, uncertaintly quantification, data analysis, and visualization.

## Nessie

The primary library to support data services is the Network Scalable Service Interface (Nessie). Nessie is a framework for developing parallel client-server data services HPC system.

Nessie has the following features to address scalability, efficient data movement, and support for heterogeneous architectures:

*   asynchronous interfaces,
*   remote-direct-memory-addressing (RDMA),
*   server-directed data movement,
*   separate channels for control and data movement,
*   XDR encoding of control messages to support services on heterogenous systems.

The Nessie API follows a remote procedure call (RPC) model, where the client (i.e., the scientific ap- plication) tells the server(s) to execute a function on its behalf. Nessie relies on client and server stub functions to encode/decode (i.e., marshal) procedure call parameters to/from a machine-independent format.

## NNTI

The Nessie Network Transport Interface (NNTI) provides a portable, lightweight, abstraction for RDMA operations on common HPC systems. Our current implementation includes support for the Cray Seastar, InfiniBand, Cray Gemini, and IBM DCMF interconnects. The APIs include commands to open and close the interface, connect and disconnect to a peer, register and deregister memory buffers, and finally asynchronously transport (through put, get, and wait commands) bulk data. The NNTI library sits below the Nessie RPC library to enable portability across HPC interconnects.

## Example Data Services

*   Xfer service: Example that transfers data to/from a data service. Used to test interface.
*   PnetCDF staging service: A replacement for PnetCDF that stages writes. Used to demonstrate a burst buffer.
*   SQL service (not in repo): Provides an extension of VTKSQL that uses a service as a remote proxy for an ODBC database.
*   Graph IO service (not in repo): Service for writing graphs to a remote ODBC database.
*   CTH fragment detection (not in repo): Performs in-transit fragment detection for CTH shock physics code. systems.
*   Kelpie Key/Value Store (not in repo): Provides an in-memory key/value store.

![Image nessie](images/nessie.png)

What is Trios useful for?

Trios is useful for developing parallel distributed data services.

Who is using Trios?

Trios has been used for a number of projects at Sandia National Laboratories. The Nessie libraries originated as part of the lightweight file system project. It was then used for an LDRD to explore staging techniques to offset the impact of bursty I/O operations. Nessie has also been used at Sandia to demonstrate remote database functionality, real-time network analysis, interactive visualization, and in-transit fragment detection for shock physics. NNTI is also being used by ORNL and GA Tech to provide networking capabilities for the ADIOS I/O libraries.