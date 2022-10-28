# ARTLOTS Standard - Version 1.0
ARTLOTS - Advanced Resource Tagging for Learners On The Spectrum


## Abstract
ARTLOTS is a JSON based file structure for tagging learning resources with additional metadata
to classify software-based learning resource content and provide a common structure to resources for learners on the autism spectrum.

The core aim of this standard is to provide a baseline for interoperability of learning resources for learners
on the autism spectrum.

This standard is a component of the OpenEARL.org project.

## Developed by

OpenEARL.org working group.


## Version
Version 1.0
Date 1st Nov 2022.

## Contact

OpenEARL.org team can be contacted at info@openearl.org


## 1. Introduction
The ARTLOTS standard is designed to be a common standard for resource exchange and integration for learning
applications used by learners on the autism spectrum. Emphasis is placed on the attributes of an autistic learner which
are often overlooked by other resource tagging approaches.

The core standard can be broken into three components:

1. Learner Profile Metadata (Section 2)
3. Learning Resource Tagging Metadata (Section 3)
3. Learning Resource Scene Structures (Section 4)



## 2. Learner Profile Metadata
**Filename:** learner_profile.json

The core of the ARTLOTS standard is the learner profile. This profile is designed to capture information about the learner. Three core sections can be seen in this. The first is profile_static_attributes that covers the core attributes of the learner that are typically not likely to change. Basic profile data is stored here.

**first_name** - Learners first name. This attribute is commonly used in learning resources to provide direct references to the learner during dialogue.

**last_name** - Learners last name. Used when direct dialogue to formally address the learner.

**gender** - Learners gender preference.

**dexterity** - The dexterity attribute is designed to capture the ability of the learner when input is required into the system. Low levels of dexterity will result 
in less combination choices and less required advanced movement such as moving a mouse or object on a screen by the learner.

**age** - The age attribute is used as a refernece point for the learner during dialogue. The age is not used as a deciding factor for levels of detail or complexity.

```

{
    "profile_static_attributes": [
        {
            "first_name": "John"
        },
        {
            "last_name": "Smith"
        },
        {
            "gender": "male"
        },
        {
            "dexterity": "high"
        },
        {
            "age": "4"
        }
    ],
    "profile_skill_attributes": [
        {
            "visual_tolerance": "low"
        },
        {
            "reading_ability": "low"
        },
        {
            "listening_ability": "medium"
        },
        {
            "adaptability": "high"
        },
        {
            "socialskills": "low"
        }

    ],
    "profile_complexity_attributes": {
        "task_complexity": "med",
        "prompt_complexity": "low",
        "visual_complexity": "low"
    }



}

```



## 3. Learning Resource Tagging Metadata


**Filename:** scene.json (top)

```
{
	"activityName": "Getting ready for school",
	"metadata": {
		"description": "This is a collection of tasks outlining getting ready for school. Aimed at a medium level of complexity. To work on listening and criticl thinking",
		"classifications": {
			"language_class": "med",
			"adaptability_class": "high",
			"socialskills_class": "med",
			"listening_class": "high",
			"prompt_repetition": "med",
			"task_complexity_class": "med",
			"prompt_complexity_class": "low",
			"visual_complexity_class": "low"
		},
		"task_types": [
			"listening skill",
			"critical thinking"
		]

	}
}
```








## 4. Learning Resource Scene Structure



```
{
	"actions": [{
		"orderId": "1",
		"tag": "getting out the bed",
		"alternativeAction": "",
		"questions": ["So, <name>, what do you do first when getting ready for school?",
			"Ok <name>, what's the first thing you do when getting ready for school?"
		],
		"correctResponses": ["I get out the bed", "I get up"],
		"previous": "",
		"noAnswerPrompts": ["<name>, are you going to tell me what you do first?",
			"Come on <name>, tell me the first thing you do when geeting ready for school"
		],
		"errorPrompts": ["no way <name>, that's not the first thing you do!!",
			"<name>, your mom told me that's not the first thing you do when getting ready for school"
		],
		"reinforcers": ["excellent", "great", "very good"],
		"childActivity": ""
	}]
}

```







