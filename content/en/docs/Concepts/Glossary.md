---
title: "Glossary"
linkTitle: "Glossary"
date: 2020-04-24
weight: 3
description: >
  A glossary of common terms used in the context of OLM.
---

### Bundle

A collection of manifests and metadata that describe a version of an operator that can be installed to a Kubernetes cluster and managed by OLM.

### Bundle Image

A container image that holds a single [bundle](#Bundle).

### Catalog

A collection of [bundles](#Bundle) consisting of any number of different operators and versions.

### Package

A set of [bundles](#Bundle) within a [catalog](#Catalog) that correspond to unique versions of the same operator.

### Channel

A sequence of [bundles](#Bundle) belonging to a [package](#Package) that representing an ordered stream of updates for an operator.

### Channel Head

The latest [bundle](#Bundle) in a [channel](#Channel).

### Catalog Image

A catalog image is a containerized datastore that describes a set of operator and update metadata that can be installed onto a cluster via OLM.

**Aliases**: OPM Index

### Dependency

An Operator may have a dependency on another Operator being present in the cluster. For example, the Vault Operator has a dependency on the Etcd Operator for its data persistence layer. OLM resolves these dependencies by ensuring all specified versions of Operators and CRDs are installed on the cluster during the installation phase. This dependency is resolved by finding and installing an Operator in a Catalog that satisfies the required CRD API, and not related to [packages](#Packages)/[bundles](#Bundles).

**Aliases**: Operator Dependency, GVK Dependency, API Dependency, Required CRD

### Index

The Index refers to an image of a database (a database snapshot) that contains information about Operator bundles including CSVs, CRDs, etc of all versions. This index can host a history of used operators on a cluster and be maintained by adding or removing operators.

**Aliases**: Registry DB, Catalog DB, OPM registry


### Registry

A database which stores [Bundle Images](#Bundle-Image) of Operators, each with all of its latest/historical versions in all [channels](#Channel).

### Upgrade Graph

The graph created by 
An upgrade graph links [CSVs](./custom-resource-definitions/cluster-service-version) together, similar to the upgrade graph of any other packaged software. Operators can be installed sequentially, or certain versions can be skipped. The update graph is expected to grow only at the head with newer versions being added. This is automatically resolved as part 

