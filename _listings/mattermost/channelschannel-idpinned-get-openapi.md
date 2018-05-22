---
swagger: "2.0"
x-collection-name: Mattermost
x-complete: 0
info:
  title: Mattermost API Get a channels pinned posts
  description: Get a list of pinned posts for channel.
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
  /users/ids:
    post:
      summary: Get users by ids
      description: |-
        Get a list of users based on a provided list of user ids.
        ##### Permissions
        Requires an active session but no other permissions.
      operationId: get-a-list-of-users-based-on-a-provided-list-of-user-ids-permissionsrequires-an-active-session-but-n
      x-api-path-slug: usersids-post
      parameters:
      - in: body
        name: body
        description: List of user ids
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Users
      - By
      - Ids
  /users/usernames:
    post:
      summary: Get users by usernames
      description: |-
        Get a list of users based on a provided list of usernames.
        ##### Permissions
        Requires an active session but no other permissions.
      operationId: get-a-list-of-users-based-on-a-provided-list-of-usernames-permissionsrequires-an-active-session-but-
      x-api-path-slug: usersusernames-post
      parameters:
      - in: body
        name: body
        description: List of usernames
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Users
      - By
      - Usernames
  /users/search:
    post:
      summary: Search users
      description: |-
        Get a list of users based on search criteria provided in the request body. Searches are typically done against username, full name, nickname and email unless otherwise configured by the server.
        ##### Permissions
        Requires an active session and `read_channel` and/or `view_team` permissions for any channels or teams specified in the request body.
      operationId: get-a-list-of-users-based-on-search-criteria-provided-in-the-request-body-searches-are-typically-don
      x-api-path-slug: userssearch-post
      parameters:
      - in: body
        name: body
        description: Search criteria
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Search
      - Users
  /users/autocomplete:
    get:
      summary: Autocomplete users
      description: |-
        Get a list of users for the purpose of autocompleting based on the provided search term. Specify a combination of `team_id` and `channel_id` to filter results further.
        ##### Permissions
        Requires an active session and `view_team` and `read_channel` on any teams or channels used to filter the results further.
      operationId: get-a-list-of-users-for-the-purpose-of-autocompleting-based-on-the-provided-search-term-specify-a-co
      x-api-path-slug: usersautocomplete-get
      parameters:
      - in: query
        name: channel_id
        description: Channel ID
      - in: query
        name: name
        description: Username, nickname first name or last name
      - in: query
        name: team_id
        description: Team ID
      responses:
        200:
          description: OK
      tags:
      - Autocomplete
      - Users
  /users/{user_id}:
    get:
      summary: Get a user
      description: |-
        Get a user a object. Sensitive information will be sanitized out.
        ##### Permissions
        Requires an active session but no other permissions.
      operationId: get-a-user-a-object-sensitive-information-will-be-sanitized-out-permissionsrequires-an-active-sessio
      x-api-path-slug: usersuser-id-get
      parameters:
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - User
    put:
      summary: Update a user
      description: |-
        Update a user by providing the user object. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
        ##### Permissions
        Must be logged in as the user being updated or have the `edit_other_users` permission.
      operationId: update-a-user-by-providing-the-user-object-the-fields-that-can-be-updated-are-defined-in-the-request
      x-api-path-slug: usersuser-id-put
      parameters:
      - in: body
        name: body
        description: User object that is to be updated
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - User
    delete:
      summary: Deactivate a user account.
      description: |-
        Deactivates the user by archiving its user object.
        ##### Permissions
        Must be logged in as the user being deactivated or have the `edit_other_users` permission.
      operationId: deactivates-the-user-by-archiving-its-user-object-permissionsmust-be-logged-in-as-the-user-being-dea
      x-api-path-slug: usersuser-id-delete
      parameters:
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Deactivate
      - User
      - Account.
  /users/{user_id}/patch:
    put:
      summary: Patch a user
      description: |-
        Partially update a user by providing only the fields you want to update. Omitted fields will not be updated. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
        ##### Permissions
        Must be logged in as the user being updated or have the `edit_other_users` permission.
      operationId: partially-update-a-user-by-providing-only-the-fields-you-want-to-update-omitted-fields-will-not-be-u
      x-api-path-slug: usersuser-idpatch-put
      parameters:
      - in: body
        name: body
        description: User object that is to be updated
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - User
  /users/{user_id}/roles:
    put:
      summary: Update a user's roles
      description: |-
        Update a user's system-level roles. Valid user roles are "system_user", "system_admin" or both of them. Overwrites any previously assigned system-level roles.
        ##### Permissions
        Must have the `manage_roles` permission.
      operationId: update-a-users-systemlevel-roles-valid-user-roles-are-system-user-system-admin-or-both-of-them-overw
      x-api-path-slug: usersuser-idroles-put
      parameters:
      - in: body
        name: roles
        description: Space-delimited system roles to assign to the user
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Users
      - Roles
  /users/{user_id}/active:
    put:
      summary: Update user active status
      description: |-
        Update user active or inactive status.

        __Since server version 4.6, users using a SSO provider to login can be activated or deactivated with this endpoint. However, if their activation status in Mattermost does not reflect their status in the SSO provider, the next synchronization or login by that user will reset the activation status to that of their account in the SSO provider. Server versions 4.5 and before do not allow activation or deactivation of SSO users from this endpoint.__
        ##### Permissions
        User can deactivate themself.
        User with `manage_system` permission can activate or deactivate a user.
      operationId: update-user-active-or-inactive-status-since-server-version-46-users-using-a-sso-provider-to-login-ca
      x-api-path-slug: usersuser-idactive-put
      parameters:
      - in: body
        name: body
        description: Use `true` to set the user active, `false` for inactive
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - User
      - Active
      - Status
  /users/{user_id}/image:
    get:
      summary: Get user's profile image
      description: |-
        Get a user's profile image based on user_id string parameter.
        ##### Permissions
        Must be logged in.
      operationId: get-a-users-profile-image-based-on-user-id-string-parameter-permissionsmust-be-logged-in
      x-api-path-slug: usersuser-idimage-get
      parameters:
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Users
      - Profile
      - Image
    post:
      summary: Set user's profile image
      description: |-
        Set a user's profile image based on user_id string parameter.
        ##### Permissions
        Must be logged in as the user being updated or have the `edit_other_users` permission.
      operationId: set-a-users-profile-image-based-on-user-id-string-parameter-permissionsmust-be-logged-in-as-the-user
      x-api-path-slug: usersuser-idimage-post
      parameters:
      - in: formData
        name: image
        description: The image to be uploaded
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Set
      - Users
      - Profile
      - Image
  /users/username/{username}:
    get:
      summary: Get a user by username
      description: |-
        Get a user object by providing a username. Sensitive information will be sanitized out.
        ##### Permissions
        Requires an active session but no other permissions.
      operationId: get-a-user-object-by-providing-a-username-sensitive-information-will-be-sanitized-out-permissionsreq
      x-api-path-slug: usersusernameusername-get
      parameters:
      - in: path
        name: username
        description: Username
      responses:
        200:
          description: OK
      tags:
      - User
      - By
      - Username
  /users/password/reset:
    post:
      summary: Reset password
      description: |-
        Update the password for a user using a one-use, timed recovery code tied to the user's account. Only works for non-SSO users.
        ##### Permissions
        No permissions required.
      operationId: update-the-password-for-a-user-using-a-oneuse-timed-recovery-code-tied-to-the-users-account-only-wor
      x-api-path-slug: userspasswordreset-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Reset
      - Password
  /users/{user_id}/mfa:
    put:
      summary: Update a user's MFA
      description: |-
        Activates multi-factor authentication for the user if `activate` is true and a valid `code` is provided. If activate is false, then `code` is not required and multi-factor authentication is disabled for the user.
        ##### Permissions
        Must be logged in as the user being updated or have the `edit_other_users` permission.
      operationId: activates-multifactor-authentication-for-the-user-if-activate-is-true-and-a-valid-code-is-provided-i
      x-api-path-slug: usersuser-idmfa-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Users
      - MFA
  /users/{user_id}/mfa/generate:
    post:
      summary: Generate MFA secret
      description: |-
        Generates an multi-factor authentication secret for a user and returns it as a string and as base64 encoded QR code image.
        ##### Permissions
        Must be logged in as the user or have the `edit_other_users` permission.
      operationId: generates-an-multifactor-authentication-secret-for-a-user-and-returns-it-as-a-string-and-as-base64-e
      x-api-path-slug: usersuser-idmfagenerate-post
      parameters:
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Generate
      - MFA
      - Secret
  /users/mfa:
    post:
      summary: Check MFA
      description: |-
        Check if a user has multi-factor authentication active on their account by providing a login id. Used to check whether an MFA code needs to be provided when logging in.
        ##### Permissions
        No permission required.
      operationId: check-if-a-user-has-multifactor-authentication-active-on-their-account-by-providing-a-login-id-used-
      x-api-path-slug: usersmfa-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Check
      - MFA
  /users/{user_id}/password:
    put:
      summary: Update a user's password
      description: |-
        Update a user's password. New password must meet password policy set by server configuration. Current password is required if you're updating your own password.
        ##### Permissions
        Must be logged in as the user the password is being changed for or have `manage_system` permission.
      operationId: update-a-users-password-new-password-must-meet-password-policy-set-by-server-configuration-current-p
      x-api-path-slug: usersuser-idpassword-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Users
      - Password
  /users/password/reset/send:
    post:
      summary: Send password reset email
      description: |-
        Send an email containing a link for resetting the user's password. The link will contain a one-use, timed recovery code tied to the user's account. Only works for non-SSO users.
        ##### Permissions
        No permissions required.
      operationId: send-an-email-containing-a-link-for-resetting-the-users-password-the-link-will-contain-a-oneuse-time
      x-api-path-slug: userspasswordresetsend-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Send
      - Password
      - Reset
      - Email
  /users/email/{email}:
    get:
      summary: Get a user by email
      description: |-
        Get a user object by providing a user email. Sensitive information will be sanitized out.
        ##### Permissions
        Requires an active session but no other permissions.
      operationId: get-a-user-object-by-providing-a-user-email-sensitive-information-will-be-sanitized-out-permissionsr
      x-api-path-slug: usersemailemail-get
      parameters:
      - in: path
        name: email
        description: User Email
      responses:
        200:
          description: OK
      tags:
      - User
      - By
      - Email
  /users/{user_id}/sessions:
    get:
      summary: Get user's sessions
      description: |-
        Get a list of sessions by providing the user GUID. Sensitive information will be sanitized out.
        ##### Permissions
        Must be logged in as the user being updated or have the `edit_other_users` permission.
      operationId: get-a-list-of-sessions-by-providing-the-user-guid-sensitive-information-will-be-sanitized-out-permis
      x-api-path-slug: usersuser-idsessions-get
      parameters:
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Users
      - Sessions
  /users/{user_id}/sessions/revoke:
    post:
      summary: Revoke a user session
      description: |-
        Revokes a user session from the provided user id and session id strings.
        ##### Permissions
        Must be logged in as the user being updated or have the `edit_other_users` permission.
      operationId: revokes-a-user-session-from-the-provided-user-id-and-session-id-strings-permissionsmust-be-logged-in
      x-api-path-slug: usersuser-idsessionsrevoke-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Revoke
      - User
      - Session
  /users/{user_id}/sessions/revoke/all:
    post:
      summary: Revoke all active sessions for a user
      description: |-
        Revokes all user sessions from the provided user id and session id strings.
        ##### Permissions
        Must be logged in as the user being updated or have the `edit_other_users` permission.
        __Minimum server version__: 4.4
      operationId: revokes-all-user-sessions-from-the-provided-user-id-and-session-id-strings-permissionsmust-be-logged
      x-api-path-slug: usersuser-idsessionsrevokeall-post
      parameters:
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Revoke
      - ""
      - Active
      - Sessionsa
      - User
  /users/sessions/device:
    put:
      summary: Attach mobile device
      description: |-
        Attach a mobile device id to the currently logged in session. This will enable push notiofications for a user, if configured by the server.
        ##### Permissions
        Must be authenticated.
      operationId: attach-a-mobile-device-id-to-the-currently-logged-in-session-this-will-enable-push-notiofications-fo
      x-api-path-slug: userssessionsdevice-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Attach
      - Mobile
      - Device
  /users/{user_id}/audits:
    get:
      summary: Get users audits
      description: |-
        Get a list of audit by providing the user GUID.
        ##### Permissions
        Must be logged in as the user or have the `edit_other_users` permission.
      operationId: get-a-list-of-audit-by-providing-the-user-guid-permissionsmust-be-logged-in-as-the-user-or-have-the-
      x-api-path-slug: usersuser-idaudits-get
      parameters:
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Users
      - Audits
  /users/email/verify:
    post:
      summary: Verify user email
      description: |-
        Verify the email used by a user to sign-up their account with.
        ##### Permissions
        No permissions required.
      operationId: verify-the-email-used-by-a-user-to-signup-their-account-with-permissionsno-permissions-required
      x-api-path-slug: usersemailverify-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Verify
      - User
      - Email
  /users/email/verify/send:
    post:
      summary: Send verification email
      description: |-
        Send an email with a verification link to a user that has an email matching the one in the request body. This endpoint will return success even if the email does not match any users on the system.
        ##### Permissions
        No permissions required.
      operationId: send-an-email-with-a-verification-link-to-a-user-that-has-an-email-matching-the-one-in-the-request-b
      x-api-path-slug: usersemailverifysend-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Send
      - Verification
      - Email
  /users/login/switch:
    post:
      summary: Switch login method
      description: |-
        Switch a user's login method from using email to OAuth2/SAML/LDAP or back to email. When switching to OAuth2/SAML, account switching is not complete until the user follows the returned link and completes any steps on the OAuth2/SAML service provider.

        To switch from email to OAuth2/SAML, specify `current_service`, `new_service`, `email` and `password`.

        To switch from OAuth2/SAML to email, specify `current_service`, `new_service`, `email` and `new_password`.

        To switch from email to LDAP/AD, specify `current_service`, `new_service`, `email`, `password`, `ldap_ip` and `new_password` (this is the user's LDAP password).

        To switch from LDAP/AD to email, specify `current_service`, `new_service`, `ldap_ip`, `password` (this is the user's LDAP password), `email`  and `new_password`.

        Additionally, specify `mfa_code` when trying to switch an account on LDAP/AD or email that has MFA activated.

        ##### Permissions
        No current authentication required except when switching from OAuth2/SAML to email.
      operationId: switch-a-users-login-method-from-using-email-to-oauth2samlldap-or-back-to-email-when-switching-to-oa
      x-api-path-slug: usersloginswitch-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Switch
      - Login
      - Method
  /users/{user_id}/tokens:
    post:
      summary: Create a user access token
      description: |-
        Generate a user access token that can be used to authenticate with the Mattermost REST API.

        __Minimum server version__: 4.1

        ##### Permissions
        Must have `create_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
      operationId: generate-a-user-access-token-that-can-be-used-to-authenticate-with-the-mattermost-rest-api-minimum-s
      x-api-path-slug: usersuser-idtokens-post
      parameters:
      - in: body
        name: token
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - User
      - Access
      - Token
    get:
      summary: Get user access tokens
      description: |-
        Get a list of user access tokens for a user. Does not include the actual authentication tokens. Use query paremeters for paging.

        __Minimum server version__: 4.1

        ##### Permissions
        Must have `read_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
      operationId: get-a-list-of-user-access-tokens-for-a-user-does-not-include-the-actual-authentication-tokens-use-qu
      x-api-path-slug: usersuser-idtokens-get
      parameters:
      - in: query
        name: page
        description: The page to select
      - in: query
        name: per_page
        description: The number of tokens per page
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - User
      - Access
      - Tokens
  /users/tokens:
    get:
      summary: Get user access tokens
      description: |-
        Get a page of user access tokens for users on the system. Does not include the actual authentication tokens. Use query parameters for paging.

        __Minimum server version__: 4.7

        ##### Permissions
        Must have `manage_system` permission.
      operationId: get-a-page-of-user-access-tokens-for-users-on-the-system-does-not-include-the-actual-authentication-
      x-api-path-slug: userstokens-get
      parameters:
      - in: query
        name: page
        description: The page to select
      - in: query
        name: per_page
        description: The number of tokens per page
      responses:
        200:
          description: OK
      tags:
      - User
      - Access
      - Tokens
  /users/tokens/revoke:
    post:
      summary: Revoke a user access token
      description: |-
        Revoke a user access token and delete any sessions using the token.

        __Minimum server version__: 4.1

        ##### Permissions
        Must have `revoke_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
      operationId: revoke-a-user-access-token-and-delete-any-sessions-using-the-token-minimum-server-version--41-permis
      x-api-path-slug: userstokensrevoke-post
      parameters:
      - in: body
        name: token
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Revoke
      - User
      - Access
      - Token
  /users/tokens/{token_id}:
    get:
      summary: Get a user access token
      description: |-
        Get a user access token. Does not include the actual authentication token.

        __Minimum server version__: 4.1

        ##### Permissions
        Must have `read_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
      operationId: get-a-user-access-token-does-not-include-the-actual-authentication-token-minimum-server-version--41-
      x-api-path-slug: userstokenstoken-id-get
      parameters:
      - in: path
        name: token_id
        description: User access token GUID
      responses:
        200:
          description: OK
      tags:
      - User
      - Access
      - Token
  /users/tokens/disable:
    post:
      summary: Disable personal access token
      description: |-
        Disable a personal access token and delete any sessions using the token. The token can be re-enabled using `/users/tokens/enable`.

        __Minimum server version__: 4.4

        ##### Permissions
        Must have `revoke_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
      operationId: disable-a-personal-access-token-and-delete-any-sessions-using-the-token-the-token-can-be-reenabled-u
      x-api-path-slug: userstokensdisable-post
      parameters:
      - in: body
        name: token
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Disable
      - Personal
      - Access
      - Token
  /users/tokens/enable:
    post:
      summary: Enable personal access token
      description: |-
        Re-enable a personal access token that has been disabled.

        __Minimum server version__: 4.4

        ##### Permissions
        Must have `create_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
      operationId: reenable-a-personal-access-token-that-has-been-disabled-minimum-server-version--44-permissionsmust-h
      x-api-path-slug: userstokensenable-post
      parameters:
      - in: body
        name: token
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Enable
      - Personal
      - Access
      - Token
  /users/tokens/search:
    post:
      summary: Search tokens
      description: |-
        Get a list of tokens based on search criteria provided in the request body. Searches are done against the token id, user id and username.

        __Minimum server version__: 4.7

        ##### Permissions
        Must have `manage_system` permission.
      operationId: get-a-list-of-tokens-based-on-search-criteria-provided-in-the-request-body-searches-are-done-against
      x-api-path-slug: userstokenssearch-post
      parameters:
      - in: body
        name: body
        description: Search criteria
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Search
      - Tokens
  /users/{user_id}/auth:
    put:
      summary: Update a users authentication method
      description: |-
        Updates a user's authentication method. This can be used to change them to/from LDAP authentication for example.

        __Minimum server version__: 4.6
        ##### Permissions
        Must have the `edit_other_users` permission.
      operationId: updates-a-users-authentication-method-this-can-be-used-to-change-them-tofrom-ldap-authentication-for
      x-api-path-slug: usersuser-idauth-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Users
      - Authentication
      - Method
  /users/{user_id}/status:
    get:
      summary: Get user status
      description: |-
        Get user status by id from the server.
        ##### Permissions
        Must be authenticated.
      operationId: get-user-status-by-id-from-the-server-permissionsmust-be-authenticated
      x-api-path-slug: usersuser-idstatus-get
      parameters:
      - in: path
        name: user_id
        description: User ID
      responses:
        200:
          description: OK
      tags:
      - User
      - Status
    put:
      summary: Update user status
      description: |-
        Manually set a user's status. When setting a user's status, the status will remain that value until set "online" again, which will return the status to being automatically updated based on user activity.
        ##### Permissions
        Must have `edit_other_users` permission for the team.
      operationId: manually-set-a-users-status-when-setting-a-users-status-the-status-will-remain-that-value-until-set-
      x-api-path-slug: usersuser-idstatus-put
      parameters:
      - in: body
        name: body
        description: Status object that is to be updated
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: user_id
        description: User ID
      responses:
        200:
          description: OK
      tags:
      - User
      - Status
  /users/status/ids:
    post:
      summary: Get user statuses by id
      description: |-
        Get a list of user statuses by id from the server.
        ##### Permissions
        Must be authenticated.
      operationId: get-a-list-of-user-statuses-by-id-from-the-server-permissionsmust-be-authenticated
      x-api-path-slug: usersstatusids-post
      parameters:
      - in: body
        name: post
        description: List of user ids to fetch
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - User
      - Statuses
      - By
      - Id
  /teams:
    post:
      summary: Create a team
      description: |-
        Create a new team on the system.
        ##### Permissions
        Must be authenticated and have the `create_team` permission.
      operationId: create-a-new-team-on-the-system-permissionsmust-be-authenticated-and-have-the-create-team-permission
      x-api-path-slug: teams-post
      parameters:
      - in: body
        name: body
        description: Team that is to be created
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Team
    get:
      summary: Get teams
      description: |-
        For regular users only returns open teams. Users with the "manage_system" permission will return teams regardless of type. The result is based on query string parameters - page and per_page.
        ##### Permissions
        Must be authenticated. "manage_system" permission is required to show all teams.
      operationId: for-regular-users-only-returns-open-teams-users-with-the-manage-system-permission-will-return-teams-
      x-api-path-slug: teams-get
      parameters:
      - in: query
        name: page
        description: The page to select
      - in: query
        name: per_page
        description: The number of teams per page
      responses:
        200:
          description: OK
      tags:
      - Teams
  /teams/{team_id}:
    get:
      summary: Get a team
      description: |-
        Get a team on the system.
        ##### Permissions
        Must be authenticated and have the `view_team` permission.
      operationId: get-a-team-on-the-system-permissionsmust-be-authenticated-and-have-the-view-team-permission
      x-api-path-slug: teamsteam-id-get
      parameters:
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Team
    put:
      summary: Update a team
      description: |-
        Update a team by providing the team object. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
        ##### Permissions
        Must have the `manage_team` permission.
      operationId: update-a-team-by-providing-the-team-object-the-fields-that-can-be-updated-are-defined-in-the-request
      x-api-path-slug: teamsteam-id-put
      parameters:
      - in: body
        name: body
        description: Team to update
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Team
    delete:
      summary: Delete a team
      description: |-
        Soft deletes a team, by marking the team as deleted in the database. Soft deleted teams will not be accessible in the user interface.

        Optionally use the permanent query parameter to hard delete the team for compliance reasons.
        ##### Permissions
        Must have the `manage_team` permission.
      operationId: soft-deletes-a-team-by-marking-the-team-as-deleted-in-the-database-soft-deleted-teams-will-not-be-ac
      x-api-path-slug: teamsteam-id-delete
      parameters:
      - in: query
        name: permanent
        description: Permanently delete the team, to be used for compliance reasons
          only
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Team
  /teams/{team_id}/patch:
    put:
      summary: Patch a team
      description: |-
        Partially update a team by providing only the fields you want to update. Omitted fields will not be updated. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
        ##### Permissions
        Must have the `manage_team` permission.
      operationId: partially-update-a-team-by-providing-only-the-fields-you-want-to-update-omitted-fields-will-not-be-u
      x-api-path-slug: teamsteam-idpatch-put
      parameters:
      - in: body
        name: body
        description: Team object that is to be updated
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Team
  /teams/name/{name}:
    get:
      summary: Get a team by name
      description: |-
        Get a team based on provided name string
        ##### Permissions
        Must be authenticated, team type is open and have the `view_team` permission.
      operationId: get-a-team-based-on-provided-name-string-permissionsmust-be-authenticated-team-type-is-open-and-have
      x-api-path-slug: teamsnamename-get
      parameters:
      - in: path
        name: name
        description: Team Name
      responses:
        200:
          description: OK
      tags:
      - Team
      - By
      - Name
  /teams/search:
    post:
      summary: Search teams
      description: |-
        Search teams based on search term provided in the request body.
        ##### Permissions
        Logged in user only shows open teams
        Logged in user with "manage_system" permission shows all teams
      operationId: search-teams-based-on-search-term-provided-in-the-request-body-permissionslogged-in-user-only-shows-
      x-api-path-slug: teamssearch-post
      parameters:
      - in: body
        name: body
        description: Search criteria
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Search
      - Teams
  /teams/name/{name}/exists:
    get:
      summary: Check if team exists
      description: Check if the team exists based on a team name.
      operationId: check-if-the-team-exists-based-on-a-team-name
      x-api-path-slug: teamsnamenameexists-get
      parameters:
      - in: path
        name: name
        description: Team Name
      responses:
        200:
          description: OK
      tags:
      - Check
      - If
      - Team
      - Exists
  /users/{user_id}/teams:
    get:
      summary: Get a user's teams
      description: |-
        Get a list of teams that a user is on.
        ##### Permissions
        Must be authenticated as the user or have the `manage_system` permission.
      operationId: get-a-list-of-teams-that-a-user-is-on-permissionsmust-be-authenticated-as-the-user-or-have-the-manag
      x-api-path-slug: usersuser-idteams-get
      parameters:
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Users
      - Teams
  /teams/{team_id}/members:
    get:
      summary: Get team members
      description: |-
        Get a page team members list based on query string parameters - team id, page and per page.
        ##### Permissions
        Must be authenticated and have the `view_team` permission.
      operationId: get-a-page-team-members-list-based-on-query-string-parameters--team-id-page-and-per-page-permissions
      x-api-path-slug: teamsteam-idmembers-get
      parameters:
      - in: query
        name: page
        description: The page to select
      - in: query
        name: per_page
        description: The number of users per page
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Team
      - Members
    post:
      summary: Add user to team
      description: |-
        Add user to the team by user_id.
        ##### Permissions
        Must be authenticated and team be open to add self. For adding another user, authenticated user must have the `add_user_to_team` permission.
      operationId: add-user-to-the-team-by-user-id-permissionsmust-be-authenticated-and-team-be-open-to-add-self-for-ad
      x-api-path-slug: teamsteam-idmembers-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - User
      - To
      - Team
  /teams/members/invite:
    post:
      summary: Add user to team from invite
      description: |-
        Using either an invite id or hash/data pair from an email invite link, add a user to a team.
        ##### Permissions
        Must be authenticated.
      operationId: using-either-an-invite-id-or-hashdata-pair-from-an-email-invite-link-add-a-user-to-a-team-permission
      x-api-path-slug: teamsmembersinvite-post
      parameters:
      - in: query
        name: data
        description: Data with time and team id
      - in: query
        name: hash
        description: Hash value with time, team id and and InviteSaltId
      - in: query
        name: invite_id
        description: Invite id to add user to the team
      responses:
        200:
          description: OK
      tags:
      - User
      - To
      - Team
      - From
      - Invite
  /teams/{team_id}/members/batch:
    post:
      summary: Add multiple users to team
      description: |-
        Add a number of users to the team by user_id.
        ##### Permissions
        Must be authenticated. Authenticated user must have the `add_user_to_team` permission.
      operationId: add-a-number-of-users-to-the-team-by-user-id-permissionsmust-be-authenticated-authenticated-user-mus
      x-api-path-slug: teamsteam-idmembersbatch-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Multiple
      - Users
      - To
      - Team
  /users/{user_id}/teams/members:
    get:
      summary: Get team members for a user
      description: |-
        Get a list of team members for a user. Useful for getting the ids of teams the user is on and the roles they have in those teams.
        ##### Permissions
        Must be logged in as the user or have the `edit_other_users` permission.
      operationId: get-a-list-of-team-members-for-a-user-useful-for-getting-the-ids-of-teams-the-user-is-on-and-the-rol
      x-api-path-slug: usersuser-idteamsmembers-get
      parameters:
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Team
      - Membersa
      - User
  /teams/{team_id}/members/{user_id}:
    get:
      summary: Get a team member
      description: |-
        Get a team member on the system.
        ##### Permissions
        Must be authenticated and have the `view_team` permission.
      operationId: get-a-team-member-on-the-system-permissionsmust-be-authenticated-and-have-the-view-team-permission
      x-api-path-slug: teamsteam-idmembersuser-id-get
      parameters:
      - in: path
        name: team_id
        description: Team GUID
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Team
      - Member
    delete:
      summary: Remove user from team
      description: |-
        Delete the team member object for a user, effectively removing them from a team.
        ##### Permissions
        Must be logged in as the user or have the `remove_user_from_team` permission.
      operationId: delete-the-team-member-object-for-a-user-effectively-removing-them-from-a-team-permissionsmust-be-lo
      x-api-path-slug: teamsteam-idmembersuser-id-delete
      parameters:
      - in: path
        name: team_id
        description: Team GUID
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Remove
      - User
      - From
      - Team
  /teams/{team_id}/members/ids:
    post:
      summary: Get team members by ids
      description: |-
        Get a list of team members based on a provided array of user ids.
        ##### Permissions
        Must have `view_team` permission for the team.
      operationId: get-a-list-of-team-members-based-on-a-provided-array-of-user-ids-permissionsmust-have-view-team-perm
      x-api-path-slug: teamsteam-idmembersids-post
      parameters:
      - in: body
        name: body
        description: List of user ids
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Team
      - Members
      - By
      - Ids
  /teams/{team_id}/stats:
    get:
      summary: Get a team stats
      description: |-
        Get a team stats on the system.
        ##### Permissions
        Must be authenticated and have the `view_team` permission.
      operationId: get-a-team-stats-on-the-system-permissionsmust-be-authenticated-and-have-the-view-team-permission
      x-api-path-slug: teamsteam-idstats-get
      parameters:
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Team
      - Stats
  /teams/{team_id}/image:
    get:
      summary: Get the team icon
      description: |-
        Get the team icon of the team.

        __Minimum server version__: 4.9

        ##### Permissions
        User must be authenticated. In addition, team must be open or the user must have the `view_team` permission.
      operationId: get-the-team-icon-of-the-team-minimum-server-version--49-permissionsuser-must-be-authenticated-in-ad
      x-api-path-slug: teamsteam-idimage-get
      parameters:
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Team
      - Icon
    post:
      summary: Sets the team icon
      description: |-
        Sets the team icon for the team.

        __Minimum server version__: 4.9

        ##### Permissions
        Must be authenticated and have the `manage_team` permission.
      operationId: sets-the-team-icon-for-the-team-minimum-server-version--49-permissionsmust-be-authenticated-and-have
      x-api-path-slug: teamsteam-idimage-post
      parameters:
      - in: formData
        name: image
        description: The image to be uploaded
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Sets
      - Team
      - Icon
  /teams/{team_id}/members/{user_id}/roles:
    put:
      summary: Update a team member roles
      description: |-
        Update a team member roles. Valid team roles are "team_user", "team_admin" or both of them. Overwrites any previously assigned team roles.
        ##### Permissions
        Must be authenticated and have the `manage_team_roles` permission.
      operationId: update-a-team-member-roles-valid-team-roles-are-team-user-team-admin-or-both-of-them-overwrites-any-
      x-api-path-slug: teamsteam-idmembersuser-idroles-put
      parameters:
      - in: body
        name: body
        description: Space-delimited team roles to assign to the user
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: team_id
        description: Team GUID
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Team
      - Member
      - Roles
  /users/{user_id}/teams/unread:
    get:
      summary: Get team unreads for a user
      description: |-
        Get the count for unread messages and mentions in the teams the user is a member of.
        ##### Permissions
        Must be logged in.
      operationId: get-the-count-for-unread-messages-and-mentions-in-the-teams-the-user-is-a-member-of-permissionsmust-
      x-api-path-slug: usersuser-idteamsunread-get
      parameters:
      - in: query
        name: exclude_team
        description: Optional team id to be excluded from the results
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Team
      - Unreadsa
      - User
  /users/{user_id}/teams/{team_id}/unread:
    get:
      summary: Get unreads for a team
      description: |-
        Get the unread mention and message counts for a team for the specified user.
        ##### Permissions
        Must be the user or have `edit_other_users` permission and have `view_team` permission for the team.
      operationId: get-the-unread-mention-and-message-counts-for-a-team-for-the-specified-user-permissionsmust-be-the-u
      x-api-path-slug: usersuser-idteamsteam-idunread-get
      parameters:
      - in: path
        name: team_id
        description: Team GUID
      - in: path
        name: user_id
        description: User GUID
      responses:
        200:
          description: OK
      tags:
      - Unreadsa
      - Team
  /teams/{team_id}/invite/email:
    post:
      summary: Invite users to the team by email
      description: |-
        Invite users to the existing team usign the user's email.
        ##### Permissions
        Must have `invite_to_team` permission for the team.
      operationId: invite-users-to-the-existing-team-usign-the-users-email-permissionsmust-have-invite-to-team-permissi
      x-api-path-slug: teamsteam-idinviteemail-post
      parameters:
      - in: body
        name: body
        description: List of users email
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Invite
      - Users
      - To
      - Team
      - By
      - Email
  /teams/{team_id}/import:
    post:
      summary: Import a Team from other application
      description: |-
        Import a team into a existing team. Import users, channels, posts, hooks.
        ##### Permissions
        Must have `permission_import_team` permission.
      operationId: import-a-team-into-a-existing-team-import-users-channels-posts-hooks-permissionsmust-have-permission
      x-api-path-slug: teamsteam-idimport-post
      parameters:
      - in: formData
        name: file
        description: A file to be uploaded in zip format
      - in: formData
        name: filesize
        description: The size of the zip file to be imported
      - in: formData
        name: importFrom
        description: String that defines from which application the team was exported
          to be imported into Mattermost
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - Import
      - Team
      - From
      - Other
      - Application
  /teams/invite/{invite_id}:
    get:
      summary: Get invite info for a team
      description: |-
        Get the `name`, `display_name`, `description` and `id` for a team from the invite id.

        __Minimum server version__: 4.0

        ##### Permissions
        No authentication required.
      operationId: get-the-name-display-name-description-and-id-for-a-team-from-the-invite-id-minimum-server-version--4
      x-api-path-slug: teamsinviteinvite-id-get
      parameters:
      - in: path
        name: invite_id
        description: Invite id for a team
      responses:
        200:
          description: OK
      tags:
      - Invite
      - Infoa
      - Team
  /channels:
    post:
      summary: Create a channel
      description: |-
        Create a new channel.
        ##### Permissions
        If creating a public channel, `create_public_channel` permission is required. If creating a private channel, `create_private_channel` permission is required.
      operationId: create-a-new-channel-permissionsif-creating-a-public-channel-create-public-channel-permission-is-req
      x-api-path-slug: channels-post
      parameters:
      - in: body
        name: body
        description: Channel object to be created
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Channel
  /channels/direct:
    post:
      summary: Create a direct message channel
      description: |-
        Create a new direct message channel between two users.
        ##### Permissions
        Must be one of the two users and have `create_direct_channel` permission. Having the `manage_system` permission voids the previous requirements.
      operationId: create-a-new-direct-message-channel-between-two-users-permissionsmust-be-one-of-the-two-users-and-ha
      x-api-path-slug: channelsdirect-post
      parameters:
      - in: body
        name: body
        description: The two user ids to be in the direct message
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Direct
      - Message
      - Channel
  /channels/group:
    post:
      summary: Create a group message channel
      description: |-
        Create a new group message channel to group of users. If the logged in user's id is not included in the list, it will be appended to the end.
        ##### Permissions
        Must have `create_group_channel` permission.
      operationId: create-a-new-group-message-channel-to-group-of-users-if-the-logged-in-users-id-is-not-included-in-th
      x-api-path-slug: channelsgroup-post
      parameters:
      - in: body
        name: body
        description: User ids to be in the group message channel
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Group
      - Message
      - Channel
  /teams/{team_id}/channels/ids:
    post:
      summary: Get a list of channels by ids
      description: |-
        Get a list of public channels on a team by id.
        ##### Permissions
        `view_team` for the team the channels are on.
      operationId: get-a-list-of-public-channels-on-a-team-by-id-permissionsview-team-for-the-team-the-channels-are-on
      x-api-path-slug: teamsteam-idchannelsids-post
      parameters:
      - in: body
        name: body
        description: List of channel ids
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: team_id
        description: Team GUID
      responses:
        200:
          description: OK
      tags:
      - List
      - Of
      - Channels
      - By
      - Ids
  /channels/{channel_id}:
    get:
      summary: Get a channel
      description: |-
        Get channel from the provided channel id string.
        ##### Permissions
        `read_channel` permission for the channel.
      operationId: get-channel-from-the-provided-channel-id-string-permissionsread-channel-permission-for-the-channel
      x-api-path-slug: channelschannel-id-get
      parameters:
      - in: path
        name: channel_id
        description: Channel GUID
      responses:
        200:
          description: OK
      tags:
      - Channel
    put:
      summary: Update a channel
      description: |-
        Update a channel. The fields that can be updated are listed as paramters. Omitted fields will be treated as blanks.
        ##### Permissions
        If updating a public channel, `manage_public_channel_members` permission is required. If updating a private channel, `manage_private_channel_members` permission is required.
      operationId: update-a-channel-the-fields-that-can-be-updated-are-listed-as-paramters-omitted-fields-will-be-treat
      x-api-path-slug: channelschannel-id-put
      parameters:
      - in: body
        name: body
        description: Channel object to be updated
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: channel_id
        description: Channel GUID
      responses:
        200:
          description: OK
      tags:
      - Channel
    delete:
      summary: Delete a channel
      description: |-
        Soft deletes a channel, by marking the channel as deleted in the database. Soft deleted channels will not be accessible in the user interface.
        ##### Permissions
        `delete_public_channel` permission if the channel is public,
        `delete_private_channel` permission if the channel is private,
        or have `manage_system` permission.
      operationId: soft-deletes-a-channel-by-marking-the-channel-as-deleted-in-the-database-soft-deleted-channels-will-
      x-api-path-slug: channelschannel-id-delete
      parameters:
      - in: path
        name: channel_id
        description: Channel GUID
      responses:
        200:
          description: OK
      tags:
      - Channel
  /channels/{channel_id}/patch:
    put:
      summary: Patch a channel
      description: |-
        Partially update a channel by providing only the fields you want to update. Omitted fields will not be updated. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
        ##### Permissions
        If updating a public channel, `manage_public_channel_members` permission is required. If updating a private channel, `manage_private_channel_members` permission is required.
      operationId: partially-update-a-channel-by-providing-only-the-fields-you-want-to-update-omitted-fields-will-not-b
      x-api-path-slug: channelschannel-idpatch-put
      parameters:
      - in: body
        name: body
        description: Channel object to be updated
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: channel_id
        description: Channel GUID
      responses:
        200:
          description: OK
      tags:
      - Channel
  /channels/{channel_id}/convert:
    post:
      summary: Convert a channel from public to private
      description: |-
        Convert into private channel from the provided channel id string.

        __Minimum server version__: 4.10

        ##### Permissions
        Must have `manage_system` permission.
      operationId: convert-into-private-channel-from-the-provided-channel-id-string-minimum-server-version--410-permiss
      x-api-path-slug: channelschannel-idconvert-post
      parameters:
      - in: path
        name: channel_id
        description: Channel GUID
      responses:
        200:
          description: OK
      tags:
      - Convert
      - Channel
      - From
      - Public
      - To
      - Private
  /channels/{channel_id}/restore:
    post:
      summary: Restore a channel
      description: |-
        Restore channel from the provided channel id string.

        __Minimum server version__: 3.10

        ##### Permissions
        `manage_team` permission for the team of channel.
      operationId: restore-channel-from-the-provided-channel-id-string-minimum-server-version--310-permissionsmanage-te
      x-api-path-slug: channelschannel-idrestore-post
      parameters:
      - in: path
        name: channel_id
        description: Channel GUID
      responses:
        200:
          description: OK
      tags:
      - Restore
      - Channel
  /channels/{channel_id}/stats:
    get:
      summary: Get channel statistics
      description: |-
        Get statistics for a channel.
        ##### Permissions
        Must have the `read_channel` permission.
      operationId: get-statistics-for-a-channel-permissionsmust-have-the-read-channel-permission
      x-api-path-slug: channelschannel-idstats-get
      parameters:
      - in: path
        name: channel_id
        description: Channel GUID
      responses:
        200:
          description: OK
      tags:
      - Channel
      - Statistics
  /channels/{channel_id}/pinned:
    get:
      summary: Get a channels pinned posts
      description: Get a list of pinned posts for channel.
      operationId: get-a-list-of-pinned-posts-for-channel
      x-api-path-slug: channelschannel-idpinned-get
      parameters:
      - in: path
        name: channel_id
        description: Channel GUID
      responses:
        200:
          description: OK
      tags:
      - Channels
      - Pinned
      - Posts
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