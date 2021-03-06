---
layout: page
title: IPv4 Network Configurator Tutorial
tutorial: Configurator
---

This tutorial shows how to configure IP addresses and routing tables (that
is, achieve static autoconfiguration) in wired and wireless networks
in the INET Framework using the `Ipv4NetworkConfigurator` module.

In INET simulations, configurator modules are commonly used for assigning
IP addresses to network nodes and for setting up their routing tables.
There are various configurators modules in INET; this tutorial covers the
most generic and most featureful one, `Ipv4NetworkConfigurator`.
`Ipv4NetworkConfigurator` supports automatic and manual network configuration,
and their combinations. By default, the configuration is fully automatic.
The user can also specify parts (or all) of the configuration manually,
and the rest will be configured automatically by the configurator.
The configurator's various features can be turned on and off with parameters.
The details of the configuration, such as IP addresses and routes, can be specified
in an XML file.

<!--
The tutorial itself is organized into several steps, each one demonstrating
a different feature or use case for the network configurator.

Essentially, the configurator module simulates a real life network administrator.
The configurator assigns IP addresses to interfaces, and sets up static routing in IPv4 networks.
It doesn't configure IP addresses and routes directly, but stores the configuration in its internal data structures.
Network nodes contain an instance of `Ipv4NodeConfigurator`, which configures the corresponding node's interface table and routing table based on information contained in the global `Ipv4NetworkConfigurator` module.
The purpose of this design is that when router reboots after a simulated failure or shutdown,
this way it can pull its IPv4 configuration from the configurator module, and restore
its IPv4 addresses and routing table.
-->

This is an advanced tutorial, and it assumes that you are familiar with creating
and running simulations in OMNeT++ and INET. If you aren't, you can check out
the <a href="https://docs.omnetpp.org/tutorials/tictoc/"
target="_blank">TicToc Tutorial</a> to get started with using OMNeT++.

If you need more information at any time, feel free to refer to the OMNeT++ and
INET documentation:

- <a href="https://omnetpp.org/doc/omnetpp/manual/usman.html" target="_blank">OMNeT++ User Manual</a>
- <a href="https://omnetpp.org/doc/omnetpp/api/index.html" target="_blank">OMNeT++ API Reference</a>
- <a href="https://omnetpp.org/doc/inet/api-current/inet-manual-draft.pdf" target="_blank">INET Manual draft</a>
- <a href="https://omnetpp.org/doc/inet/api-current/neddoc/index.html" target="_blank">INET Reference</a>
