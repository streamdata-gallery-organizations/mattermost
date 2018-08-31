{
  "info": {
    "name": "Mattermost API Get channel statistics",
    "_postman_id": "d895c14d-9740-403d-be1c-d6769727d1a6",
    "description": "Get statistics for a channel.\n##### Permissions\nMust have the `read_channel` permission.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Channel",
      "item": [
        {
          "id": "4a193c50-9041-44c5-8f04-55f800fe3c16",
          "name": "get-statistics-for-a-channel-permissionsmust-have-the-read-channel-permission",
          "request": {
            "url": {
              "protocol": "http",
              "host": "your-mattermost-url.com",
              "path": [
                "api",
                "v4",
                "channels/:channel_id/stats"
              ],
              "variable": [
                {
                  "id": "channel_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get statistics for a channel.\n##### Permissions\nMust have the `read_channel` permission."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "0cf66c3d-d4b0-4aa5-9ee4-38640f8f0ec1"
            }
          ]
        }
      ]
    }
  ]
}