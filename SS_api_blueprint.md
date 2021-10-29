FORMAT: 1A
HOST: https://selfservice-3.rightscale.com

# RightScale Self-Service API
The RightScale Self-Service API lets you interact with cloud resources at the application level, instead of the component level. Isn't that cool?

# Group Applications
Resources that represent the Applications that are available in the Catalog

## Applications Collection [/catalogs/{catalog_id}/applications]
+ Parameters
    + catalog_id (required, string, `12345`) ... ID of the Catalog

### List all Applications [GET]
Get the list of applications available in the specified Catalog

+ Response 200 (applications/json)

    JSON representation of the Applications in the specified Catalog

    + Body

            [{
              "kind": "Teller",
              "id": "subjects",
              "name": "rankle",
              "href": "elitist",
              "short_description": "mynahes",
              "long_description": "desolates",
              "parameters": [
                {
                  "name": "pervades",
                  "label": "Wilfredo",
                  "category": "key",
                  "description": "stringently",
                  "no_echo": true,
                  "min_length": 855,
                  "max_length": 153,
                  "min_value": 106,
                  "max_value": 126,
                  "allowed_pattern": "escalator",
                  "allowed_values": [
                    "An Object",
                    "An Object",
                    "An Object"
                  ],
                  "constraint_description": "kits",
                  "default": "An Object",
                  "index": 151,
                  "type": "number"
                },
                {
                  "name": "transatlantic",
                  "label": "Ishmael",
                  "category": "Rosanne",
                  "description": "allowed",
                  "no_echo": false,
                  "min_length": 628,
                  "max_length": 96,
                  "min_value": 398,
                  "max_value": 793,
                  "allowed_pattern": "inequalities",
                  "allowed_values": [
                    "An Object",
                    "An Object",
                    "An Object"
                  ],
                  "constraint_description": "retarded",
                  "default": "An Object",
                  "index": 490,
                  "type": "list"
                }
              ],
              "template": {
                "href": "excavation"
              },
              "author": {
                "id": 478,
                "name": "practicing",
                "email": "descrying"
              },
              "timestamps": {
                "created_at": "2013-06-17T00:00:00+00:00",
                "updated_at": "2013-01-26T00:00:00+00:00"
              }
            }]

### Create Application [POST]
Add a new Application to the Catalog

+ Request (application/json)

        {
          "name": "My new app",
          "short_description": "short",
          "source": "big ole json",
          "template_href": "href of the template",
          "long_description": "longer one"
        }

+ Response 202 (text/plain)

    The Application was accepted into the Catalog

    + Body

+ Response 409 

    The Application already exists in the Catalog

    + Body

### Delete Applications [DELETE]
Delete multiple Applications from the Catalog

+ Request (application/json)

        {
          "ids": "[123,456,789]"
        }

+ Response 200

## Catalog Applications [/catalogs/{catalog_id}/applications/{id}{?view}]
+ Parameters
    + catalog_id (required, string, `12345`) ... ID of the Catalog
    + id (required, string, `67890`) ... ID of the Application

### Show Application Details [GET]
Get details for a particular Application

+ Parameters
    + view (optional, string `[default,expanded]`) ... Show either the default or expanded view of data

+ Response 200
    
    + Body

            {
              "kind": "Teller",
              "id": "subjects",
              "name": "rankle",
              "href": "elitist",
              "short_description": "mynahes",
              "long_description": "desolates",
              "parameters": [
                {
                  "name": "pervades",
                  "label": "Wilfredo",
                  "category": "key",
                  "description": "stringently",
                  "no_echo": true,
                  "min_length": 855,
                  "max_length": 153,
                  "min_value": 106,
                  "max_value": 126,
                  "allowed_pattern": "escalator",
                  "allowed_values": [
                    "An Object",
                    "An Object",
                    "An Object"
                  ],
                  "constraint_description": "kits",
                  "default": "An Object",
                  "index": 151,
                  "type": "number"
                },
                {
                  "name": "transatlantic",
                  "label": "Ishmael",
                  "category": "Rosanne",
                  "description": "allowed",
                  "no_echo": false,
                  "min_length": 628,
                  "max_length": 96,
                  "min_value": 398,
                  "max_value": 793,
                  "allowed_pattern": "inequalities",
                  "allowed_values": [
                    "An Object",
                    "An Object",
                    "An Object"
                  ],
                  "constraint_description": "retarded",
                  "default": "An Object",
                  "index": 490,
                  "type": "list"
                }
              ],
              "template": {
                "href": "excavation"
              },
              "author": {
                "id": 478,
                "name": "practicing",
                "email": "descrying"
              },
              "timestamps": {
                "created_at": "2013-06-17T00:00:00+00:00",
                "updated_at": "2013-01-26T00:00:00+00:00"
              }
            }

### Update Application [PUT]

+ Response 200

### Delete Application [DELETE]

+ Response 200

# Group AccountSettings
## AccountSettings Collection [/account/:account_id/settings]
+ Parameters
    + account_id (required, string, `12345`) ... ID of the account

### List Account Settings [GET]

+ Response 200
    
    + Body

            [{
              "name": "hangnail",
              "value": "catalyzes",
              "group_name": "abrasive",
              "created_by": {
                "id": 100,
                "name": "intrinsic",
                "email": "voodooing"
              },
              "created_at": "2014-03-22T00:00:00+00:00",
              "updated_at": "2013-10-29T00:00:00+00:00"
            }]

### Create Account Setting [POST]

+ Request (application/json)

        {
          "name": "My new app",
          "value": "short",
          "group_name": "big ole json",
        }

+ Response 202

## Account Settings [/account/:account_id/settings/:name]
+ Parameters
    + account_id (required, string, `12345`) ... ID of the account
    + name (required, string, `setting_1`) ... name of the AccountSetting

### Show AccountSetting Details [GET]
+ Response 200
    
    + Body

            {
              "name": "hangnail",
              "value": "catalyzes",
              "group_name": "abrasive",
              "created_by": {
                "id": 100,
                "name": "intrinsic",
                "email": "voodooing"
              },
              "created_at": "2014-03-22T00:00:00+00:00",
              "updated_at": "2013-10-29T00:00:00+00:00"
            }

### Delete AccountSetting [DELETE]

+ Response 200
