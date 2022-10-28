# ARTLOTS Standard - Version 1.0
ARTLOTS - Advanced Resource Tagging for Learners On The Spectrum

**Status:** Live Beta
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

The JSON files outlined in this standard include:

**learner_profile.json** - Learner specific profile data outlining their personal attributes and current abilities.

**scene.json** - A structure for learning resources.


## 2. Learner Profile Metadata
**Filename:** learner_profile.json

The core of the ARTLOTS standard is the learner profile. This profile is designed to capture information about the learner. Three core sections can be seen in this. The first is profile_static_attributes that covers the core attributes of the learner that are typically not likely to change. Basic profile data is stored here.

- **first_name** - Learners first name. This attribute is commonly used in learning resources to provide direct references to the learner during dialogue.

- **last_name** - Learners last name. Used when direct dialogue to formally address the learner.

- **gender** - Learners gender preference.

- **dexterity** - The dexterity attribute is designed to capture the ability of the learner when input is required into the system. Low levels of dexterity will result 
in less combination choices and less required advanced movement such as moving a mouse or object on a screen by the learner.

- **age** - The age attribute is used as a refernece point for the learner during dialogue. The age is not used as a deciding factor for levels of detail or complexity.

The **profile_skill_attributes** are designed to reflect the current abilities of the learner in a range of different categories. Depending on the values, a variety of changes can be made to the quantity of visual, auditory stimulus, and complexity in any given scene. 

- **visual_tolerance** - This attribute is designed to reflect the overall level of visual stimulus a learner is able for. Low visual tolerance will result in lighter colours, less complex scenes or less actors involved in any given scene.
- **reading_ability** - The reading ability of a learner directly impacts how scenes can be rendered. Learners with low reading ability will not be required to read content or dialogue. Learners with a high ability will be encouraged to read scene dialogue and text placed on interactive buttons.
- **listening_ability** - As some learners enjoy listening to dialogue, if the listening ability is set to high, more dialogue will be spoken. If the ability is low, background music and additional sound effects will be removed from a scene.
- **adaptability** - A learner's adaptability is a reference to how comfortable they are with new actors and content being displayed. A learner with a low adaptability will  be provided with reoccurring themes of interest during all scenes to encourage familiarity.
- **socialskills** - A learner's social skills is a reference to their over all ability to interact and respond to social based dialogue. Learners with a low social skills will be encouraged to focus on the area in small increments and not overwhelmed with social dialogue.

The **profile_complexity_attributes** are designed as a reference point for the level of overall complexity that should be provided for a learner.

- **task_complexity** - The task complexity is designed to outline the overal general complexity of a task in a given scene. This is directly linked to the amount of thought and effort that is needed for a correct answer.
- **prompt_complexity** - This attribute is used for deciding on the number of options that are available for the learner to choose from. Low complexity allows one of two possible choices.
- **visual_complexity** - This attribute is designed to outline how complex an individual scene should be for the learner. Low complexity outlines that few scene actors and background components should be added to a scene. 


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
Each learning resource is a compilation of individual scenes. The JSON below represents one individual scene from a learning resource.

-**activity_name** - A basic title for the resource. This is often used as the name when individual scenes are rendered or when listed as part of a learning resource.

-**creation_date** - The date when the resource was last modified. Structured as DD-MM-YYYY.

The core of the scene is the **metadata** tag. This contains a **description** attribute that describes the scene in detail. The **classifications** outlines for each of the core ability levels in each area that the resource is designed for. 


- **language_class** - This attribute describes the overall complexity of the language used in the scene. High indicating detailed language.
- **adaptability_class** - This referneces the overall adaptability of the learner. Where low, the topics and actors relevant to the learner will become more frequently mentioned.
- **socialskills_class** - This references the overall amount of social skills required for the scene. If high, the learner is expected to have good understanding of social dialogue. If low, very little social dialogue is included.
- **listening_class** - For learners with good listening skills, if this attribute is set to high, an emphasis is placed on the vocalisation of dialogue and prompts to the learner.
- **prompt_repetition** - This attribute outlines how often prompts in the scene are repeated. Often specific learners benefit from repeating a question or prompt.
- **task_complexity_class** - This attribute defines the overall task complexity with reference to how much thought and effort is required from the learner to complete for a successful answer.
- **prompt_complexity_class** - This attribute references the overall complexity of the prompt with respect to the number of options and detail added to the prompt. Low complexity would be image based with no text. 
- **visual_complexity_class** - As some learners require minimal distraction, the visual complexity references the number of background activities that are being performed in the scene. If low, no additional actors or background images are added as they may cause additional distraction.






**Filename:** scene.json (top)

```
{
	"creation_date": "28-10-2022"
	"activity_name": "Getting ready for school",
	"metadata": {
		"description": "This is a collection of tasks outlining getting ready for school.",
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







