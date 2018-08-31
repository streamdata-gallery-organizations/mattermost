{
  "info": {
    "name": "Mattermost API Autocomplete custom emoji",
    "_postman_id": "d9964c7f-a863-4506-a330-2e33e9ee061a",
    "description": "Get a list of custom emoji with names starting with or matching the provided name. Returns a maximum of 100 results.\n##### Permissions\nMust be authenticated.\n\n__Minimum server version__: 4.7",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Autocomplete",
      "item": [
        {
          "id": "c3d53056-fdf3-4477-bd4b-fe421cc28ffb",
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
              "id": "294f6878-3703-451c-a9a4-f8431968a24b"
            }
          ]
        },
        {
          "id": "ad279bbb-a82a-4e9d-856b-180fff2b88ef",
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
              "id": "5b43666e-f4ed-4926-bff8-772e04f22b63"
            }
          ]
        },
        {
          "id": "45defa45-c41c-4552-be04-56e9e19de158",
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
              "id": "0631f6b3-2cba-4e87-addd-c3f73479fa29"
            }
          ]
        }
      ]
    }
  ]
}