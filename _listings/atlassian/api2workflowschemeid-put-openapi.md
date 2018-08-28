---
swagger: "2.0"
x-collection-name: Atlassian
x-complete: 0
info:
  title: Jira Cloud API Update workflow scheme
  description: |-
    Update the passed workflow scheme.

    The body of the request is a representation of the workflow scheme. Values not passed are assumed to indicate no change for that field.

    The passed representation can have its updateDraftIfNeeded flag set to true to indicate that the draft should be created and/or updated when the actual scheme cannot be edited (e.g. when the scheme is being used by a project). Values not appearing the body will not be touched.
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
  /content/blueprint/instance/{draftId}:
    post:
      summary: Publish legacy draft
      description: "Publishes a legacy draft of a page created from a blueprint. Legacy
        drafts \nwill eventually be removed in favour of shared drafts. For now, this
        method \nworks the same as [Publish shared draft](#api-content-blueprint-instance-draftId-put).\n\n**[Permissions](https://confluence.atlassian.com/x/_AozKw)
        required**: \nPermission to view the draft and 'Add' permission for the space
        that \nthe content will be created in."
      operationId: com.atlassian.confluence.plugins.restapi.resources.ContentBlueprintResource.publishLegacyDraft_post
      x-api-path-slug: contentblueprintinstancedraftid-post
      parameters:
      - in: path
        name: draftId
        description: The ID of the draft page that was created from a blueprint
      - in: query
        name: expand
        description: A multi-value parameter indicating which properties of the new
          content to expand when returned
      - in: query
        name: status
        description: The status of the content to be updated, i
      responses:
        200:
          description: OK
      tags:
      - Publish
      - Legacy
      - Draft
    put:
      summary: Publish shared draft
      description: "Publishes a shared draft of a page created from a blueprint.\n\n**[Permissions](https://confluence.atlassian.com/x/_AozKw)
        required**: \nPermission to view the draft and 'Add' permission for the space
        that \nthe content will be created in."
      operationId: com.atlassian.confluence.plugins.restapi.resources.ContentBlueprintResource.publishSharedDraft_put
      x-api-path-slug: contentblueprintinstancedraftid-put
      parameters:
      - in: path
        name: draftId
        description: The ID of the draft page that was created from a blueprint
      - in: query
        name: expand
        description: A multi-value parameter indicating which properties of the new
          content to expand when returned
      - in: query
        name: status
        description: The status of the content to be updated, i
      responses:
        200:
          description: OK
      tags:
      - Publish
      - Shared
      - Draft
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
  /api/2/workflowscheme/{id}/draft:
    get:
      summary: Get workflow scheme draft
      description: Returns the requested draft workflow scheme to the caller.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.getWorkflowSchemeDraft_get
      x-api-path-slug: api2workflowschemeiddraft-get
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
    put:
      summary: Update workflow scheme draft
      description: |-
        Update a draft workflow scheme. The draft will created if necessary.

        The body is a representation of the workflow scheme. Values not passed are assumed to indicate no change for that field.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.updateWorkflowSchemeDraft_put
      x-api-path-slug: api2workflowschemeiddraft-put
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
    delete:
      summary: Delete workflow scheme draft
      description: Delete the passed draft workflow scheme.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.deleteWorkflowSchemeDraft_del
      x-api-path-slug: api2workflowschemeiddraft-delete
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
  /api/2/workflowscheme/{id}/draft/default:
    get:
      summary: Get draft default workflow
      description: Return the default workflow from the passed draft workflow scheme
        to the caller.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.getDraftDefaultWorkflow_get
      x-api-path-slug: api2workflowschemeiddraftdefault-get
      parameters:
      - in: path
        name: id
        description: the id of the parent scheme
      responses:
        200:
          description: OK
      tags:
      - Draft
      - Default
      - Workflow
    put:
      summary: Update draft default workflow
      description: Set the default workflow for the passed draft workflow scheme.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.updateDraftDefaultWorkflow_pu
      x-api-path-slug: api2workflowschemeiddraftdefault-put
      parameters:
      - in: path
        name: id
        description: the id of the parent scheme
      responses:
        200:
          description: OK
      tags:
      - Draft
      - Default
      - Workflow
    delete:
      summary: Delete draft default workflow
      description: Remove the default workflow from the passed draft workflow scheme.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.deleteDraftDefaultWorkflow_de
      x-api-path-slug: api2workflowschemeiddraftdefault-delete
      parameters:
      - in: path
        name: id
        description: the id of the parent scheme
      responses:
        200:
          description: OK
      tags:
      - Draft
      - Default
      - Workflow
  /api/2/workflowscheme/{id}/draft/issuetype/{issueType}:
    get:
      summary: Get workflow scheme draft issue type
      description: Returns the issue type mapping for the passed draft workflow scheme.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.getWorkflowSchemeDraftIssueTy
      x-api-path-slug: api2workflowschemeiddraftissuetypeissuetype-get
      parameters:
      - in: path
        name: id
        description: the id of the parent scheme
      - in: path
        name: issueType
        description: the issue type to query
      responses:
        200:
          description: OK
      tags:
      - Workflow
      - Scheme
      - Draft
      - Issue
      - Type
    put:
      summary: Set workflow scheme draft issue type
      description: |-
        Set the issue type mapping for the passed draft scheme.

        The passed representation can have its updateDraftIfNeeded flag set to true to indicate that the draft should be created/updated when the actual scheme cannot be edited.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.setWorkflowSchemeDraftIssueTy
      x-api-path-slug: api2workflowschemeiddraftissuetypeissuetype-put
      parameters:
      - in: path
        name: id
        description: the id of the parent scheme
      - in: path
        name: issueType
        description: the issue type being set
      responses:
        200:
          description: OK
      tags:
      - Set
      - Workflow
      - Scheme
      - Draft
      - Issue
      - Type
    delete:
      summary: Delete workflow scheme draft issue type
      description: Remove the specified issue type mapping from the draft scheme.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.deleteWorkflowSchemeDraftIssu
      x-api-path-slug: api2workflowschemeiddraftissuetypeissuetype-delete
      parameters:
      - in: path
        name: id
        description: the parent of the draft scheme
      - in: path
        name: issueType
        description: the issue type to remove
      responses:
        200:
          description: OK
      tags:
      - Workflow
      - Scheme
      - Draft
      - Issue
      - Type
  /api/2/workflowscheme/{id}/draft/workflow:
    get:
      summary: Get draft workflow
      description: Returns the draft workflow mappings or requested mapping to the
        caller.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.getDraftWorkflow_get
      x-api-path-slug: api2workflowschemeiddraftworkflow-get
      parameters:
      - in: path
        name: id
        description: the id of the parent scheme
      - in: query
        name: workflowName
        description: the workflow mapping to return
      responses:
        200:
          description: OK
      tags:
      - Draft
      - Workflow
    put:
      summary: Update draft workflow mapping
      description: |-
        Update the draft scheme to include the passed mapping.

        The body is a representation of the workflow mapping. Values not passed are assumed to indicate no change for that field.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.updateDraftWorkflowMapping_pu
      x-api-path-slug: api2workflowschemeiddraftworkflow-put
      parameters:
      - in: path
        name: id
        description: the id of the parent scheme
      - in: query
        name: workflowName
        description: the name of the workflow mapping to update
      responses:
        200:
          description: OK
      tags:
      - Draft
      - Workflow
      - Mapping
    delete:
      summary: Delete draft workflow mapping
      description: Delete the passed workflow from the draft workflow scheme.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.deleteDraftWorkflowMapping_de
      x-api-path-slug: api2workflowschemeiddraftworkflow-delete
      parameters:
      - in: path
        name: id
        description: the id of the parent scheme
      - in: query
        name: workflowName
        description: the name of the workflow to delete
      responses:
        200:
          description: OK
      tags:
      - Draft
      - Workflow
      - Mapping
  /api/2/workflowscheme/{id}:
    put:
      summary: Update workflow scheme
      description: |-
        Update the passed workflow scheme.

        The body of the request is a representation of the workflow scheme. Values not passed are assumed to indicate no change for that field.

        The passed representation can have its updateDraftIfNeeded flag set to true to indicate that the draft should be created and/or updated when the actual scheme cannot be edited (e.g. when the scheme is being used by a project). Values not appearing the body will not be touched.
      operationId: com.atlassian.jira.rest.v2.admin.workflowscheme.WorkflowSchemeResource.updateWorkflowScheme_put
      x-api-path-slug: api2workflowschemeid-put
      parameters:
      - in: path
        name: id
        description: the id of the scheme
      responses:
        200:
          description: OK
      tags:
      - Workflow
      - Scheme
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