{
  "info": {
    "name": "Mattermost API Get webapp plugins",
    "_postman_id": "3dcca93a-e709-45c1-a339-dd6958b666ee",
    "description": "Get a list of web app plugins installed and activated on the server.\n\n##### Permissions\nNo permissions required.\n\n__Minimum server version__: 4.4",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Plugins",
      "item": [
        {
          "id": "43f40d8c-4d3e-4840-836a-43729d0a8241",
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
              "id": "ce8add02-3bbb-4147-9050-670985ed1fd8"
            }
          ]
        }
      ]
    },
    {
      "name": "Webapp",
      "item": [
        {
          "id": "d98a22ab-0a76-4a64-9f51-c07b7ae08475",
          "name": "get-a-list-of-web-app-plugins-installed-and-activated-on-the-server-permissionsno-permissions-requir",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/plugins/webapp",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get a list of web app plugins installed and activated on the server.\n\n##### Permissions\nNo permissions required.\n\n__Minimum server version__: 4.4"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "c8412f14-7511-4aa7-90e6-440cdb7f63c6"
            }
          ]
        }
      ]
    }
  ]
}