{
  "info": {
    "name": "Mattermost API Recycle database connections",
    "_postman_id": "d055cc83-c86c-491c-a889-8f2cb33195e5",
    "description": "Recycle database connections by closing and reconnecting all connections to master and read replica databases.\n##### Permissions\nMust have `manage_system` permission.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Recycle",
      "item": [
        {
          "id": "756e6d52-dceb-4517-99f2-8071523cc389",
          "name": "recycle-database-connections-by-closing-and-reconnecting-all-connections-to-master-and-read-replica-",
          "request": {
            "url": "http://your-mattermost-url.com/api/v4/database/recycle",
            "method": "POST",
            "body": {
              "mode": "raw"
            },
            "description": "Recycle database connections by closing and reconnecting all connections to master and read replica databases.\n##### Permissions\nMust have `manage_system` permission."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "397bdc3a-7214-4a3c-aa9d-e9fef396b45a"
            }
          ]
        }
      ]
    }
  ]
}