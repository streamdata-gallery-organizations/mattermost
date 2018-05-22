---
swagger: "2.0"
x-collection-name: Mattermost
x-complete: 0
info:
  title: Mattermost API Create a user
  description: |-
    Create a new user on the system.
    ##### Permissions
    No permission required but user creation can be controlled by server configuration.
  termsOfService: https://about.mattermost.com/default-terms/
  version: 4.0.0
host: your-mattermost-url.com
basePath: /api/v4
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /users:
    post:
      summary: Create a user
      description: |-
        Create a new user on the system.
        ##### Permissions
        No permission required but user creation can be controlled by server configuration.
      operationId: create-a-new-user-on-the-system-permissionsno-permission-required-but-user-creation-can-be-controlle
      x-api-path-slug: users-post
      parameters:
      - in: body
        name: body
        description: User object to be created
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - User
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---