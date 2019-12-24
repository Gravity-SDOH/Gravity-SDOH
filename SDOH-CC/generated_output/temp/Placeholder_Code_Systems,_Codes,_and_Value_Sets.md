---
title: Placeholder Code Systems, Codes, and Value Sets
layout: default
active: Placeholder Code Systems, Codes, and Value Sets
---

[Previous Page](FHIR_Artifact_Naming_Conventions.html)

## Purpose
This document describes a simple process for assigning and managing temporary identifiers for terminology code systems, codes and value set ids within the context of FHIR IG development. It covers the life cycle from the point of creating identifiers to the endpoint of finalizing them by replacement with a permanent SDO.

When a guide is in a state of not complete (i.e. has not yet published as an STU), terminology artifacts such as code systems identifiers and codes, and value set identifiers should not be treated as permanent codes. Implementers cannot rely on any placeholder codes becoming permanent codes in the indicated code system. 

Placeholder codes are always destroyed and replaced with official permanent codes prior to the completion of ballot reconciliation and before the IG is published as an active standard.
 
## Placeholder Code Creation Process
This process is designed to support rapid assignment of new identifiers with little or no risk of creating ambiguous or overlapping values. These identifiers are guaranteed to be unique within the use of a specific IG managed by a specific workgroup/organization and within a specific time window with the intended purpose to support activities such as Connectathon testing.  This process is not intended to replace any processes being developed by HTA , UTG, CIMI, etc.

## Placeholder Code / Code System Assignment

First a set of prefixes need to be agreed upon to support the steps below. The prefixes are <group/team prefix> and `<code system: SDO terminology source prefix>`.   The idea is to keep the prefixes short so that they're easy to work with but unique within the scope of a project.
	
**Organization Prefix**

Always in upper case in the following format `<TTT>`. For example, Elimu uses `<ELU>`, gravity can use `<GRV>`, AMA can use `<AMA>`. etc
	
**Code System Prefix** 

Always in upper case and is intentionally not an official code system designation so as to avoid confusion when later reconciling codes against submissions to SDOs. 
	
**Code System Name**

The Code System Name is written in all capital letters and follows the pattern: ` <Org Prefix>-< Code System Prefix`>.
	
All of these prefixes are case insensitive, but we use all lowercase for consistency.

| SDO Source Terminology | Code System Prefix |
|------------------------|--------------------|
| SNOMED CT              | sctt               |
| LOINC                  | lncct              |
| RXNORM                 | rxnnt              |
| ICD-10-CM              | i10cmt             |
| ICD-10-PCS             | i10pcst            |
| HCPCS                  | ihcpcst            |
| CPT-4                  | icpt4t             |
| HL7                    | hl7t               |

Table 17: SDO Source Terminology

## Code System Creation Steps
Agree on prefixes. 

Create placeholder code system names in the format of  
				`		 <Org Prefix>-<Code System Prefix>`
	
If needed, create placeholder code system urns in the format of http://`<Org Prefix>.<Code System Prefix>.tmp/<OrgPrefix>-<Code System Prefix>`
	
Track the list of placeholder Code Systems in a common accessible repository such as a shared google spreadsheet or confluence page that the team an access for reference. Include documentation of them in the pre-publication Implementation Guide.

	Example: grv-sctt or expressed as a urn: http://grv.sctt.tmp/grv-sctt

	Example: grv-lncct           urn: http://grv.lncct.tmp/grv-lncct

	Example: grv-hl7t-tasks	urn: http://grv.hl7t-tasks.tmp/grv-hl7t-tasks


## Code Creation Steps
Placeholder codes are always represented in the format of `<Org Prefix>-<Code System Prefix>-<YYYYMMDDHHmmssTZ>`  so as to assure uniqueness within the scope of a project team. YYYY is a 4-digit year, MM is the 2-digit month, DD is the 2-digit day and HH is the 2-digit hour, mm is the minutes, ss is the seconds, TZ is the timezone. The time stamp is the time at which a code is being created. The advantage of this approach is that its a balance between simplicity and uniqueness. 

Agree on a reference time zone (TZ) (e.g., ET, CT, MT, PT) since time is used in the code assignment as stated above.

Note that since codes can never be specified in FHIR without a code system that this format will assure uniqueness of codes within the scope of a placeholder code system. 

	Example code:  grv-lncct-20191212171000ET

	Example code: grv-hl7-tasks-20191209143500ET system = http://grv.hl7t-tasks.tmp/grv-hl7t-tasks Display=screen-pts Text=Screen Patients



### Placeholder Value Set Identifier Assignment
Value sets placeholder identifiers are intended to populate the id element of a FHIR valueset resource.  The convention is similar to that of creating placeholder codes with the exception that a new prefix of VS is added to the id. 

## Value Set ID Creation Steps:
Agree on a reference time zone TZ(e.g., ET, CT, MT, PT) since the time zone is used in the placeholder Value Set name.

Value Sets are always created in the following format: `<Org Prefix>-<value set name>` -VS-`<YYYYMMDDHHmmssTZ>`.

To define the value set, record the value set identifier and its definition, then add the set of placeholder codes within the value set. 

	Example: GRV-Question 1 Answer Code List-VS-20191126101500ET


[Next Page](Local_Identifier_Systems.html)