{
  "info": {
    "name": "Mattermost API Get plugins",
    "_postman_id": "544c2c5e-d817-4eb1-8a12-24f93e6416f8",
    "description": "Get a list of inactive and a list of active plugin manifests. Plugins must be enabled in the server's config settings.\n\n##### Permissions\nMust have `manage_system` permission.\n\n__Minimum server version__: 4.4",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Plugins",
      "item": [
        {
          "id": "6ffd6f92-831b-47e9-8066-0edd1df04ce6",
          "name": "get-a-list-of-inactive-and-a-list-of-active-plugin-manifests-plugins-must-be-enabled-in-the-servers-",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/plugins",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get a list of inactive and a list of active plugin manifests. Plugins must be enabled in the server's config settings.\n\n##### Permissions\nMust have `manage_system` permission.\n\n__Minimum server version__: 4.4"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "b2c96cd6-91e8-42b6-926f-880eaa707d22"
            }
          ]
        }
      ]
    }
  ]
}