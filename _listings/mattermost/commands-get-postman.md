{
  "info": {
    "name": "Mattermost API List commands for a team",
    "_postman_id": "3adf2cca-f043-421a-a150-46024f7c46fb",
    "description": "List commands for a team.\n##### Permissions\n`manage_slash_commands` if need list custom commands.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "List",
      "item": [
        {
          "id": "e60492c7-536f-4a00-b680-73d092d1f19e",
          "name": "list-commands-for-a-team-permissionsmanage-slash-commands-if-need-list-custom-commands",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/commands?custom_only=%7B%7D&team_id=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "List commands for a team.\n##### Permissions\n`manage_slash_commands` if need list custom commands."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "90f79b33-1362-4b1a-ad88-e61ef58ab2f9"
            }
          ]
        }
      ]
    }
  ]
}