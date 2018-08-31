{
  "info": {
    "name": "Mattermost API List outgoing webhooks",
    "_postman_id": "74f4b99b-0d21-4e7f-a5c8-307fbf4deeac",
    "description": "Get a page of a list of outgoing webhooks. Optionally filter for a specific team or channel using query parameters.\n##### Permissions\n`manage_webhooks` for the system or `manage_webhooks` for the specific team/channel.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "List",
      "item": [
        {
          "id": "5217e537-69c7-4a44-98e0-7a33d5a1d1df",
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
              "id": "4f544aae-f21d-4b03-bf7b-c471b1d04240"
            }
          ]
        },
        {
          "id": "fccc0108-fd9c-4085-8500-f261c4c341db",
          "name": "get-a-page-of-a-list-of-outgoing-webhooks-optionally-filter-for-a-specific-team-or-channel-using-que",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/hooks/outgoing?channel_id=%7B%7D&page=%7B%7D&per_page=%7B%7D&team_id=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get a page of a list of outgoing webhooks. Optionally filter for a specific team or channel using query parameters.\n##### Permissions\n`manage_webhooks` for the system or `manage_webhooks` for the specific team/channel."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "93112ea4-1f39-46ad-ad8d-3c2d5742f1ce"
            }
          ]
        }
      ]
    }
  ]
}