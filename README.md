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
|6  | [Convert this below json to yaml?](#what-is-callback-hell) |
|7  | [How to handle call back function?](#how-to-handle-call-back-function) |




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







