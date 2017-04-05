# Feature name

* Proposal: [SDL-NNNN](NNNN-Performance-testing.md)
* Author: [Dmitriy Boltovskiy](https://github.com/dboltovskyi)
* Status: **Awaiting review**
* Impacted Platforms: [ATF]

## Introduction

This proposal is to have an ability of SDL performace testing using ATF functionality.

## Motivation

Currently performance testing of SDL is not possible due to restrictions of ATF.
By implelenting proposed solution new types of testing become available:
* Load - check that SDL works as designed under a specific expected load
* Stress (robustness) - allows to understand the upper limits of SDL capacity
* Soak (endurance) - allows to determine if SDL can sustain the continuous expected load

## Proposed solution

A new feature of ATF is proposed: possibility to send multiple requests at mobile connection in parallel.
Processing duration of each request has to be measured as well as total duration.

## Potential downsides

No potential downsides are observed

## Impact on existing code

Existing code won't be affected

## Alternatives considered

Alternative approaches are not considered

