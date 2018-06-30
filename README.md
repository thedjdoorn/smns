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
A model is a part of your schema that is the blueprint for an entity. A model can consist of fields, relationships to other models and/or methods. A field is a property of the model with a type and a value. 

If a field is used as a unique identifier, it is preceeded by a pound sign (#). If not, a hyphen (-) is used. Please note the following:
* A model can only have **one** unique identifier
* Only use the pound sign notation if the entity is identified by that field by the DBMS OR
* Only use the pound sign notation if the value of that field is used to refer to the entity
* If a unique identifier is assigned automatically by the DBMS, you are not obligated to include that in your model

![An example of a model describing a Car](https://raw.githubusercontent.com/thedjdoorn/smns/master/car-Model.png)

### Types
A field can have a type. Since this spec was primarily written for MongoDB, the type conventions will look a little bit like JavaScript types. That means that primitive JS types (boolean, null, undefined, number, string, symbol and object) will all be written in lowercase letters, whereas everything else (Date, Map) will be written in Pascal case.  
Generic types are modeled by putting the type variable in angle brackets behind the generic type. An array of numbers would look like *Array\<number>*.

### References
An entity can reference another entity by putting the unique identifier in one of its fields. This relationship is modeled by putting an asterisk(\*) after the type and by connecting the two models with a generic connector.

![The car has an owner of type Person, the owner field contains the id of the corresponding Person](https://raw.githubusercontent.com/thedjdoorn/smns/master/car-person-relationship.png)

### Subdocuments
An entity can contain one or multiple subdocuments that all comply to the same structure. As opposed to entity references, subdocuments are part of the parent entity and only exist in the parent entity's context. A subdocument relationship is modeled by following up the type with an amperzand (&) and by connecting the models with an arrow pointing from the parent model to the child model.

![A dealership has an array of cars that only exist in the context of the dealership](https://raw.githubusercontent.com/thedjdoorn/smns/master/subdocument-relationship.png)

### Instance Methods
### Stored Procedures

## Changelog
|Version|Comments|Author|Date|
|-------|--------|------|----|
|0.0.1|Wrote the introduction and table of contents|David Doorn (thedjdoorn)|06/29/18|
|0.5.1|Wrote the specification for models, types and relations| David Doorn (thedjdoorn)|06/30/18|

## Future versions
