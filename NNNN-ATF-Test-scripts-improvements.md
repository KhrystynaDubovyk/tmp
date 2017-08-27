# Improve Automated test scripts

* Proposal: [SDL-NNNN](NNNN-ATF-Test-scripts-improvements.md)
* Author: [Dmitriy Boltovskiy](https://github.com/DBoltovskyi)
* Status: 
* Impacted Platforms: [ATF Test Scripts]

## Introduction
 
## Motivation
Quality of SDL needs to be improved. In order to make this happen number of automated scripts needs to be increased significantly.
Ideally to have complete test sets for the whole SDL functionality.

## Proposed solution
Existing 'user_modules' has to be refactored and all functions have to be split into two groups Utils and Common sequences.

All existing test scripts have to be updated in order to follow template and to use new structure of 'user_modules'.
New scripts has to follow template.

All scripts have to be kept in up-to-date state and maintained continuously.

All scripts have to be run as frequently as possible. Using of CI will help to automate this process.

## Detailed design
### Total refactoring of 'user_modules'
Existing functions have to be split into two groups:
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

## Impact on existing code
Huge impact on existing automated test scripts

## Alternatives considered
No
