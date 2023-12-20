**Note:** This repository is specific to NodeJS.

### Table of Contents

| No. | Questions |
| --- | --------- |
|   | **NodeJS Fundamentals** |
|1  | [What is YAML?](#what-is-yaml) |
|2  | [What is the difference between yaml and JSON?](#difference-between-yaml-json) |
|3  | [Can yaml be used in place of json?](#yaml-in-place-json) |
|4  | [What is the use of anchor and alias in yaml?](#anchor-alias) |
|5  | [YAML datatypes?](#yaml-datatypes) |
|6  | [What will be the value for below line in YAML in JSON?](#yes-true) |
        ---
        Account:
          name: Narayan Sahoo
          inProject: Yes
          projectName: CICD pipeline
|   |     |
| ----   | ----------------     |
|7  | [Can you make this 'yes' or 'No' as string?](#yes-string) |
|8  | [Convert this below json to yaml?](#json-to-yaml) |

        {
            "Routine": {
                "days": [
                {
                    "weekday": {
                    "wakeup": "6:00 AM",
                    "activities": [
                        "workout",
                        "meetings",
                        "work",
                        "sleep"
                    ],
                    "sleeptime": "10:00 PM"
                    }
                }
                ]
            },
            "schedules": {
                "days": {
                "weekend": [
                    {
                    "monday": {
                        "wakeup": "6:00 AM",
                        "activities": [
                        "workout",
                        "meetings",
                        "work",
                        "sleep"
                        ],
                        "sleeptime": "10:00 PM"
                    }
                    },
                    {
                    "tuesday": {
                        "wakeup": "6:00 AM",
                        "activities": [
                        "workout",
                        "meetings",
                        "work",
                        "sleep"
                        ],
                        "sleeptime": "10:00 PM"
                    }
                    },
                    {
                    "wednesday": {
                        "wakeup": "6:00 AM",
                        "activities": [
                        "workout",
                        "meetings",
                        "work",
                        "sleep"
                        ],
                        "sleeptime": "10:00 PM"
                    }
                    },
                    {
                    "thursday": {
                        "wakeup": "6:00 AM",
                        "activities": [
                        "workout",
                        "meetings",
                        "work",
                        "sleep"
                        ],
                        "sleeptime": "10:00 PM"
                    }
                    },
                    {
                    "friday": null,
                    "wakeup": "6:00 AM",
                    "activities": [
                        "workout",
                        "meetings",
                        "work",
                        "sleep"
                    ],
                    "sleeptime": "12:00 AM"
                    }
                ]
                }
            }
        }

|  |   |
| ---- | ----------------  |
|9  | [Can you tell the output from this below code and explain?](#string-output) |
        ---
        Project: CICD
        desc: |
            CICD is need
            to be done
            by YAML
        history: >
            Initially it was
        done manually
        now done by YAML

|  |   |
| ---- | ----------------  |
|10  | [Can you remove the last line break from the above code?](#remove-line-break) |
|11  | [What is KEY-VALUE pairs?](#key-value) |
|12  | [What is Scalers?](#Scalers) |
|13  | [Comment in YAML?](#comment) |



## &nbsp;
## &nbsp;

## Answers

1. ### [What is YAML?](#what-is-yaml)

    YAML is a light-weight, human-readable data-serialization language. It is primarily designed to make the format easy to read while including advanced features.
    YAML stands for “YAML Ain't Markup Language”.

    It is similar to XML and JSON files but uses a more minimalist syntax even while maintaining similar capabilities.
    YAML files are created with extensions “.yaml” or “.yml” . You can use any IDE or text editor to open/create YAML files.
    YAML is similar inline style to JSON (is a superset of JSON).
    It is very easy and simple for represent complex mapping. Due to which it is heavily used in configuration settings.

**[⬆ Back to Top](#table-of-contents)**

2. ### [What is the difference between yaml and JSON?](#difference-between-yaml-json)

    YAML is a super set of JSON which means all the features of JSON can be found in YAML. For example if you compare with
    JavaScript and TypeScript, TypeScript will be YAML and JavaScript will be JSON. 
    **One main difference between yaml and json is in YAML we can have comments where not in JSON**
    Lets look at the below table for to understand the differences

    | JSON | YAMM  | 
    | --- | ------- |
    | Harder to read | Easier to read and understand |
    | Explicit, strict syntax requirements | Minimalist syntax | 
    | Comments are not allowed | Allows comments | 
    | Hierarchy is denoted by using braces and brackets. | Hierarchy is denoted by using double space characters. | 
    | Favored in web development & transmitting data over HTTP |  Best for configuration files, along with JSON features. |

    Here is a example for JSON and YAML with same data. 
    
    ### JSON

            {
                "Products": [
                    {
                        "Accounts": [
                            "savings",
                            "current"
                        ]
                    },
                    {
                        "Loans": [
                            "Home",
                            "Car",
                            "Personal"
                        ]
                    },
                    {
                        "Cards": [
                            "credit cards",
                            "debit cards"
                        ]
                    }
                ]
            }
    ### YAML

            Products:
              - Accounts:
                - savings
                - current
              - Loans:
                 - Home 
                 - Car
                 - Personal
              - Cards:
                 - credit cards
                 - debit cards
        

**[⬆ Back to Top](#table-of-contents)**

3. ### [Can yaml be used in place of json?](#yaml-in-place-json)

    With technical approach YAML can be used for data exchange purpose between application to application which JSON is doing write now. But still JSON is used the reason is in applications to application data exchange communication No one bothered about human readability because two applications has to understand that request but not a human being, whereas in DevOps or in any cloud configuration where definitely some human has to understand it that's why YAML become more popular inside configuration management products rather than data exchange.

**[⬆ Back to Top](#table-of-contents)**

4. ### [What is the use of anchor and alias in yaml?](#anchor-alias)

    Anchors and aliases let you identify an item with an anchor in a YAML document, and then refer to that item with an alias later in the same document. Anchors are identified by an & character, and aliases by an * character.

    * The anchor '&' which defines a chunk of values/configuration 
    * The alias '*' used to refer to that chunk elsewhere

    Anchors & Aliases can be considered If we have repeated sections inside our yaml files. They can reduce effort and make updating in bulk, easier.

    The Alias essentially acts as a "see above’’ command, which makes the program pause standard traversal, return to the anchor point, then resume standard traversal after the Anchored portion is finished.

    YAML anchorsandaliasescannotcontainthe'[',']','{','}',and','characters.

**[⬆ Back to Top](#table-of-contents)**

5. ### [YAML datatypes?](#yaml-datatypes)

    Datatype supported by YAML are mostly all kind, like 

    * string, 
    * boolean, 
    * integers, 
    * float, 
    * timestamp, 
    * null

    But we don't need to explicitely define it's data type while writing an YAML file, YAML offers versatility in typing by auto-detecting data types while also supporting explicit typing options.

**[⬆ Back to Top](#table-of-contents)**

6. ### [What will be the value for below line in YAML in JSON?](#yes-true)

        ---
        Account:
          name: Narayan Sahoo
          inProject: Yes
          projectName: CICD pipeline

    The above lines on YAML will have this below output in JSON

        {
            "Account": {
                "name": "Narayan Sahoo",
                "inProject": true,
                "projectName": "CICD pipeline"
            }
        }

**[⬆ Back to Top](#table-of-contents)**

7. ### [Can you make this 'yes' or 'No' as string?](#yes-string)

    Yes we can make this **Yes** or **No** as a string by appling explicit typing option in YAML
        ---
        Account:
          name: Narayan Sahoo
          inProject: !!str Yes #explicit data type options
          projectName: CICD pipeline

    The above lines on YAML will have this below output in JSON

        {
            "Account": {
                "name": "Narayan Sahoo",
                "inProject": "Yes",
                "projectName": "CICD pipeline"
            }
        }

**[⬆ Back to Top](#table-of-contents)**

8. ### [Convert this below json to yaml?](#json-to-yaml)

    As it has some repeatetive objects so YAML anchor and alias can be usesd also override anchors


        ---
        Routine:
            days: 
            - weekday: &working
                    wakeup: 6:00 AM
                activities:
                    - workout
                - meetings
                - work
                - sleep
                sleeptime: 10:00 PM
        schedules:
            days:
            weekend:
                - monday: *working
            - tuesday: *working
            - wednesday: *working
            - thursday: *working
            - friday: 
                <<: *working
                sleeptime: 12:00 AM


**[⬆ Back to Top](#table-of-contents)**

9. ### [Can you tell the output from this below code and explain?](#json-to-yaml)

        ---
        Project: CICD
        desc: |
            CICD is need
            to be done
            by YAML
        history: >
            Initially it was
        done manually
        now done by YAML

    On the above code we are using to type of style for declaring multiline string
    
    * Folded style  **'|'** : it will have all the line breaks
    * Literal style **'>'** : it will have only one line break at the end

    This will be the outout in JSON

            {
                "Project": "CICD",
                "desc": "CICD is need\nto be done\nby YAML\n",
                "history": "Initially it was done manually now done by YAML\n"
            }



**[⬆ Back to Top](#table-of-contents)**

10. ### [Can you remove the last line break from the above code?](#remove-line-break)

    Yes we can achieve this by adding **'-'** with both the string style.

        ---
        Project: CICD
        desc: |-
            CICD is need
            to be done
            by YAML
        history: >-
            Initially it was
        done manually
        now done by YAML


    Outout in JSON

            {
                "Project": "CICD",
                "desc": "CICD is need\nto be done\nby YAML",
                "history": "Initially it was done manually now done by YAML"
            }



**[⬆ Back to Top](#table-of-contents)**

11. ### [What is KEY-VALUE pairs?](#key-value)
    Most things in a YAML file are a form of key-value pair. Key-value pairs are the basis for all other YAML
construction

For example: 

        # <key>: <value>
        account: projectname # projectname is value where account is the key 



**[⬆ Back to Top](#table-of-contents)**

12. ### [What is Scalers?](#Scalers)
    Scalars represent a single stored value. Scalars are assigned to key names as values. You define a key with
a name, colon, and space, then a value for it to hold

For example: 

        # <key>: <value>
        account: projectname # projectname is scaler 



**[⬆ Back to Top](#table-of-contents)**

13. ### [Comment in YAML?](#comment)
    
    **#** key is refered as comment in YAML file

For example: 

        ---
        Project: CICD
        desc: |-
            CICD is need
            to be done
            by YAML
        #history: >-
        #  Initially it was
        #  done manually
        #  now done by YAML
This above code will be represented like below in json, because JSON don't have commented line support

        {
            "Project": "CICD",
            "desc": "CICD is need\nto be done\nby YAML"
        }



**[⬆ Back to Top](#table-of-contents)**







