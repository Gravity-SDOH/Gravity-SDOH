---
title: Local Identifier Systems
layout: default
active: Local Identifier Systems
---

[Previous Page](Placeholder_Code_Systems,_Codes,_and_Value_Sets.html)


Local Identifier Systems are used in IGs to demonstrate how to identify certain resources that need to be identified for an actual implementation.  The placeholder identification system needs to be replaced by an implementers actual identification system when conforming to the IG.

## Purpose
Certain resources, such a Questionnaires used for screening patients, need to be uniquely identified by the System Actor serving those Questionnaire Resources.  In order to provide general guidance, this implementation guide uses a naming convention to create placeholder identification systems.  The following material describes how to the placeholder identification systems are specified in this IG and explains how implementers would modify the placeholder information in their own implementations. 

## Placeholder Identification System Creation Steps
Each Form Manager can set up their own prefix replacing locali-screenings with their own unique identifier system for identifying Questionnaire Resources.

Example placeholder identification system: display=grv-locali-screenings	urn: http://grv.locali-screenings.tmp/grv-locali-screenings 

The identifier to identify the questionnaire would be: grv-locali-screenings-20191209144500ET
null