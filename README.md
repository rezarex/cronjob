# Dowell Opensource License Compatibility Library

## Version 0.1.0

## Description

The DoWell Legalzard Package provides a seamless interface to the Legalzard API powered
by [DoWell UX Living Lab](https://uxlivinglab.com/en/).

The Legalzard API provides access to a wide range of legal information and resources. It allows developers to retrieve
information about software licenses, legal documents, legal entities, check license compatibility, and more. The API
aims to facilitate the integration of legal information into applications, websites, or other software systems.

## Installation

Download or clone the project
from [github](https://github.com/DoWellLabs/Opensource-License-Compatibility/tree/legalzard-Dennis) to the root of your
project.

## Usage

Import the package

```python
from legalzard import Legalzard
```

Create an instance of the API. You use this instance to access all the package-API methods

```python
license = Legalzard(api_key='YOUR-VALID-API-KEY')
```

### Features

This library offers all the features through the Legalzard API

1. Creating Licenses
   Use the method ```get_all```
   Get all licenses submitted.
   The method returns a response body with two parameters, ```isSucsess```, a boolean showing retrieval status
   and ```data```, a list of licenses.

2. Retrieving all licenses
   Create a license by adding all the fields required by using the ```create``` method which accepts one argument in the
   form of a dictionary. This argument contains all the license information to be created.

3. Retrieving a single license
   Retrieve license information using an ID by using the method ```retrieve``` and passing an Id. The response is
   similar to the ```get_all``` method but the list of of licenses only contains a single license.
4. Updating a license
   Use the ```update``` method. This method updates the license information stored on the database. It accepts two
   arguments, ```id``` and ```license``` object as a dictionary similar to what the ```create``` method accepts.
5. Deleting a license
   Using the ```delete``` method pass an ```id``` and to remove license.
6. Searching for a license
   The API the feature of search for licenses containing a specific phrase. The method accepts a ```search_term```
   argument and returns a response object similar to the ```get_all``` method with list of matching licenses.
7. Retrieving license compatibility.
   Use the ```check_compatibility``` method to check the level of compatibility of two licenses.
   The method accepts a ```comparison_data``` dictionary.
8. Check Comparison History
   Get the comparison history by user using the ```get_compatibility_history``` method that accepts two
   arguments, ```organization_id``` and ```user_id```. The response object contains a list of comparison history
   objects.pip

## Legalzard

- Detailed API information on the [Legalzard API](https://documenter.getpostman.com/view/22392526/2s93mBvyQx)

## Configuration

- The Package requires a valid API key for authentication.

## Dependecies

- requests : Required to make HTTP requests
- json : Require to parse data as JSON objects

## Library Reference

#### Methods

- ```__init__(api_key)``` Initializes the package
- ```get_all()``` Retrieves all of the licenses
- ```create(license: dict)``` Creates a license in the databases. See examples for parameters
- ```retrieve(event_id)``` Fetch license information by ```ID```
- ```update(event_id: str, license: dict)``` Updates an already existing license by receiving its ```ID``` and new
  license information
- ```delete(event_id: str)``` Deletes a license by ```ID```
- ```search(search_term: str)``` Find a license by passing a phrase within the license
- ```check_compatibility(comparison_data: dict)``` Check the compatibility of two licenses by passing a dictionary with
  the license information. See data exmples for parameters.
- ```get_compatibility_history(organization_id: str = None, user_id: str = None)``` Retrieves compatibility check
  history. It receives to optional parameters ```organization_id``` and ```user_id```.

#### Examples

Usage Examples

```python
from legalzard import Legalzard

license = Legalzard(api_key='0138f2e5-acad-4493-ade1-5ad4b3b4836b')

# Get licenses
all = license.get_all()

# Search License
srch = license.search('personal info')

```

Data Examples

- License creation parameters
   ```json
  {
                "license_name": "Test & Sample",
                "license_tags": [],
                "version": "No Version",
                "type_of_license": "PERMISSIVE",
                "short_description": "You can copy,modify and distribute this license as long as you fulfill license requirements.",
                "description": "The SFL (Standard Function Library) from iMatix is a portable function library for C/C++ programs.The SFL is written in ANSI C and has been ported to MS-DOS, Windows, OS/2, Linux and other UNIX systems and Digital OpenVMS. It comes with complete sources and documentation in HTML. The SFL is free software that you may use and distribute for private or commercial purposes according to license agreement.",
                "disclaimer": "Copyright © 1991-2000 iMatix Corporation.",
                "risk_for_choosing_license": "This license places a lot of conditions on use and distribution of it.",
                "limitation_of_liability": "In no event and under no legal theory, whether in tort (including negligence), contract, or otherwise, unless required by applicable law (such as deliberate and grossly negligent acts) or agreed to in writing, shall any Contributor be liable to You for damages, including any direct, indirect, special, incidental, or consequential damages of any character arising as a result of this License or out of the use or inability to use the Work (including but not limited to damages for loss of goodwill, work stoppage, computer failure or malfunction, or any and all other commercial damages or losses), even if such Contributor has been advised of the possibility of such damages.",
                "license_url": "https://spdx.org/licenses/iMatix.html",
                "logo_detail": {
                    "filename": "img_02c8ccb5-3ffb-4737-83db-effb3da529ed.png",
                    "actual_filename": "Logo.png",
                    "file_extension": "png",
                    "url": "https://100080.pythonanywhere.com/media/img/img_02c8ccb5-3ffb-4737-83db-effb3da529ed.png"
                },
                "recommendation": "",
                "is_active": false,
                "permissions": [
                    {
                        "action": "Patent Use",
                        "permission": "No",
                        "has_other_condition": false
                    },
                    {
                        "action": "Patent Grant",
                        "permission": "No",
                        "has_other_condition": false
                    }
                ],
                "conditions": [
                    {
                        "action": "Disclose Source Code",
                        "permission": "No",
                        "has_other_condition": false
                    },
                    {
                        "action": "Network Use is for Distribution",
                        "permission": "No",
                        "has_other_condition": false
                    },
                    {
                        "action": "Release Under Same License",
                        "permission": "Yes",
                        "has_other_condition": false
                    },
                    {
                        "action": "State Changes",
                        "permission": "Yes",
                        "has_other_condition": false
                    },
                    {
                        "action": "Code can be used in closed source project",
                        "permission": "No",
                        "has_other_condition": false
                    },
                    {
                        "action": "Copied",
                        "permission": "Yes",
                        "has_other_condition": false
                    },
                    {
                        "action": "Distributed",
                        "permission": "Yes",
                        "has_other_condition": true
                    },
                    {
                        "action": "Reproduced",
                        "permission": "Yes",
                        "has_other_condition": false
                    },
                    {
                        "action": "Modified",
                        "permission": "Yes",
                        "has_other_condition": true
                    },
                    {
                        "action": "Commercial Used",
                        "permission": "Yes",
                        "has_other_condition": false
                    }
                ],
                "limitations": [
                    {
                        "action": "Liability",
                        "permission": "No",
                        "has_other_condition": false
                    },
                    {
                        "action": "Warranty",
                        "permission": "No",
                        "has_other_condition": false
                    },
                    {
                        "action": "Trademark use",
                        "permission": "No",
                        "has_other_condition": false
                    },
                    {
                        "action": "Redistribution",
                        "permission": "Yes",
                        "has_other_condition": true
                    }
                ],
                "references": [],
                "laws": "Not Fixed",
                "sources": [
                    {
                        "action": "FSF Approved",
                        "permission": "Yes"
                    },
                    {
                        "action": "OSI Approved",
                        "permission": "No"
                    }
                ],
                "must_includes": [
                    {
                        "action": "License",
                        "permission": "Yes"
                    },
                    {
                        "action": "Copyright Notice",
                        "permission": "Yes"
                    }
                ]
            }
   ```
- Compatibility Check parameters
   ```json
    {
    "license_event_id_one": "FB1010000000167238702450728865",
    "license_event_id_two": "FB1010000000167247184554419413",
    "user_id": 609,
    "organization_id": "63cf89a0dcc2a171957b290b"
    }
    ```

## License

- Apache License 2.0