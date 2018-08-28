---
name: Open Science Framework
x-slug: open-science-framework
description: OSF provides free and open source project management support for researchers
  across the entire research lifecycle. As a collaboration tool, OSF helps researchers
  work on projects privately with a limited number of collaborators and make parts
  of their projects public, or make all the project publicly accessible for broader
  dissemination. As a workflow system, OSF enables connections to the many services
  researchers already use to streamline their process and increase efficiency. As
  a flexible repository, it can store and archive research data, protocols, and materials.
image: ""
x-kinRank: "7"
x-alexaRank: "0"
tags: Draft
created: "2018-08-27"
modified: "2018-08-27"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/draft/master/_listings/open-science-framework/apis.md
specificationVersion: "0.14"
apis:
- name: Open Science Framework - List all draft registrations
  x-api-slug: nodesnode-iddraft-registrations-get
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
  image: ""
  humanURL: https://cos.io
  baseURL: https://test-api.osf.io//v2
  tags: Research, Science, API Provider, Profiles, General Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/draft/master/_listings/open-science-framework/nodesnode-iddraft-registrations-get-openapi.md
- name: Open Science Framework - Create a draft registration
  x-api-slug: nodesnode-iddraft-registrations-post
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
  image: ""
  humanURL: https://cos.io
  baseURL: https://test-api.osf.io//v2
  tags: Research, Science, API Provider, Profiles, General Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/draft/master/_listings/open-science-framework/nodesnode-iddraft-registrations-post-openapi.md
- name: Open Science Framework - Delete a draft registration
  x-api-slug: nodesnode-iddraft-registrationsdraft-id-delete
  description: |-
    Permanently deletes a draft registration. A draft that has already been registered cannot be deleted.
    #### Permissions
    Only project administrators may delete draft registrations.
    #### Returns
    If the request is successful, no content is returned.

    If the request is unsuccessful, a JSON object with an `errors` key containing information about the failure will be returned. Refer to the [list of error codes]() to understand why this request may have failed.
  image: ""
  humanURL: https://cos.io
  baseURL: https://test-api.osf.io//v2
  tags: Research, Science, API Provider, Profiles, General Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/draft/master/_listings/open-science-framework/nodesnode-iddraft-registrationsdraft-id-delete-openapi.md
- name: Open Science Framework - Retrieve a draft registration
  x-api-slug: nodesnode-iddraft-registrationsdraft-id-get
  description: |-
    Retrieve the details of a given draft registration.
    Draft registrations contain the supplemental registration questions that accompany a registration. A registration is a frozen version of the project that can never be edited or deleted, but can be withdrawn.

    Your original project remains editable but will now have the draft registration linked to it.
    #### Permissions
    Only project administrators may view draft registrations.
    #### Returns
    Returns a JSON object with a `data` key containing the representation of the requested draft registration, if the request is successful.

    If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
  image: ""
  humanURL: https://cos.io
  baseURL: https://test-api.osf.io//v2
  tags: Research, Science, API Provider, Profiles, General Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/draft/master/_listings/open-science-framework/nodesnode-iddraft-registrationsdraft-id-get-openapi.md
- name: Open Science Framework - Update a draft registration
  x-api-slug: nodesnode-iddraft-registrationsdraft-id-patch
  description: |-
    Updates a draft registration by setting the values of the attributes specified in the request body. Any unspecified attributes will be left unchanged.

    Draft registrations contain the supplemental registration questions that accompany a registration. Answer the questions in the draft registration supplement by sending update requests until you are ready to submit the draft.

    The registration supplement of a draft registration cannot be updated after the draft has been created.

    When updating a draft registration, `registration_metadata` is required. It must be a dictionary with keys as question ids in the registration form, and values as nested dictionaries matching the specific format in the [registration schema](TODO: link me pls).

    If a question is multiple-choice, the question response must exactly match one of the possible choices.
    #### Permissions
    Only project administrators may update draft registrations.
    #### Returns
    Returns a JSON object with a `data` key containing the new representation of the updated draft registration, if the request is successful.

    If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
  image: ""
  humanURL: https://cos.io
  baseURL: https://test-api.osf.io//v2
  tags: Research, Science, API Provider, Profiles, General Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/draft/master/_listings/open-science-framework/nodesnode-iddraft-registrationsdraft-id-patch-openapi.md
x-common:
- type: x-website
  url: https://cos.io
- type: x-api-gallery
  url: http://open.fintech.api.gallery.streamdata.io
- type: x-api-stack
  url: http://open.science.framework.stack.network
- type: x-github
  url: https://github.com/OSFramework
- type: x-twitter
  url: https://twitter.com/OSFramework
- type: x-website
  url: http://osf.io
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---