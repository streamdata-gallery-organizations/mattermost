---
swagger: "2.0"
x-collection-name: Mattermost
x-complete: 0
info:
  title: Mattermost API Disable personal access token
  description: |-
    Disable a personal access token and delete any sessions using the token. The token can be re-enabled using `/users/tokens/enable`.

    __Minimum server version__: 4.4

    ##### Permissions
    Must have `revoke_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
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