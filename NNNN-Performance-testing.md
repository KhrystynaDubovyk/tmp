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

A new feature of ATF is to have possibility to send multiple requests at mobile connection in parallel.
Processing duration of each request has to be measured as well as total duration.

Example:
1. Create mobile connection
2. Register one application
3. Send 100 requests (any RPC), with payload size = 1 kB
4. Check average processing time (duration)
5. Do steps 3,4 for payload size = 10 kB
6. Compare results

## Potential downsides

No potential downsides are observed

## Impact on existing code

Existing code won't be affected

## Alternatives considered

Using of alternative approaches (JMeter, Tsung etc.) was not considered due to impossibility to adopt them for ATF

