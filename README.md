eMake
=====

eMake is a code generation tool which helps the programmer to create the basic 
Model structure used by the Evolved Team. It should accelerate the process
behind coding the following layers: Data Persistance, Model Objects,
Object-Relational Mapping, Data Input/Validation and Documentation usually 
required by all our projects. This means eMake should handle:

1. MSSQL
    - Table
    - Storage Procedures
2. .NET
    - C# Interop ActiveX DLL
    - Web Service
3. WEB
    - ASP Class
    - HTML Form
    - ASP Process
    - Validations
4. Documentation
    - Natural Docs

Usage
-----

    > cscript emake Model.emk

Type definition
---------------

- Evolved.Text
- Evolved.Number
- Evolved.Boolean
- Evolved.Date
- Evolved.Area
- Evolved.Select
- Evolved.Radios
- Evolved.Checkboxes

DB Field Prototype
------------------

    {
        primary_key: false,
        foreign_key: null,
        indexed: false
    }

Example: User.emk
-----------------

> Note: Properties between [] are optional.

    {
        db: {
            connection: "Provider=SQLOLEDB;Database ..."
        },
        dot_net: {
            [namespace: "Namespace",]
            version: 3.5
        },
        properties: {
            num_id: {
                primary_key: true,
                indexed: true,
                type: (new Evolved.Number(documentation[, max, min, db_type, orm_type]))
            },
            alpha_id: {
                [primary_key: false,]
                indexed: true,
                type: (new Evolved.Text(documentation[, length, default, validation, mask, db_type, orm_type]))
            },
            name: {
                type: (new Evolved.Text(documentation[, length, default, validation, mask, db_type, orm_type]))
            }
            .
            .
            .
        }
    }
