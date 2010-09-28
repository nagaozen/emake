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

> Note: Properties between _italic_ are optional.

    {
        db: {
            connection: "Provider=SQLOLEDB;Database ..."
        },
        dot_net: {
            _namespace: "Namespace",_
            version: 3.5
        },
        properties: {
            num_id: {
                primary_key: true,
                indexed: true,
                type: "Number",
                props: {
                    documentation: "...",
                    _max: 0,_
                    _min: 1024,_
                    _db_type: "int",_
                    _orm_type: "int"_
                }
            },
            alpha_id: {
                _primary_key: false,_
                indexed: true,
                type: "Text",
                props: {
                    documentation: "...",
                    _length: 32,_
                    _default: "default",_
                    _validation: /[A-Za-z]+/gi,_
                    _mask: "###.###.###-##",_
                    _db_type: "int",_
                    _orm_type: "int"_
                }
            },
            name: {
                .
                .
                .
            }
            .
            .
            .
        }
    }
