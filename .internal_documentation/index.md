---
title: Internal documentation
permalink: internal/
has_children: true
nav_order: 1
has_toc: false
---

# Scalability with a glance
Sagas are used connect multiple actions/events into one transaction. All single actions should be constructed, so they can be used individual, but also in combination with other actions.

One example is uploading of different formats, like .xls, .xlsx, .doc, .docx, etc, here one action is to extract all information needed into the input json format.

Input is a document and an id which will be used to trace the actions, output is a JSON object and the id.

On the overall level message queue are used, to make the overall process scalable on multiple instances. The overall topics follow the XBRL wheel:

1. Extract
2. Convert
3. Validate
4. Visualize

Then it is possible to to have multiple consumers for each of the four steps, and it is possible to hook in at all steps wihtout constructing a saga for all possible combinations. And it will be possible to split up the topics, if some of the sagas handles too much.

## Sagas and Events

### Events
Input and output of events should be as general as possible, such it will be possible at a latter state to change the implementation. The events can be seen as interfaces for the overall functionality.

### Sagas
Extract
1. ??
2. ??

Convert
1. ??
2. ??

Validate
1. ??
2. ??

Visualize
1. ??
2. ??


### Common events
#### Scheduled delete
`fileId` / `projectId` and `timestamp` for when created, then it is possible to update this timestamp, if the deletion should be posponed
#### Delete files

#### Persist files

#### Retrive files

## Message Queue
Log
Error handling
