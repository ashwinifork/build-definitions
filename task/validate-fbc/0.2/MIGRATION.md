# Migration Guide for `validate-fbc` Task v0.2

## Overview
Version 0.2 of the `validate-fbc` task introduces support for "binaryless" File-Based Catalogs (FBCs) for OpenShift versions 4.15 and higher [CLOUDDST-31457](https://redhat.atlassian.net/browse/CLOUDDST-31457). 

Version 0.2 tries to fetch OCP version uisng `com.redhat.fbc.openshift.version` label and when not found falls back to find the ocp version using base image idenfication.

For OCP version v4.15 and + the base-image verification is now bypassed. 
Also it dynamically maps the required OCP versions to the correct `opm` binaries provided directly within the `konflux-test` image.

## Backwards Compatibility
This version is **fully backwards compatible** with v0.1 in terms of inputs and outputs. Existing pipelines will continue to function without requiring any structural changes to parameters or workspaces.

## Changes at a Glance

### Parameters
No parameters were added, removed, or modified.

| Parameter | Status | Notes |
| --------- | ------ | ----- |
| `IMAGE_URL` | Unchanged | |
| `IMAGE_DIGEST` | Unchanged | |

### Results
No results were added, removed, or modified.

| Result | Status | Notes |
| ------ | ------ | ----- |
| `RELATED_IMAGE_ARTIFACT` | Unchanged | |
| `TEST_OUTPUT_ARTIFACT` | Unchanged | |
| `TEST_OUTPUT` | Unchanged | |
| `RELATED_IMAGES_DIGEST` | Unchanged | |
| `IMAGES_PROCESSED` | Unchanged | |
| `RENDERED_CATALOG_DIGEST`| Unchanged | |


## How to Migrate

To migrate to `v0.2`, you simply need to update the version reference in your Pipeline definition. 
