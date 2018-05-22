{
  "info": {
    "name": "Mattermost API Autocomplete channels",
    "_postman_id": "82d6d3ed-22d3-4e9e-8e0f-52a1f8a6999b",
    "description": "Autocomplete public channels on a team based on the search term provided in the request URL.\n\n__Minimum server version__: 4.7\n\n##### Permissions\nMust have the `list_team_channels` permission.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Autocomplete",
      "item": [
        {
          "id": "652467cb-dc43-4b46-ac27-e2e6a8abd750",
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
              "id": "4d0047ef-9afb-4cfa-99b9-ecdbe4579c99"
            }
          ]
        },
        {
          "id": "62d2d732-3bff-4c38-a2a6-238da3969196",
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
              "id": "7286e650-23de-423b-8b29-066b1e5e0134"
            }
          ]
        }
      ]
    }
  ]
}