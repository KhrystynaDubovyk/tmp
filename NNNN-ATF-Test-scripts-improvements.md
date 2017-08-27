# Improve Automated test scripts

* Proposal: [SDL-NNNN](NNNN-ATF-Test-scripts-improvements.md)
* Author: [Dmitriy Boltovskiy](https://github.com/DBoltovskyi)
* Status: 
* Impacted Platforms: [ATF Test Scripts]

## Introduction
 
## Motivation
Quality of SDL needs to be improved. In order to make this happen number of automated scripts needs to be increased significantly. Ideally to have complete test set for the whole SDL functionality.

## Proposed solution
Split all functions in existing 'user_modules' into two groups Utils and Common sequences.

Update all existing test scripts according to template and new structure of 'user_modules'.
Create new scripts according to template.

Maintain continuously all scripts in up-to-date state.

Run all scripts as frequently as possible. Usage of CI will help to automate this process.

## Detailed design

### Script template
Already implemented for Remote Control functionalty.

### Changes of 'user_modules'
Split existing functions into two groups:
1. Utils
These are general helpers, ex.:
- file and database accessors
- table transformers
- validatots
- etc.
2. Common sequences
These are commonly used sequences of actions, ex.::
- hmi initialization
- application registration and activation
- policy table update
- Ignition On / Off  
- etc.

### Updating of existing scrips
Update existing scripts according to template and new structure.
This can be done step by step depending on priority.

## Impact on existing code
Huge impact on existing automated test scripts.

## Alternatives considered
No
