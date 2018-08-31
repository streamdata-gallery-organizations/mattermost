{
  "info": {
    "name": "Mattermost API Remove public certificate",
    "_postman_id": "7f70ab25-2fbf-48b0-87a4-033362c60bc0",
    "description": "Delete the current public certificate being used with your SAML configuration. This will also disable encryption for SAML on your system as this certificate is required for that.\n##### Permissions\nMust have `manage_system` permission.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Convert",
      "item": [
        {
          "id": "39364532-003f-4bcc-8de5-dd3ae8d36a88",
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
              "id": "368209d0-a580-4895-9910-033cdb84e372"
            }
          ]
        }
      ]
    },
    {
      "name": "Public",
      "item": [
        {
          "id": "59b01547-3894-4843-b242-62da4dbb3db9",
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
              "id": "88d4e707-8b8b-40b6-b45e-7960f17b889c"
            }
          ]
        },
        {
          "id": "518e6b6d-18e5-42d0-a7c2-5a3e81310000",
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
              "id": "c1f7e5d3-6a38-4973-a1f5-170fb7032096"
            }
          ]
        }
      ]
    },
    {
      "name": "Upload",
      "item": [
        {
          "id": "27b5c547-a76c-4e34-8405-14c587108b62",
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
              "id": "e1bbaac6-8aac-474e-ae9b-b838d1ed6fbe"
            }
          ]
        }
      ]
    },
    {
      "name": "Remove",
      "item": [
        {
          "id": "5620c7f5-695f-40a9-8f59-956fd1ed1b97",
          "name": "delete-the-current-public-certificate-being-used-with-your-saml-configuration-this-will-also-disable",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/saml/certificate/public",
            "method": "DELETE",
            "body": {
              "mode": "raw"
            },
            "description": "Delete the current public certificate being used with your SAML configuration. This will also disable encryption for SAML on your system as this certificate is required for that.\n##### Permissions\nMust have `manage_system` permission."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "b247d4f8-66f2-4479-8275-729d29f0b2d0"
            }
          ]
        }
      ]
    }
  ]
}