---
swagger: "2.0"
x-collection-name: Atlassian
x-complete: 0
info:
  title: Jira Cloud API Create workflow scheme draft from parent
  description: Create a draft for the passed scheme. The draft will be a copy of the
    state of the parent.
  termsOfService: http://atlassian.com/terms/
  version: 1.0.0
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /api/2/workflowscheme/{id}/createdraft:
    post:
      summary: Create workflow scheme draft from parent
      description: Create a draft for the passed scheme. The draft will be a copy
        of the state of the parent.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.createWorkflowSchemeDraftFrom
      x-api-path-slug: api2workflowschemeidcreatedraft-post
      parameters:
      - in: path
        name: id
        description: the id of the parent scheme
      responses:
        200:
          description: OK
      tags:
      - Workflow
      - Scheme
      - Draft
      - From
      - Parent
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---