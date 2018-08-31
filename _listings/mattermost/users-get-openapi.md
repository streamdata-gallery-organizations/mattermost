---
swagger: "2.0"
x-collection-name: Mattermost
x-complete: 0
info:
  title: Mattermost API Get users
  description: |-
    Get a page of a list of users. Based on query string parameters, select users from a team, channel, or select users not in a specific channel.

    Since server version 4.0, some basic sorting is available using the `sort` query parameter. Sorting is currently only supported when selecting users on a team.
    ##### Permissions
    Requires an active session and (if specified) membership to the channel or team being selected from.
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
    get:
      summary: Get users
      description: |-
        Get a page of a list of users. Based on query string parameters, select users from a team, channel, or select users not in a specific channel.

        Since server version 4.0, some basic sorting is available using the `sort` query parameter. Sorting is currently only supported when selecting users on a team.
        ##### Permissions
        Requires an active session and (if specified) membership to the channel or team being selected from.
      operationId: get-a-page-of-a-list-of-users-based-on-query-string-parameters-select-users-from-a-team-channel-or-s
      x-api-path-slug: users-get
      parameters:
      - in: query
        name: in_channel
        description: The ID of the channel to get users for
      - in: query
        name: in_team
        description: The ID of the team to get users for
      - in: query
        name: not_in_channel
        description: The ID of the channel to exclude users for
      - in: query
        name: not_in_team
        description: The ID of the team to exclude users for
      - in: query
        name: page
        description: The page to select
      - in: query
        name: per_page
        description: The number of users per page
      - in: query
        name: sort
        description: Sort is only available in conjunction with certain options below
      - in: query
        name: without_team
        description: Whether or not to list users that are not on any team
      responses:
        200:
          description: OK
      tags:
      - Users
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