{
  "info": {
    "name": "Azure Automation API Runbook Draft Get Content",
    "_postman_id": "e4b5b6e8-c8f1-46ea-9cb1-5162b0f381b1",
    "description": "Retrieve the content of runbook draft identified by runbook name.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "runbook",
      "item": [
        {
          "id": "90e682c1-660f-4448-a12b-f32747ff632c",
          "name": "RunbookDraft_GetContent",
          "request": {
            "url": {
              "protocol": "http",
              "host": "management.azure.com",
              "path": [
                "subscriptions/:subscriptionId/resourceGroups/:resourceGroupName/providers/Microsoft.Automation/automationAccounts/:automationAccountName/runbooks/:runbookName/draft/content"
              ],
              "query": [
                {
                  "key": "No Name",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "automationAccountName",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "runbookName",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "subscriptionId",
                  "value": "subscriptionId",
                  "type": "string"
                },
                {
                  "id": "resourceGroupName",
                  "value": "resourceGroupName",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieve the content of runbook draft identified by runbook name"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "74e76988-c552-45a4-97d1-f5b7087fb4fa"
            }
          ]
        }
      ]
    }
  ]
}