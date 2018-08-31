{
  "info": {
    "name": "Mattermost API Get a public file link",
    "_postman_id": "b9d2f83d-236c-4193-8c2b-668c54d1054f",
    "description": "Gets a public link for a file that can be accessed without logging into Mattermost.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Convert",
      "item": [
        {
          "id": "faeb9b60-30e8-46b9-ba73-af9c33d4ec39",
          "name": "convert-into-private-channel-from-the-provided-channel-id-string-minimum-server-version--410-permiss",
          "request": {
            "url": {
              "protocol": "http",
              "host": "your-mattermost-url.com",
              "path": [
                "api",
                "v4",
                "channels/:channel_id/convert"
              ],
              "variable": [
                {
                  "id": "channel_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "POST",
            "body": {
              "mode": "raw"
            },
            "description": "Convert into private channel from the provided channel id string.\n\n__Minimum server version__: 4.10\n\n##### Permissions\nMust have `manage_system` permission."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "46813e86-8904-4219-83b4-4102cc25f2f7"
            }
          ]
        }
      ]
    },
    {
      "name": "Public",
      "item": [
        {
          "id": "94c0740a-bedb-4d60-a7cd-5c890b2df173",
          "name": "get-a-page-of-public-channels-on-a-team-based-on-query-string-parameters--page-and-per-page-permissi",
          "request": {
            "url": {
              "protocol": "http",
              "host": "your-mattermost-url.com",
              "path": [
                "api",
                "v4",
                "teams/:team_id/channels"
              ],
              "query": [
                {
                  "key": "page",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "per_page",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "team_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get a page of public channels on a team based on query string parameters - page and per_page.\n##### Permissions\nMust be authenticated and have the `list_team_channels` permission."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "babb006d-07a1-4017-86b2-6a2bf2b7c408"
            }
          ]
        },
        {
          "id": "94ec429f-101b-44c6-a50e-941647cb6a45",
          "name": "gets-a-public-link-for-a-file-that-can-be-accessed-without-logging-into-mattermost",
          "request": {
            "url": {
              "protocol": "http",
              "host": "your-mattermost-url.com",
              "path": [
                "api",
                "v4",
                "files/:file_id/link"
              ],
              "variable": [
                {
                  "id": "file_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Gets a public link for a file that can be accessed without logging into Mattermost."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "9a9c7377-70e0-4f3a-9d90-d2a4b365da0c"
            }
          ]
        }
      ]
    }
  ]
}