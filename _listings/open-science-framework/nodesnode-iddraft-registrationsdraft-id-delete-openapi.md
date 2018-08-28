---
swagger: "2.0"
x-collection-name: Open Science Framework
x-complete: 0
info:
  title: Open Science Framework Delete a draft registration
  description: |-
    Permanently deletes a draft registration. A draft that has already been registered cannot be deleted.
    #### Permissions
    Only project administrators may delete draft registrations.
    #### Returns
    If the request is successful, no content is returned.

    If the request is unsuccessful, a JSON object with an `errors` key containing information about the failure will be returned. Refer to the [list of error codes]() to understand why this request may have failed.
  contact:
    name: OSF
    url: https://osf.io/support
    email: support@osf.io
  version: "2.0"
host: test-api.osf.io
basePath: /v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /nodes/{node_id}/draft_registrations/:
    get:
      summary: List all draft registrations
      description: |-
        A paginated list of all of the draft registrations of a given node.

        Draft registrations contain the supplemental registration questions that accompany a registration. A registration is a frozen version of the project that can never be edited or deleted, but can be withdrawn.

        Your original project remains editable but will now have the draft registration linked to it.
        #### Permissions
        Only project administrators may view draft registrations.
        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of 10 draft registrations. Each resource in the array is a separate draft registration object and contains the full representation of the draft registration, meaning additional requests to a draft registration's detail view are not necessary.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).
      operationId: nodes_draft_registrations_list
      x-api-path-slug: nodesnode-iddraft-registrations-get
      parameters:
      - in: path
        name: node_id
        description: The unique identifier of the node
      responses:
        200:
          description: OK
      tags:
      - Nodes
      - Node
      - Draft
      - Registrations
    post:
      summary: Create a draft registration
      description: |-
        Initiate a draft registration of the current node.
        Draft registrations contain the supplemental registration questions that accompany a registration. A registration is a frozen version of the project that can never be edited or deleted, but can be withdrawn.

        Your original project remains editable but will now have the draft registration linked to it.
        #### Permissions
        Only project administrators may view create registrations.
        #### Required
        Required fields for creating a draft registration include:

        &nbsp;&nbsp;&nbsp;&nbsp`registration_supplement`
        #### Returns
        Returns a JSON object with a `data` key containing the representation of the created draft registration, if the request is successful.

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: nodes_draft_registrations_create
      x-api-path-slug: nodesnode-iddraft-registrations-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: node_id
        description: The unique identifier of the node
      responses:
        200:
          description: OK
      tags:
      - Nodes
      - Node
      - Draft
      - Registrations
  /nodes/{node_id}/draft_registrations/{draft_id}/:
    delete:
      summary: Delete a draft registration
      description: |-
        Permanently deletes a draft registration. A draft that has already been registered cannot be deleted.
        #### Permissions
        Only project administrators may delete draft registrations.
        #### Returns
        If the request is successful, no content is returned.

        If the request is unsuccessful, a JSON object with an `errors` key containing information about the failure will be returned. Refer to the [list of error codes]() to understand why this request may have failed.
      operationId: nodes_draft_registrations_delete
      x-api-path-slug: nodesnode-iddraft-registrationsdraft-id-delete
      parameters:
      - in: path
        name: draft_id
        description: The unique identifier of the draft registration
      - in: path
        name: node_id
        description: The unique identifier of the node
      responses:
        200:
          description: OK
      tags:
      - Nodes
      - Node
      - Draft
      - Registrations
      - Draft
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