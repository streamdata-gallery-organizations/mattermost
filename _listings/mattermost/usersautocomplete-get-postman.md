{
  "info": {
    "name": "Mattermost API Autocomplete users",
    "_postman_id": "6a68340d-bdd3-4d31-8949-3038189ba96c",
    "description": "Get a list of users for the purpose of autocompleting based on the provided search term. Specify a combination of `team_id` and `channel_id` to filter results further.\n##### Permissions\nRequires an active session and `view_team` and `read_channel` on any teams or channels used to filter the results further.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Autocomplete",
      "item": [
        {
          "id": "2234728d-a34f-47c7-871a-2ade1c1cc129",
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
              "id": "5c2c5cae-8e27-4045-9f3f-9c6be8c5847c"
            }
          ]
        }
      ]
    }
  ]
}