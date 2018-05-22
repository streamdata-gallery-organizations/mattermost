{
  "info": {
    "name": "Mattermost API List autocomplete commands",
    "_postman_id": "cb3f2ba1-33ee-4fd6-8e07-644da46db678",
    "description": "List autocomplete commands in the team.\n##### Permissions\n`view_team` for the team.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Autocomplete",
      "item": [
        {
          "id": "16bc04c8-4e23-48f1-91c9-fd8dc57e20e5",
          "name": "get-a-list-of-users-for-the-purpose-of-autocompleting-based-on-the-provided-search-term-specify-a-co",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/users/autocomplete?channel_id=%7B%7D&name=%7B%7D&team_id=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get a list of users for the purpose of autocompleting based on the provided search term. Specify a combination of `team_id` and `channel_id` to filter results further.\n##### Permissions\nRequires an active session and `view_team` and `read_channel` on any teams or channels used to filter the results further."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "dc5b4800-6de3-4ad1-b24c-90f74e115c91"
            }
          ]
        },
        {
          "id": "8f38b480-97e5-499c-b227-4b41fa183e53",
          "name": "autocomplete-public-channels-on-a-team-based-on-the-search-term-provided-in-the-request-url-minimum-",
          "request": {
            "url": {
              "protocol": "http",
              "host": "your-mattermost-url.com",
              "path": [
                "api",
                "v4",
                "teams/:team_id/channels/autocomplete"
              ],
              "query": [
                {
                  "key": "name",
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
            "description": "Autocomplete public channels on a team based on the search term provided in the request URL.\n\n__Minimum server version__: 4.7\n\n##### Permissions\nMust have the `list_team_channels` permission."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "082a4b8c-34a7-4658-b61d-589b483a1578"
            }
          ]
        },
        {
          "id": "27edb214-4d25-4673-8cbe-aeb9221fc304",
          "name": "get-a-list-of-custom-emoji-with-names-starting-with-or-matching-the-provided-name-returns-a-maximum-",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/emoji/autocomplete?name=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get a list of custom emoji with names starting with or matching the provided name. Returns a maximum of 100 results.\n##### Permissions\nMust be authenticated.\n\n__Minimum server version__: 4.7"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "7521d221-0588-49da-963c-4fc6486a40ee"
            }
          ]
        }
      ]
    },
    {
      "name": "List",
      "item": [
        {
          "id": "45c9fb53-2bb5-43e5-8405-0e2734032238",
          "name": "list-autocomplete-commands-in-the-team-permissionsview-team-for-the-team",
          "request": {
            "url": {
              "protocol": "http",
              "host": "your-mattermost-url.com",
              "path": [
                "api",
                "v4",
                "teams/:team_id/commands/autocomplete"
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
            "description": "List autocomplete commands in the team.\n##### Permissions\n`view_team` for the team."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "90f4bbb1-023a-495b-98b1-f779a8f3fd9b"
            }
          ]
        }
      ]
    }
  ]
}