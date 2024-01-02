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
|14  | [What is the command of docker building image?](#build-image) |
|15  | [Create a basic docker file for node application and explain?](#docker-file-create) |
|16  | [How to change destination directory in the image?](#workdir) |
|17  | [How to run a shell inside a docker image?](#run-shell) |
|18  | [How to run a docker with port mapping?](#port-mapping) |




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

    With technical approach YAML can be used for data exchange purpose between application to application which JSON is doing right now. The reason is in applications to application data exchange communication No one bothered about human readability because only two applications has to understand that request but not a human being, whereas in DevOps or in any cloud configuration where definitely some human has to understand it that's why YAML become more popular inside configuration management products rather than data exchange.

**[⬆ Back to Top](#table-of-contents)**

4. ### [What is the use of anchor and alias in yaml?](#anchor-alias)

    Anchors and aliases let you identify an item with an anchor in a YAML document, and then refer to that item with an alias later in the same document. Anchors are identified by an & character, and aliases by an * character.

    * The anchor '&' which defines a chunk of values/configuration 
    * The alias '*' used to refer to that chunk elsewhere

    Anchors & Aliases can be considered If we have repeated sections inside our yaml files. They can reduce effort and make updating in bulk, easier.

    The Alias essentially acts as a "see above’’ command, which makes the program pause standard traversal, return to the anchor point, then resume standard traversal after the Anchored portion is finished.

    YAML anchors and aliases cannot contain the'[',']','{','}',and','characters.

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

14. ### [What is the command of docker building image?](#build-image)
    
        docker build .
    this command will return an image with a id, using id is not recommended as every time with new build it will be changed or newly created. Instead of that we can use this 

        docker build -t dockerhub/myapplication .

    In the above command: 
    *  **-t** is for tagging,
    * **dockerhu** is docker account username
    * **myapplication** is the tag which we want to create
    * dot is the directory on which we want to build the image
    



**[⬆ Back to Top](#table-of-contents)**

15. ### [Create a basic docker file for node application and explain?](#docker-file-create)
    
    To create docker file, we have to create docker file in the root directory of our node application and the filename should be **Dockerfile** without any extension.

        # Base image specification
        FROM node:alpine

        # installations
        COPY ./ ./
        RUN npm install

        # Default command
        CMD ["npm", "start"]

    In the above example:
    * we are pulling an image from docker hub, which is **node** and with the tag **alpine**, it can be any other tag like version which is available in dockerhub under this node image
    * Under installation we are copying everything from root and pasting it inside the image root folder, first **dot slash** is from our application and second **dot slash** is destination.
    * In the **RUN** command its clear for dependency installations
    * The default command **CMD** is to start the application, in this case it is **npm start**
    

**[⬆ Back to Top](#table-of-contents)**

16. ### [How to change destination directory in the image?](#workdir)
    
    We can achive it by using **WORKDIR** in our dockerfile, and it is a good practice to specific a work directory inside the image, otherwise there will be a high chance of conflicting directory 

        # Base image specification
        FROM node:alpine

        WORKDIR /usr/app

        # installations
        COPY ./ ./
        RUN npm install

        # Default command
        CMD ["npm", "start"]

    In the above example we have selected **usr** directory, which we can get by running a shell inside the image.
    And inside the **usr** directory we are creating **app** directory and there we are pasting our source code. 
    

**[⬆ Back to Top](#table-of-contents)**

17. ### [How to run a shell inside a docker image?](#run-shell)
    
    To run a shell inside docker image follow these below steps.

    1. Get the docker id or image tag name 
    
            docker ps 
    2. After getting the id run the below command
            
            docker run -it <image id> sh
    This will open the shell of the image, and we can run window commands like
    **ls**, **cd** etc

    If the docker is already running, we can use **exec** command instead of **run**
            
        docker exec -it <image id> sh

**[⬆ Back to Top](#table-of-contents)**

18. ### [How to run a docker with port mapping?](#port-mapping)
    
    After getting image name by running the below command:

        docker run -p 3000:5000 dockerUser/imagename
    In the above code, **-p** is the tag for port and 3000 is the port where the request will come in 
    local machine and 5000 is the port inside container

**[⬆ Back to Top](#table-of-contents)**







