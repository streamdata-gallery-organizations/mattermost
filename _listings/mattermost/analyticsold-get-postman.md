{
  "info": {
    "name": "Mattermost API Get analytics",
    "_postman_id": "37b78c4e-1ba1-42d2-a781-93aedf6a32bd",
    "description": "Get some analytics data about the system. This endpoint uses the old format, the `/analytics` route is reserved for the new format when it gets implemented.\n\nThe returned JSON changes based on the `name` query parameter but is always key/value pairs.\n\n__Minimum server version__: 4.0\n\n##### Permissions\nMust have `manage_system` permission.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Analytics",
      "item": [
        {
          "id": "b6b98f2a-98de-4925-9213-e811f2f8e865",
          "name": "get-some-analytics-data-about-the-system-this-endpoint-uses-the-old-format-the-analytics-route-is-re",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/analytics/old?name=%7B%7D&team_id=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get some analytics data about the system. This endpoint uses the old format, the `/analytics` route is reserved for the new format when it gets implemented.\n\nThe returned JSON changes based on the `name` query parameter but is always key/value pairs.\n\n__Minimum server version__: 4.0\n\n##### Permissions\nMust have `manage_system` permission."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "bcc56da5-dbf4-4f5c-b010-abdfc1604250"
            }
          ]
        }
      ]
    }
  ]
}