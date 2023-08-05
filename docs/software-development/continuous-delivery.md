# Continuous Delivery

Delivering (Releasing) a new version of software is a tedious and a repetitive task.
Having an automated Continuous Delivery pipeline makes everyone's life much easier.

## Continuous Delivery Pipelines
A Continuous Delivery Pipeline is a series of automated processes for delivering new software.
This goes hand in hand and comes a step after [Continuous Integration](continuous-integration.md) and 
[Automated Testing](automated-testing.md).

An ideal scenario of the entire CI/CD process is as follows:

1. Developer pushes a commit to the main branch.

2. The Continuous Integration prepares a build that's in a releasable state.

3. Automated Testing is executed to validate the new build.

4. The Continuous Delivery Pipeline releases the newly tested build.

## Feature Toggles
An obvious problem arises if developers **continuously** integrate their changes to the main branch.<BR>
Most of the times the development of a feature takes a long time and can't be integrated until completed.

This is when **Feature Toggles** come to rescue.<br>
Feature Toggles (or Feature Flags) is a powerful technique allowing teams to modify system behavior without changing code. 
We use this to confidently push incomplete features to the main branch (And even release them).

The incomplete features can be simply switched off using a Feature Toggle (Flag).

## Git Tags
We do want to continuously integrate changes to the main branch and we do want the automated build and 
testing process to be executed every time code is pushed to the main branch.

But in most cases, it's unlikely that we want all the successful builds to be released with the Delivery Pipeline.

To select a certain build to be released, we use Git Tags and mark a **specific commit** as the version 
that should be released by the Continuous Delivery Pipeline.
