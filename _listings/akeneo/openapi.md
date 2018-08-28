swagger: "2.0"
x-collection-name: Akeneo
x-complete: 1
info:
  title: Official Akeneo PIM API
  description: the-akeneo-api-brought-to-youfind-out-how-this-postman-collection-works-by-visiting-httpapi-akeneo-com
  version: 1.0.0
host: example.com
basePath: /api
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /rest/v1/products/AKNTS_BPS/draft:
    get:
      summary: draft (2.x and EE only)
      description: |-
        Assuming that there is already a draft for the given product. The draft was created by the same user that using this request.
        The user has only an edition permission through categories on the given product.
      operationId: RestV1ProductsAKNTSBPSDraftGet
      x-api-path-slug: restv1productsaknts-bpsdraft-get
      responses:
        200:
          description: OK
      tags:
      - Draft
      - (2
      - X
      - EE
      - Only)
  /rest/v1/product-models/amor/draft:
    get:
      summary: draft (2.3 and EE only)
      description: |-
        Assuming that there is already a draft for the given product model. The draft was created by the same user that is using this request.
        The user has only an edition permission through categories on the given product model.
      operationId: RestV1ProductModelsAmorDraftGet
      x-api-path-slug: restv1productmodelsamordraft-get
      responses:
        200:
          description: OK
      tags:
      - Draft
      - (2
      - "3"
      - EE
      - Only)