---
swagger: "2.0"
x-collection-name: Swagger
x-complete: 1
info:
  title: Swagger Hub Registry
  description: the-registry-api-for-swaggerhub
  contact:
    name: SwaggerHub
    url: http://swaggerhub.com
    email: info@swaggerhub.com
  version: 1.0.45
host: api.swaggerhub.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /apis/{owner}/{api}/{version}/.draft:
    delete:
      summary: Deletes a particular version of the specified API
      description: Deletes a particular version of the specified api.
      operationId: deleteDraftApi
      x-api-path-slug: apisownerapiversion-draft-delete
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - ""
      - Draft
    get:
      summary: Retrieves the draft for the specified API and version
      description: Retrieves the draft for the specified api and version.
      operationId: getDraft
      x-api-path-slug: apisownerapiversion-draft-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - ""
      - Draft
    put:
      summary: Saves the provided draft for a Swagger definition
      description: Saves the provided draft for a swagger definition.
      operationId: saveDraft
      x-api-path-slug: apisownerapiversion-draft-put
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: definition
        description: the Swagger definition of this API
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - ""
      - Draft
  /domains/{owner}/{domain}/{version}/.draft:
    delete:
      summary: Deletes a particular version of the specified Domain
      description: Deletes a particular version of the specified domain.
      operationId: deleteDraftDomain
      x-api-path-slug: domainsownerdomainversion-draft-delete
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Draft
    get:
      summary: Retrieves the draft for the specified domain
      description: Retrieves the draft for the specified domain.
      operationId: getDraftDomain
      x-api-path-slug: domainsownerdomainversion-draft-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Draft
    put:
      summary: Saves the provided draft for a domain.
      description: Saves the provided draft for a domain..
      operationId: saveDraftDomain
      x-api-path-slug: domainsownerdomainversion-draft-put
      parameters:
      - in: body
        name: definition
        description: the Swagger definition of this Domain
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Draft
---