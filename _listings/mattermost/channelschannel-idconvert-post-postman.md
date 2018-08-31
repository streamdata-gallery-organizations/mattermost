{
  "info": {
    "name": "Mattermost API Convert a channel from public to private",
    "_postman_id": "0dd41551-63f1-451e-ad9c-5a501f79dc4b",
    "description": "Convert into private channel from the provided channel id string.\n\n__Minimum server version__: 4.10\n\n##### Permissions\nMust have `manage_system` permission.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Convert",
      "item": [
        {
          "id": "554e5262-5462-4ec1-8eea-3d3c4ad5cac5",
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
              "id": "5e1444b6-1218-47b8-a915-28e787aa76ee"
            }
          ]
        }
      ]
    }
  ]
}