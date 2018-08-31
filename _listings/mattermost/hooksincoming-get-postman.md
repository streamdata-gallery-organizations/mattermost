{
  "info": {
    "name": "Mattermost API List incoming webhooks",
    "_postman_id": "9ebd9124-8bf1-45ce-a7ce-ca5218aaa43b",
    "description": "Get a page of a list of incoming webhooks. Optionally filter for a specific team using query parameters.\n##### Permissions\n`manage_webhooks` for the system or `manage_webhooks` for the specific team.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "List",
      "item": [
        {
          "id": "548d0e0a-d0ce-40ed-95d4-4e2ae7d054b1",
          "name": "get-a-page-of-a-list-of-incoming-webhooks-optionally-filter-for-a-specific-team-using-query-paramete",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/hooks/incoming?page=%7B%7D&per_page=%7B%7D&team_id=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get a page of a list of incoming webhooks. Optionally filter for a specific team using query parameters.\n##### Permissions\n`manage_webhooks` for the system or `manage_webhooks` for the specific team."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "499b838b-81e4-45c6-b396-625c3ef4a910"
            }
          ]
        }
      ]
    }
  ]
}