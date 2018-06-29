# SMNS - Spec for Modelling NoSQL Schemas

## Table of Contents
  1. Introduction
  2. Why this document?
  3. Spec
    a. Models
    b. Types
    c. References
    d. Subdocuments
    e. Instance methods
    f. Stored Procedures
  4. Changelog
  5. Future versions

## Introduction
This document is a specification for modelling NoSQL Schemas. While MongoDB/BSON is assumed, this specification is quite generic and may therfore be applicable to other database types or engines, such as XML. The rule of thumb for modelling is: **if your database engine or data modeller does not support it, don't model it**. Edits for this specification can be proposed by making a pull request.

## Why this document?
Models can be a very important part of a project's documentation. This includes all kinds of UML diagrams like Class and Sequence Diagrams, but can also contain Entity Relationship Diagrams that describe the structure of the used database. As opposed to relational databases, NoSQL databases do not natively enforce a specific model. That however, does not mean that a NoSQL database can not comply to a schema specified by the database engine or data modeller, or that may have one indirectly because the software that uses it was built that way. The goal of this document is to define a specification for modelling NoSQL databases that have a basic structure as an alternative to Entity Relationship Diagrams.

## Spec

### Models
### Types
### References
### Subdocuments
### Instance Methods
### Stored Procedures

## Changelog
|Version|Comments|Author|Date|
|-------|--------|------|----|
|0.0.1|Wrote the introduction and table of contents|David Doorn (thedjdoorn)|06/29/18|

## Future versions
