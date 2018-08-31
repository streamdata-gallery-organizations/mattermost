{
  "info": {
    "name": "Mattermost API Upload public certificate",
    "_postman_id": "ae3b4fe2-6a6a-4ca9-93f8-46aaa75ef55f",
    "description": "Upload the public certificate to be used for encryption with your SAML configuration. This will also set the filename for the PublicCertificateFile setting in your `config.json`.\n##### Permissions\nMust have `manage_system` permission.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Convert",
      "item": [
        {
          "id": "e2035e40-a408-442c-9cad-e586b4ca2b30",
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
              "id": "1d9d0101-6f62-42f4-8045-174ccb7f1577"
            }
          ]
        }
      ]
    },
    {
      "name": "Public",
      "item": [
        {
          "id": "ec530c96-79de-4286-a926-13f38b6b138a",
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
              "id": "212c68ff-7846-4e12-b9ec-1076ccc60478"
            }
          ]
        },
        {
          "id": "08d79153-ac8f-4908-a94a-67ca52051813",
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
              "id": "c9f5ded0-6263-4849-915c-a90750e10f54"
            }
          ]
        }
      ]
    },
    {
      "name": "Upload",
      "item": [
        {
          "id": "e4652eb5-ed41-483d-a09d-ed70835b3c71",
          "name": "upload-the-public-certificate-to-be-used-for-encryption-with-your-saml-configuration-this-will-also-",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/saml/certificate/public",
            "method": "POST",
            "body": {
              "mode": "urlencoded",
              "urlencoded": [
                {
                  "key": "certificate",
                  "value": "{}",
                  "disabled": false,
                  "description": "The public certificate file"
                }
              ]
            },
            "description": "Upload the public certificate to be used for encryption with your SAML configuration. This will also set the filename for the PublicCertificateFile setting in your `config.json`.\n##### Permissions\nMust have `manage_system` permission."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "d42ce38a-a58a-485d-b137-14f315053e5d"
            }
          ]
        }
      ]
    }
  ]
}