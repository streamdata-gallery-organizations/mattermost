---
name: Mattermost
x-slug: mattermost
description: Open source, private cloud Slack-alternative, Workplace messaging for
  web, PCs and phones. MIT-licensed. Hundreds of contributors. 14 languages. Secure,
  configurable, and scalable from teams to the enterprise.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
x-kinRank: "8"
x-alexaRank: "95684"
tags: Mattermost
created: "2018-06-20"
modified: "2018-06-20"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/apis.md
specificationVersion: "0.14"
apis:
- name: Mattermost API Create a user
  x-api-slug: mattermost-api
  description: |-
    Create a new user on the system.
    ##### Permissions
    No permission required but user creation can be controlled by server configuration.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users
  tags: User
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/users-post-openapi.md
- name: Mattermost API Get users
  x-api-slug: mattermost-api
  description: |-
    Get a page of a list of users. Based on query string parameters, select users from a team, channel, or select users not in a specific channel.

    Since server version 4.0, some basic sorting is available using the `sort` query parameter. Sorting is currently only supported when selecting users on a team.
    ##### Permissions
    Requires an active session and (if specified) membership to the channel or team being selected from.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users
  tags: Users
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/users-get-openapi.md
- name: Mattermost API Get users by ids
  x-api-slug: mattermost-api
  description: |-
    Get a list of users based on a provided list of user ids.
    ##### Permissions
    Requires an active session but no other permissions.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/ids
  tags: Users,By,Ids
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersids-post-openapi.md
- name: Mattermost API Get users by usernames
  x-api-slug: mattermost-api
  description: |-
    Get a list of users based on a provided list of usernames.
    ##### Permissions
    Requires an active session but no other permissions.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/usernames
  tags: Users,By,Usernames
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersusernames-post-openapi.md
- name: Mattermost API Search users
  x-api-slug: mattermost-api
  description: |-
    Get a list of users based on search criteria provided in the request body. Searches are typically done against username, full name, nickname and email unless otherwise configured by the server.
    ##### Permissions
    Requires an active session and `read_channel` and/or `view_team` permissions for any channels or teams specified in the request body.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/search
  tags: Search,Users
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/userssearch-post-openapi.md
- name: Mattermost API Autocomplete users
  x-api-slug: mattermost-api
  description: |-
    Get a list of users for the purpose of autocompleting based on the provided search term. Specify a combination of `team_id` and `channel_id` to filter results further.
    ##### Permissions
    Requires an active session and `view_team` and `read_channel` on any teams or channels used to filter the results further.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/autocomplete
  tags: Autocomplete,Users
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersautocomplete-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersautocomplete-get-openapi.md
- name: Mattermost API Get a user
  x-api-slug: mattermost-api
  description: |-
    Get a user a object. Sensitive information will be sanitized out.
    ##### Permissions
    Requires an active session but no other permissions.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}
  tags: User
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-id-get-openapi.md
- name: Mattermost API Update a user
  x-api-slug: mattermost-api
  description: |-
    Update a user by providing the user object. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}
  tags: User
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-id-put-openapi.md
- name: Mattermost API Deactivate a user account.
  x-api-slug: mattermost-api
  description: |-
    Deactivates the user by archiving its user object.
    ##### Permissions
    Must be logged in as the user being deactivated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}
  tags: Deactivate,User,Account.
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-id-delete-openapi.md
- name: Mattermost API Patch a user
  x-api-slug: mattermost-api
  description: |-
    Partially update a user by providing only the fields you want to update. Omitted fields will not be updated. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/patch
  tags: User
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idpatch-put-openapi.md
- name: Mattermost API Update a user's roles
  x-api-slug: mattermost-api
  description: |-
    Update a user's system-level roles. Valid user roles are "system_user", "system_admin" or both of them. Overwrites any previously assigned system-level roles.
    ##### Permissions
    Must have the `manage_roles` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/roles
  tags: Users,Roles
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idroles-put-openapi.md
- name: Mattermost API Update user active status
  x-api-slug: mattermost-api
  description: |-
    Update user active or inactive status.

    __Since server version 4.6, users using a SSO provider to login can be activated or deactivated with this endpoint. However, if their activation status in Mattermost does not reflect their status in the SSO provider, the next synchronization or login by that user will reset the activation status to that of their account in the SSO provider. Server versions 4.5 and before do not allow activation or deactivation of SSO users from this endpoint.__
    ##### Permissions
    User can deactivate themself.
    User with `manage_system` permission can activate or deactivate a user.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/active
  tags: User,Active,Status
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idactive-put-openapi.md
- name: Mattermost API Get user's profile image
  x-api-slug: mattermost-api
  description: |-
    Get a user's profile image based on user_id string parameter.
    ##### Permissions
    Must be logged in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/image
  tags: Users,Profile,Image
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idimage-get-openapi.md
- name: Mattermost API Set user's profile image
  x-api-slug: mattermost-api
  description: |-
    Set a user's profile image based on user_id string parameter.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/image
  tags: Set,Users,Profile,Image
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idimage-post-openapi.md
- name: Mattermost API Get a user by username
  x-api-slug: mattermost-api
  description: |-
    Get a user object by providing a username. Sensitive information will be sanitized out.
    ##### Permissions
    Requires an active session but no other permissions.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/username/{username}
  tags: User,By,Username
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersusernameusername-get-openapi.md
- name: Mattermost API Reset password
  x-api-slug: mattermost-api
  description: |-
    Update the password for a user using a one-use, timed recovery code tied to the user's account. Only works for non-SSO users.
    ##### Permissions
    No permissions required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/password/reset
  tags: Reset,Password
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/userspasswordreset-post-openapi.md
- name: Mattermost API Update a user's MFA
  x-api-slug: mattermost-api
  description: |-
    Activates multi-factor authentication for the user if `activate` is true and a valid `code` is provided. If activate is false, then `code` is not required and multi-factor authentication is disabled for the user.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/mfa
  tags: Users,MFA
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idmfa-put-openapi.md
- name: Mattermost API Generate MFA secret
  x-api-slug: mattermost-api
  description: |-
    Generates an multi-factor authentication secret for a user and returns it as a string and as base64 encoded QR code image.
    ##### Permissions
    Must be logged in as the user or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/mfa/generate
  tags: Generate,MFA,Secret
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idmfagenerate-post-openapi.md
- name: Mattermost API Check MFA
  x-api-slug: mattermost-api
  description: |-
    Check if a user has multi-factor authentication active on their account by providing a login id. Used to check whether an MFA code needs to be provided when logging in.
    ##### Permissions
    No permission required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/mfa
  tags: Check,MFA
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersmfa-post-openapi.md
- name: Mattermost API Update a user's password
  x-api-slug: mattermost-api
  description: |-
    Update a user's password. New password must meet password policy set by server configuration. Current password is required if you're updating your own password.
    ##### Permissions
    Must be logged in as the user the password is being changed for or have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/password
  tags: Users,Password
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idpassword-put-openapi.md
- name: Mattermost API Send password reset email
  x-api-slug: mattermost-api
  description: |-
    Send an email containing a link for resetting the user's password. The link will contain a one-use, timed recovery code tied to the user's account. Only works for non-SSO users.
    ##### Permissions
    No permissions required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/password/reset/send
  tags: Send,Password,Reset,Email
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/userspasswordresetsend-post-openapi.md
- name: Mattermost API Get a user by email
  x-api-slug: mattermost-api
  description: |-
    Get a user object by providing a user email. Sensitive information will be sanitized out.
    ##### Permissions
    Requires an active session but no other permissions.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/email/{email}
  tags: User,By,Email
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersemailemail-get-openapi.md
- name: Mattermost API Get user's sessions
  x-api-slug: mattermost-api
  description: |-
    Get a list of sessions by providing the user GUID. Sensitive information will be sanitized out.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/sessions
  tags: Users,Sessions
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idsessions-get-openapi.md
- name: Mattermost API Revoke a user session
  x-api-slug: mattermost-api
  description: |-
    Revokes a user session from the provided user id and session id strings.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/sessions/revoke
  tags: Revoke,User,Session
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idsessionsrevoke-post-openapi.md
- name: Mattermost API Revoke all active sessions for a user
  x-api-slug: mattermost-api
  description: |-
    Revokes all user sessions from the provided user id and session id strings.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
    __Minimum server version__: 4.4
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/sessions/revoke/all
  tags: Revoke,,Active,Sessionsa,User
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idsessionsrevokeall-post-openapi.md
- name: Mattermost API Attach mobile device
  x-api-slug: mattermost-api
  description: |-
    Attach a mobile device id to the currently logged in session. This will enable push notiofications for a user, if configured by the server.
    ##### Permissions
    Must be authenticated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/sessions/device
  tags: Attach,Mobile,Device
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/userssessionsdevice-put-openapi.md
- name: Mattermost API Get users audits
  x-api-slug: mattermost-api
  description: |-
    Get a list of audit by providing the user GUID.
    ##### Permissions
    Must be logged in as the user or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/audits
  tags: Users,Audits
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idaudits-get-openapi.md
- name: Mattermost API Verify user email
  x-api-slug: mattermost-api
  description: |-
    Verify the email used by a user to sign-up their account with.
    ##### Permissions
    No permissions required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/email/verify
  tags: Verify,User,Email
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersemailverify-post-openapi.md
- name: Mattermost API Send verification email
  x-api-slug: mattermost-api
  description: |-
    Send an email with a verification link to a user that has an email matching the one in the request body. This endpoint will return success even if the email does not match any users on the system.
    ##### Permissions
    No permissions required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/email/verify/send
  tags: Send,Verification,Email
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersemailverifysend-post-openapi.md
- name: Mattermost API Switch login method
  x-api-slug: mattermost-api
  description: |-
    Switch a user's login method from using email to OAuth2/SAML/LDAP or back to email. When switching to OAuth2/SAML, account switching is not complete until the user follows the returned link and completes any steps on the OAuth2/SAML service provider.

    To switch from email to OAuth2/SAML, specify `current_service`, `new_service`, `email` and `password`.

    To switch from OAuth2/SAML to email, specify `current_service`, `new_service`, `email` and `new_password`.

    To switch from email to LDAP/AD, specify `current_service`, `new_service`, `email`, `password`, `ldap_ip` and `new_password` (this is the user's LDAP password).

    To switch from LDAP/AD to email, specify `current_service`, `new_service`, `ldap_ip`, `password` (this is the user's LDAP password), `email`  and `new_password`.

    Additionally, specify `mfa_code` when trying to switch an account on LDAP/AD or email that has MFA activated.

    ##### Permissions
    No current authentication required except when switching from OAuth2/SAML to email.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/login/switch
  tags: Switch,Login,Method
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersloginswitch-post-openapi.md
- name: Mattermost API Create a user access token
  x-api-slug: mattermost-api
  description: |-
    Generate a user access token that can be used to authenticate with the Mattermost REST API.

    __Minimum server version__: 4.1

    ##### Permissions
    Must have `create_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/tokens
  tags: User,Access,Token
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idtokens-post-openapi.md
- name: Mattermost API Get user access tokens
  x-api-slug: mattermost-api
  description: |-
    Get a list of user access tokens for a user. Does not include the actual authentication tokens. Use query paremeters for paging.

    __Minimum server version__: 4.1

    ##### Permissions
    Must have `read_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/tokens
  tags: User,Access,Tokens
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idtokens-get-openapi.md
- name: Mattermost API Get user access tokens
  x-api-slug: mattermost-api
  description: |-
    Get a page of user access tokens for users on the system. Does not include the actual authentication tokens. Use query parameters for paging.

    __Minimum server version__: 4.7

    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/tokens
  tags: User,Access,Tokens
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/userstokens-get-openapi.md
- name: Mattermost API Revoke a user access token
  x-api-slug: mattermost-api
  description: |-
    Revoke a user access token and delete any sessions using the token.

    __Minimum server version__: 4.1

    ##### Permissions
    Must have `revoke_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/tokens/revoke
  tags: Revoke,User,Access,Token
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/userstokensrevoke-post-openapi.md
- name: Mattermost API Get a user access token
  x-api-slug: mattermost-api
  description: |-
    Get a user access token. Does not include the actual authentication token.

    __Minimum server version__: 4.1

    ##### Permissions
    Must have `read_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/tokens/{token_id}
  tags: User,Access,Token
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/userstokenstoken-id-get-openapi.md
- name: Mattermost API Disable personal access token
  x-api-slug: mattermost-api
  description: |-
    Disable a personal access token and delete any sessions using the token. The token can be re-enabled using `/users/tokens/enable`.

    __Minimum server version__: 4.4

    ##### Permissions
    Must have `revoke_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/tokens/disable
  tags: Disable,Personal,Access,Token
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/userstokensdisable-post-openapi.md
- name: Mattermost API Enable personal access token
  x-api-slug: mattermost-api
  description: |-
    Re-enable a personal access token that has been disabled.

    __Minimum server version__: 4.4

    ##### Permissions
    Must have `create_user_access_token` permission. For non-self requests, must also have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/tokens/enable
  tags: Enable,Personal,Access,Token
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/userstokensenable-post-openapi.md
- name: Mattermost API Search tokens
  x-api-slug: mattermost-api
  description: |-
    Get a list of tokens based on search criteria provided in the request body. Searches are done against the token id, user id and username.

    __Minimum server version__: 4.7

    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/tokens/search
  tags: Search,Tokens
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/userstokenssearch-post-openapi.md
- name: Mattermost API Update a users authentication method
  x-api-slug: mattermost-api
  description: |-
    Updates a user's authentication method. This can be used to change them to/from LDAP authentication for example.

    __Minimum server version__: 4.6
    ##### Permissions
    Must have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/auth
  tags: Users,Authentication,Method
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idauth-put-openapi.md
- name: Mattermost API Get user status
  x-api-slug: mattermost-api
  description: |-
    Get user status by id from the server.
    ##### Permissions
    Must be authenticated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/status
  tags: User,Status
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idstatus-get-openapi.md
- name: Mattermost API Update user status
  x-api-slug: mattermost-api
  description: |-
    Manually set a user's status. When setting a user's status, the status will remain that value until set "online" again, which will return the status to being automatically updated based on user activity.
    ##### Permissions
    Must have `edit_other_users` permission for the team.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/status
  tags: User,Status
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idstatus-put-openapi.md
- name: Mattermost API Get user statuses by id
  x-api-slug: mattermost-api
  description: |-
    Get a list of user statuses by id from the server.
    ##### Permissions
    Must be authenticated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/status/ids
  tags: User,Statuses,By,Id
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersstatusids-post-openapi.md
- name: Mattermost API Create a team
  x-api-slug: mattermost-api
  description: |-
    Create a new team on the system.
    ##### Permissions
    Must be authenticated and have the `create_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams
  tags: Team
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teams-post-openapi.md
- name: Mattermost API Get teams
  x-api-slug: mattermost-api
  description: |-
    For regular users only returns open teams. Users with the "manage_system" permission will return teams regardless of type. The result is based on query string parameters - page and per_page.
    ##### Permissions
    Must be authenticated. "manage_system" permission is required to show all teams.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams
  tags: Teams
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teams-get-openapi.md
- name: Mattermost API Get a team
  x-api-slug: mattermost-api
  description: |-
    Get a team on the system.
    ##### Permissions
    Must be authenticated and have the `view_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}
  tags: Team
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-id-get-openapi.md
- name: Mattermost API Update a team
  x-api-slug: mattermost-api
  description: |-
    Update a team by providing the team object. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
    ##### Permissions
    Must have the `manage_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}
  tags: Team
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-id-put-openapi.md
- name: Mattermost API Delete a team
  x-api-slug: mattermost-api
  description: |-
    Soft deletes a team, by marking the team as deleted in the database. Soft deleted teams will not be accessible in the user interface.

    Optionally use the permanent query parameter to hard delete the team for compliance reasons.
    ##### Permissions
    Must have the `manage_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}
  tags: Team
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-id-delete-openapi.md
- name: Mattermost API Patch a team
  x-api-slug: mattermost-api
  description: |-
    Partially update a team by providing only the fields you want to update. Omitted fields will not be updated. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
    ##### Permissions
    Must have the `manage_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/patch
  tags: Team
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idpatch-put-openapi.md
- name: Mattermost API Get a team by name
  x-api-slug: mattermost-api
  description: |-
    Get a team based on provided name string
    ##### Permissions
    Must be authenticated, team type is open and have the `view_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/name/{name}
  tags: Team,By,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsnamename-get-openapi.md
- name: Mattermost API Search teams
  x-api-slug: mattermost-api
  description: |-
    Search teams based on search term provided in the request body.
    ##### Permissions
    Logged in user only shows open teams
    Logged in user with "manage_system" permission shows all teams
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/search
  tags: Search,Teams
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamssearch-post-openapi.md
- name: Mattermost API Check if team exists
  x-api-slug: mattermost-api
  description: Check if the team exists based on a team name.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/name/{name}/exists
  tags: Check,If,Team,Exists
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsnamenameexists-get-openapi.md
- name: Mattermost API Get a user's teams
  x-api-slug: mattermost-api
  description: |-
    Get a list of teams that a user is on.
    ##### Permissions
    Must be authenticated as the user or have the `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/teams
  tags: Users,Teams
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idteams-get-openapi.md
- name: Mattermost API Get team members
  x-api-slug: mattermost-api
  description: |-
    Get a page team members list based on query string parameters - team id, page and per page.
    ##### Permissions
    Must be authenticated and have the `view_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/members
  tags: Team,Members
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idmembers-get-openapi.md
- name: Mattermost API Add user to team
  x-api-slug: mattermost-api
  description: |-
    Add user to the team by user_id.
    ##### Permissions
    Must be authenticated and team be open to add self. For adding another user, authenticated user must have the `add_user_to_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/members
  tags: User,To,Team
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idmembers-post-openapi.md
- name: Mattermost API Add user to team from invite
  x-api-slug: mattermost-api
  description: |-
    Using either an invite id or hash/data pair from an email invite link, add a user to a team.
    ##### Permissions
    Must be authenticated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/members/invite
  tags: User,To,Team,From,Invite
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsmembersinvite-post-openapi.md
- name: Mattermost API Add multiple users to team
  x-api-slug: mattermost-api
  description: |-
    Add a number of users to the team by user_id.
    ##### Permissions
    Must be authenticated. Authenticated user must have the `add_user_to_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/members/batch
  tags: Multiple,Users,To,Team
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idmembersbatch-post-openapi.md
- name: Mattermost API Get team members for a user
  x-api-slug: mattermost-api
  description: |-
    Get a list of team members for a user. Useful for getting the ids of teams the user is on and the roles they have in those teams.
    ##### Permissions
    Must be logged in as the user or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/teams/members
  tags: Team,Membersa,User
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idteamsmembers-get-openapi.md
- name: Mattermost API Get a team member
  x-api-slug: mattermost-api
  description: |-
    Get a team member on the system.
    ##### Permissions
    Must be authenticated and have the `view_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/members/{user_id}
  tags: Team,Member
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idmembersuser-id-get-openapi.md
- name: Mattermost API Remove user from team
  x-api-slug: mattermost-api
  description: |-
    Delete the team member object for a user, effectively removing them from a team.
    ##### Permissions
    Must be logged in as the user or have the `remove_user_from_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/members/{user_id}
  tags: Remove,User,From,Team
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idmembersuser-id-delete-openapi.md
- name: Mattermost API Get team members by ids
  x-api-slug: mattermost-api
  description: |-
    Get a list of team members based on a provided array of user ids.
    ##### Permissions
    Must have `view_team` permission for the team.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/members/ids
  tags: Team,Members,By,Ids
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idmembersids-post-openapi.md
- name: Mattermost API Get a team stats
  x-api-slug: mattermost-api
  description: |-
    Get a team stats on the system.
    ##### Permissions
    Must be authenticated and have the `view_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/stats
  tags: Team,Stats
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idstats-get-openapi.md
- name: Mattermost API Get the team icon
  x-api-slug: mattermost-api
  description: |-
    Get the team icon of the team.

    __Minimum server version__: 4.9

    ##### Permissions
    User must be authenticated. In addition, team must be open or the user must have the `view_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/image
  tags: Team,Icon
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idimage-get-openapi.md
- name: Mattermost API Sets the team icon
  x-api-slug: mattermost-api
  description: |-
    Sets the team icon for the team.

    __Minimum server version__: 4.9

    ##### Permissions
    Must be authenticated and have the `manage_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/image
  tags: Sets,Team,Icon
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idimage-post-openapi.md
- name: Mattermost API Update a team member roles
  x-api-slug: mattermost-api
  description: |-
    Update a team member roles. Valid team roles are "team_user", "team_admin" or both of them. Overwrites any previously assigned team roles.
    ##### Permissions
    Must be authenticated and have the `manage_team_roles` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/members/{user_id}/roles
  tags: Team,Member,Roles
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idmembersuser-idroles-put-openapi.md
- name: Mattermost API Get team unreads for a user
  x-api-slug: mattermost-api
  description: |-
    Get the count for unread messages and mentions in the teams the user is a member of.
    ##### Permissions
    Must be logged in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/teams/unread
  tags: Team,Unreadsa,User
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idteamsunread-get-openapi.md
- name: Mattermost API Get unreads for a team
  x-api-slug: mattermost-api
  description: |-
    Get the unread mention and message counts for a team for the specified user.
    ##### Permissions
    Must be the user or have `edit_other_users` permission and have `view_team` permission for the team.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/teams/{team_id}/unread
  tags: Unreadsa,Team
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idteamsteam-idunread-get-openapi.md
- name: Mattermost API Invite users to the team by email
  x-api-slug: mattermost-api
  description: |-
    Invite users to the existing team usign the user's email.
    ##### Permissions
    Must have `invite_to_team` permission for the team.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/invite/email
  tags: Invite,Users,To,Team,By,Email
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idinviteemail-post-openapi.md
- name: Mattermost API Import a Team from other application
  x-api-slug: mattermost-api
  description: |-
    Import a team into a existing team. Import users, channels, posts, hooks.
    ##### Permissions
    Must have `permission_import_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/import
  tags: Import,Team,From,Other,Application
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idimport-post-openapi.md
- name: Mattermost API Get invite info for a team
  x-api-slug: mattermost-api
  description: |-
    Get the `name`, `display_name`, `description` and `id` for a team from the invite id.

    __Minimum server version__: 4.0

    ##### Permissions
    No authentication required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/invite/{invite_id}
  tags: Invite,Infoa,Team
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsinviteinvite-id-get-openapi.md
- name: Mattermost API Create a channel
  x-api-slug: mattermost-api
  description: |-
    Create a new channel.
    ##### Permissions
    If creating a public channel, `create_public_channel` permission is required. If creating a private channel, `create_private_channel` permission is required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels
  tags: Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channels-post-openapi.md
- name: Mattermost API Create a direct message channel
  x-api-slug: mattermost-api
  description: |-
    Create a new direct message channel between two users.
    ##### Permissions
    Must be one of the two users and have `create_direct_channel` permission. Having the `manage_system` permission voids the previous requirements.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/direct
  tags: Direct,Message,Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelsdirect-post-openapi.md
- name: Mattermost API Create a group message channel
  x-api-slug: mattermost-api
  description: |-
    Create a new group message channel to group of users. If the logged in user's id is not included in the list, it will be appended to the end.
    ##### Permissions
    Must have `create_group_channel` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/group
  tags: Group,Message,Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelsgroup-post-openapi.md
- name: Mattermost API Get a list of channels by ids
  x-api-slug: mattermost-api
  description: |-
    Get a list of public channels on a team by id.
    ##### Permissions
    `view_team` for the team the channels are on.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/channels/ids
  tags: List,Of,Channels,By,Ids
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idchannelsids-post-openapi.md
- name: Mattermost API Get a channel
  x-api-slug: mattermost-api
  description: |-
    Get channel from the provided channel id string.
    ##### Permissions
    `read_channel` permission for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}
  tags: Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-id-get-openapi.md
- name: Mattermost API Update a channel
  x-api-slug: mattermost-api
  description: |-
    Update a channel. The fields that can be updated are listed as paramters. Omitted fields will be treated as blanks.
    ##### Permissions
    If updating a public channel, `manage_public_channel_members` permission is required. If updating a private channel, `manage_private_channel_members` permission is required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}
  tags: Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-id-put-openapi.md
- name: Mattermost API Delete a channel
  x-api-slug: mattermost-api
  description: |-
    Soft deletes a channel, by marking the channel as deleted in the database. Soft deleted channels will not be accessible in the user interface.
    ##### Permissions
    `delete_public_channel` permission if the channel is public,
    `delete_private_channel` permission if the channel is private,
    or have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}
  tags: Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-id-delete-openapi.md
- name: Mattermost API Patch a channel
  x-api-slug: mattermost-api
  description: |-
    Partially update a channel by providing only the fields you want to update. Omitted fields will not be updated. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
    ##### Permissions
    If updating a public channel, `manage_public_channel_members` permission is required. If updating a private channel, `manage_private_channel_members` permission is required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/patch
  tags: Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idpatch-put-openapi.md
- name: Mattermost API Convert a channel from public to private
  x-api-slug: mattermost-api
  description: |-
    Convert into private channel from the provided channel id string.

    __Minimum server version__: 4.10

    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/convert
  tags: Convert,Channel,From,Public,To,Private
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idconvert-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idconvert-post-openapi.md
- name: Mattermost API Restore a channel
  x-api-slug: mattermost-api
  description: |-
    Restore channel from the provided channel id string.

    __Minimum server version__: 3.10

    ##### Permissions
    `manage_team` permission for the team of channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/restore
  tags: Restore,Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idrestore-post-openapi.md
- name: Mattermost API Get channel statistics
  x-api-slug: mattermost-api
  description: |-
    Get statistics for a channel.
    ##### Permissions
    Must have the `read_channel` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/stats
  tags: Channel,Statistics
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idstats-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idstats-get-openapi.md
- name: Mattermost API Get a channels pinned posts
  x-api-slug: mattermost-api
  description: Get a list of pinned posts for channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/pinned
  tags: Channels,Pinned,Posts
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idpinned-get-openapi.md
- name: Mattermost API Get public channels
  x-api-slug: mattermost-api
  description: |-
    Get a page of public channels on a team based on query string parameters - page and per_page.
    ##### Permissions
    Must be authenticated and have the `list_team_channels` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/channels
  tags: Public,Channels
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idchannels-get-openapi.md
- name: Mattermost API Get deleted channels
  x-api-slug: mattermost-api
  description: |-
    Get a page of deleted channels on a team based on query string parameters - team_id, page and per_page.

    __Minimum server version__: 3.10

    ##### Permissions
    Must be authenticated and have the `manage_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/channels/deleted
  tags: Deleted,Channels
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idchannelsdeleted-get-openapi.md
- name: Mattermost API Autocomplete channels
  x-api-slug: mattermost-api
  description: |-
    Autocomplete public channels on a team based on the search term provided in the request URL.

    __Minimum server version__: 4.7

    ##### Permissions
    Must have the `list_team_channels` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/channels/autocomplete
  tags: Autocomplete,Channels
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idchannelsautocomplete-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idchannelsautocomplete-get-openapi.md
- name: Mattermost API Search channels
  x-api-slug: mattermost-api
  description: |-
    Search public channels on a team based on the search term provided in the request body.
    ##### Permissions
    Must have the `list_team_channels` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/channels/search
  tags: Search,Channels
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idchannelssearch-post-openapi.md
- name: Mattermost API Get a channel by name
  x-api-slug: mattermost-api
  description: |-
    Gets channel from the provided team id and channel name strings.
    ##### Permissions
    `read_channel` permission for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/channels/name/{channel_name}
  tags: Channel,By,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idchannelsnamechannel-name-get-openapi.md
- name: Mattermost API Get a channel by name and team name
  x-api-slug: mattermost-api
  description: |-
    Gets a channel from the provided team name and channel name strings.
    ##### Permissions
    `read_channel` permission for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/name/{team_name}/channels/name/{channel_name}
  tags: Channel,By,Name,Team,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsnameteam-namechannelsnamechannel-name-get-openapi.md
- name: Mattermost API Get channel members
  x-api-slug: mattermost-api
  description: |-
    Get a page of members for a channel.
    ##### Permissions
    `read_channel` permission for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/members
  tags: Channel,Members
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idmembers-get-openapi.md
- name: Mattermost API Add user to channel
  x-api-slug: mattermost-api
  description: Add a user to a channel by creating a channel member object.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/members
  tags: User,To,Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idmembers-post-openapi.md
- name: Mattermost API Get channel members by ids
  x-api-slug: mattermost-api
  description: |-
    Get a list of channel members based on the provided user ids.
    ##### Permissions
    Must have the `read_channel` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/members/ids
  tags: Channel,Members,By,Ids
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idmembersids-post-openapi.md
- name: Mattermost API Get channel member
  x-api-slug: mattermost-api
  description: |-
    Get a channel member.
    ##### Permissions
    `read_channel` permission for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/members/{user_id}
  tags: Channel,Member
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idmembersuser-id-get-openapi.md
- name: Mattermost API Remove user from channel
  x-api-slug: mattermost-api
  description: |-
    Delete a channel member, effectively removing them from a channel.
    ##### Permissions
    `manage_public_channel_members` permission if the channel is public.
    `manage_private_channel_members` permission if the channel is private.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/members/{user_id}
  tags: Remove,User,From,Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idmembersuser-id-delete-openapi.md
- name: Mattermost API Update channel roles
  x-api-slug: mattermost-api
  description: |-
    Update a user's roles for a channel.
    ##### Permissions
    Must have `manage_channel_roles` permission for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/members/{user_id}/roles
  tags: Channel,Roles
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idmembersuser-idroles-put-openapi.md
- name: Mattermost API Update channel notifications
  x-api-slug: mattermost-api
  description: |-
    Update a user's notification properties for a channel. Only the provided fields are updated.
    ##### Permissions
    Must be logged in as the user or have `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/members/{user_id}/notify_props
  tags: Channel,Notifications
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idmembersuser-idnotify-props-put-openapi.md
- name: Mattermost API View channel
  x-api-slug: mattermost-api
  description: |-
    Perform all the actions involved in viewing a channel. This includes marking channels as read, clearing push notifications, and updating the active channel.
    ##### Permissions
    Must be logged in as user or have `edit_other_users` permission.

    __Response only includes `last_viewed_at_times` in Mattermost server 4.3 and newer.__
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/members/{user_id}/view
  tags: View,Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelsmembersuser-idview-post-openapi.md
- name: Mattermost API Get channel members for user
  x-api-slug: mattermost-api
  description: |-
    Get all channel members on a team for a user.
    ##### Permissions
    Logged in as the user and `view_team` permission for the team. Having `manage_system` permission voids the previous requirements.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/teams/{team_id}/channels/members
  tags: Channel,Membersuser
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idteamsteam-idchannelsmembers-get-openapi.md
- name: Mattermost API Get channels for user
  x-api-slug: mattermost-api
  description: |-
    Get all the channels on a team for a user.
    ##### Permissions
    Logged in as the user, or have `edit_other_users` permission, and `view_team` permission for the team.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/teams/{team_id}/channels
  tags: Channelsuser
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idteamsteam-idchannels-get-openapi.md
- name: Mattermost API Get unread messages
  x-api-slug: mattermost-api
  description: |-
    Get the total unread messages and mentions for a channel for a user.
    ##### Permissions
    Must be logged in as user and have the `read_channel` permission, or have `edit_other_usrs` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/channels/{channel_id}/unread
  tags: Unread,Messages
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idchannelschannel-idunread-get-openapi.md
- name: Mattermost API Create a post
  x-api-slug: mattermost-api
  description: |-
    Create a new post in a channel. To create the post as a comment on another post, provide `root_id`.
    ##### Permissions
    Must have `create_post` permission for the channel the post is being created in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts
  tags: Post
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/posts-post-openapi.md
- name: Mattermost API Create a ephemeral post
  x-api-slug: mattermost-api
  description: |-
    Create a new ephemeral post in a channel.
    ##### Permissions
    Must have `create_post_ephemeral` permission (currently only given to system admin)
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts/ephemeral
  tags: Ephemeral,Post
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/postsephemeral-post-openapi.md
- name: Mattermost API Get a post
  x-api-slug: mattermost-api
  description: |-
    Get a single post.
    ##### Permissions
    Must have `read_channel` permission for the channel the post is in or if the channel is public, have the `read_public_channels` permission for the team.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts/{post_id}
  tags: Post
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/postspost-id-get-openapi.md
- name: Mattermost API Delete a post
  x-api-slug: mattermost-api
  description: |-
    Soft deletes a post, by marking the post as deleted in the database. Soft deleted posts will not be returned in post queries.
    ##### Permissions
    Must be logged in as the user or have `delete_others_posts` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts/{post_id}
  tags: Post
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/postspost-id-delete-openapi.md
- name: Mattermost API Update a post
  x-api-slug: mattermost-api
  description: |-
    Update a post. Only the fields listed below are updatable, omitted fields will be treated as blank.
    ##### Permissions
    Must have `edit_post` permission for the channel the post is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts/{post_id}
  tags: Post
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/postspost-id-put-openapi.md
- name: Mattermost API Patch a post
  x-api-slug: mattermost-api
  description: |-
    Partially update a post by providing only the fields you want to update. Omitted fields will not be updated. The fields that can be updated are defined in the request body, all other provided fields will be ignored.
    ##### Permissions
    Must have the `edit_post` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts/{post_id}/patch
  tags: Post
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/postspost-idpatch-put-openapi.md
- name: Mattermost API Get a thread
  x-api-slug: mattermost-api
  description: |-
    Get a post and the rest of the posts in the same thread.
    ##### Permissions
    Must have `read_channel` permission for the channel the post is in or if the channel is public, have the `read_public_channels` permission for the team.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts/{post_id}/thread
  tags: Thread
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/postspost-idthread-get-openapi.md
- name: Mattermost API Get a list of flagged posts
  x-api-slug: mattermost-api
  description: |-
    Get a page of flagged posts of a user provided user id string. Selects from a channel, team or all flagged posts by a user.
    ##### Permissions
    Must be user or have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/posts/flagged
  tags: List,Of,Flagged,Posts
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idpostsflagged-get-openapi.md
- name: Mattermost API Get file info for post
  x-api-slug: mattermost-api
  description: |-
    Gets a list of file information objects for the files attached to a post.
    ##### Permissions
    Must have `read_channel` permission for the channel the post is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts/{post_id}/files/info
  tags: File,Infopost
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/postspost-idfilesinfo-get-openapi.md
- name: Mattermost API Get posts for a channel
  x-api-slug: mattermost-api
  description: |-
    Get a page of posts in a channel. Use the query parameters to modify the behaviour of this endpoint. The parameters `since`, `before` and `after` must not be used together.
    ##### Permissions
    Must have `read_channel` permission for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//channels/{channel_id}/posts
  tags: Postsa,Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/channelschannel-idposts-get-openapi.md
- name: Mattermost API Search for team posts
  x-api-slug: mattermost-api
  description: |-
    Search posts in the team and from the provided terms string.
    ##### Permissions
    Must be authenticated and have the `view_team` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/posts/search
  tags: Searchteam,Posts
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idpostssearch-post-openapi.md
- name: Mattermost API Pin a post to the channel
  x-api-slug: mattermost-api
  description: |-
    Pin a post to a channel it is in based from the provided post id string.
    ##### Permissions
    Must be authenticated and have the `read_channel` permission to the channel the post is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts/{post_id}/pin
  tags: Pin,Post,To,Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/postspost-idpin-post-openapi.md
- name: Mattermost API Unpin a post to the channel
  x-api-slug: mattermost-api
  description: |-
    Unpin a post to a channel it is in based from the provided post id string.
    ##### Permissions
    Must be authenticated and have the `read_channel` permission to the channel the post is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts/{post_id}/unpin
  tags: Unpin,Post,To,Channel
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/postspost-idunpin-post-openapi.md
- name: Mattermost API Perform a post action
  x-api-slug: mattermost-api
  description: |-
    Perform a post action, which allows users to interact with integrations through posts.
    ##### Permissions
    Must be authenticated and have the `read_channel` permission to the channel the post is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//posts/{post_id}/actions/{action_id}
  tags: Perform,Post,Action
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/postspost-idactionsaction-id-post-openapi.md
- name: Mattermost API Get the user's preferences
  x-api-slug: mattermost-api
  description: |-
    Get a list of the user's preferences.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/preferences
  tags: Users,Preferences
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idpreferences-get-openapi.md
- name: Mattermost API Save the user's preferences
  x-api-slug: mattermost-api
  description: |-
    Save a list of the user's preferences.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/preferences
  tags: Save,Users,Preferences
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idpreferences-put-openapi.md
- name: Mattermost API Delete user's preferences
  x-api-slug: mattermost-api
  description: |-
    Delete a list of the user's preferences.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/preferences/delete
  tags: Users,Preferences
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idpreferencesdelete-post-openapi.md
- name: Mattermost API List a user's preferences by category
  x-api-slug: mattermost-api
  description: |-
    Lists the current user's stored preferences in the given category.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/preferences/{category}
  tags: List,Users,Preferences,By,Category
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idpreferencescategory-get-openapi.md
- name: Mattermost API Get a specific user preference
  x-api-slug: mattermost-api
  description: |-
    Gets a single preference for the current user with the given category and name.
    ##### Permissions
    Must be logged in as the user being updated or have the `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/preferences/{category}/name/{preference_name}
  tags: Specific,User,Preference
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idpreferencescategorynamepreference-name-get-openapi.md
- name: Mattermost API Upload a file
  x-api-slug: mattermost-api
  description: |-
    Uploads a file that can later be attached to a post.

    This request can either be a multipart/form-data request with a channel_id, files and optional
    client_ids defined in the FormData, or it can be a request with the channel_id and filename
    defined as query parameters with the contents of a single file in the body of the request.

    Only multipart/form-data requests are supported by server versions up to and including 4.7.
    Server versions 4.8 and higher support both types of requests.

    ##### Permissions
    Must have `upload_file` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//files
  tags: Upload,File
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/files-post-openapi.md
- name: Mattermost API Get a file
  x-api-slug: mattermost-api
  description: |-
    Gets a file that has been uploaded previously.
    ##### Permissions
    Must have `read_channel` permission or be uploader of the file.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//files/{file_id}
  tags: File
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/filesfile-id-get-openapi.md
- name: Mattermost API Get a files thumbnail
  x-api-slug: mattermost-api
  description: |-
    Gets a file's thumbnail.
    ##### Permissions
    Must have `read_channel` permission or be uploader of the file.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//files/{file_id}/thumbnail
  tags: Files,Thumbnail
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/filesfile-idthumbnail-get-openapi.md
- name: Mattermost API Get a files preview
  x-api-slug: mattermost-api
  description: |-
    Gets a file's preview.
    ##### Permissions
    Must have `read_channel` permission or be uploader of the file.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//files/{file_id}/preview
  tags: Files,Preview
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/filesfile-idpreview-get-openapi.md
- name: Mattermost API Get a public file link
  x-api-slug: mattermost-api
  description: Gets a public link for a file that can be accessed without logging
    into Mattermost.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//files/{file_id}/link
  tags: Public,File,Link
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/filesfile-idlink-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/filesfile-idlink-get-openapi.md
- name: Mattermost API Get metadata for a file
  x-api-slug: mattermost-api
  description: |-
    Gets a file's info.
    ##### Permissions
    Must have `read_channel` permission or be uploader of the file.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//files/{file_id}/info
  tags: Metadataa,File
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/filesfile-idinfo-get-openapi.md
- name: Mattermost API Get the jobs.
  x-api-slug: mattermost-api
  description: |-
    Get a page of jobs. Use the query parameters to modify the behaviour of this endpoint.
    __Minimum server version: 4.1__
    ##### Permissions
    Must have `manage_jobs` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//jobs
  tags: Jobs.
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/jobs-get-openapi.md
- name: Mattermost API Create a new job.
  x-api-slug: mattermost-api
  description: |-
    Create a new job.
    __Minimum server version: 4.1__
    ##### Permissions
    Must have `manage_jobs` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//jobs
  tags: New,Job.
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/jobs-post-openapi.md
- name: Mattermost API Get a job.
  x-api-slug: mattermost-api
  description: |-
    Gets a single job.
    __Minimum server version: 4.1__
    ##### Permissions
    Must have `manage_jobs` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//jobs/{job_id}
  tags: Job.
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/jobsjob-id-get-openapi.md
- name: Mattermost API Cancel a job.
  x-api-slug: mattermost-api
  description: |-
    Cancel a job.
    __Minimum server version: 4.1__
    ##### Permissions
    Must have `manage_jobs` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//jobs/{job_id}/cancel
  tags: Cancel,Job.
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/jobsjob-idcancel-post-openapi.md
- name: Mattermost API Get the jobs of the given type.
  x-api-slug: mattermost-api
  description: |-
    Get a page of jobs of the given type. Use the query parameters to modify the behaviour of this endpoint.
    __Minimum server version: 4.1__
    ##### Permissions
    Must have `manage_jobs` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//jobs/type/{type}
  tags: Jobs,Of,Given,Type.
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/jobstypetype-get-openapi.md
- name: Mattermost API Check system health
  x-api-slug: mattermost-api
  description: |-
    Check if the server is up and healthy based on the configuration setting `GoRoutineHealthThreshold`. If `GoRoutineHealthThreshold` and the number of goroutines on the server exceeds that threshold the server is considered unhealthy. If `GoRoutineHealthThreshold` is not set or the number of goroutines is below the threshold the server is considered healthy.
    __Minimum server version__: 3.10
    ##### Permissions
    Must be logged in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//system/ping
  tags: Check,System,Health
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/systemping-get-openapi.md
- name: Mattermost API Recycle database connections
  x-api-slug: mattermost-api
  description: |-
    Recycle database connections by closing and reconnecting all connections to master and read replica databases.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//database/recycle
  tags: Recycle,Database,Connections
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/databaserecycle-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/databaserecycle-post-openapi.md
- name: Mattermost API Send a test email
  x-api-slug: mattermost-api
  description: |-
    Send a test email to make sure you have your email settings configured correctly. Optionally provide a configuration in the request body to test. If no valid configuration is present in the request body the current server configuration will be tested.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//email/test
  tags: Send,Test,Email
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/emailtest-post-openapi.md
- name: Mattermost API Test AWS S3 connection
  x-api-slug: mattermost-api
  description: |-
    Send a test to validate if can connect to AWS S3. Optionally provide a configuration in the request body to test. If no valid configuration is present in the request body the current server configuration will be tested.
    ##### Permissions
    Must have `manage_system` permission.
    __Minimum server version__: 4.8
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//file/s3_test
  tags: Test,AWS,S3,Connection
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/files3-test-post-openapi.md
- name: Mattermost API Get configuration
  x-api-slug: mattermost-api
  description: |-
    Retrieve the current server configuration
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//config
  tags: Configuration
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/config-get-openapi.md
- name: Mattermost API Update configuration
  x-api-slug: mattermost-api
  description: |-
    Submit a new configuration for the server to use. As of server version 4.8, the `PluginSettings.EnableUploads` setting cannot be modified by this endpoint.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//config
  tags: Configuration
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/config-put-openapi.md
- name: Mattermost API Reload configuration
  x-api-slug: mattermost-api
  description: |-
    Reload the configuration file to pick up on any changes made to it.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//config/reload
  tags: Reload,Configuration
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/configreload-post-openapi.md
- name: Mattermost API Get client configuration
  x-api-slug: mattermost-api
  description: |-
    Get a subset of the server configuration needed by the client.
    ##### Permissions
    No permission required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//config/client
  tags: Client,Configuration
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/configclient-get-openapi.md
- name: Mattermost API Get configuration made through environment variables
  x-api-slug: mattermost-api
  description: |-
    Retrieve a json object mirroring the server configuration where fields are set to true
    if the corresponding config setting is set through an environment variable. Settings
    that haven't been set through environment variables will be missing from the object.

    __Minimum server version__: 4.10

    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//config/environment
  tags: Configuration,Made,Through,Environment,Variables
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/configenvironment-get-openapi.md
- name: Mattermost API Upload license file
  x-api-slug: mattermost-api
  description: |-
    Upload a license to enable enterprise features.

    __Minimum server version__: 4.0

    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//license
  tags: Upload,License,File
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/license-post-openapi.md
- name: Mattermost API Remove license file
  x-api-slug: mattermost-api
  description: |-
    Remove the license file from the server. This will disable all enterprise features.

    __Minimum server version__: 4.0

    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//license
  tags: Remove,License,File
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/license-delete-openapi.md
- name: Mattermost API Get client license
  x-api-slug: mattermost-api
  description: |-
    Get a subset of the server license needed by the client.
    ##### Permissions
    No permission required but having the `manage_system` permission returns more information.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//license/client
  tags: Client,License
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/licenseclient-get-openapi.md
- name: Mattermost API Get audits
  x-api-slug: mattermost-api
  description: |-
    Get a page of audits for all users on the system, selected with `page` and `per_page` query parameters.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//audits
  tags: Audits
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/audits-get-openapi.md
- name: Mattermost API Invalidate all the caches
  x-api-slug: mattermost-api
  description: |-
    Purge all the in-memory caches for the Mattermost server. This can have a temporary negative effect on performance while the caches are re-populated.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//caches/invalidate
  tags: Invalidate,,Caches
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/cachesinvalidate-post-openapi.md
- name: Mattermost API Get logs
  x-api-slug: mattermost-api
  description: |-
    Get a page of server logs, selected with `page` and `logs_per_page` query parameters.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//logs
  tags: Logs
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/logs-get-openapi.md
- name: Mattermost API Add log message
  x-api-slug: mattermost-api
  description: |-
    Add log messages to the server logs.
    ##### Permissions
    Users with `manage_system` permission can log ERROR or DEBUG messages.
    Logged in users can log ERROR or DEBUG messages when `ServiceSettings.EnableDeveloper` is `true` or just DEBUG messages when `false`.
    Non-logged in users can log ERROR or DEBUG messages when `ServiceSettings.EnableDeveloper` is `true` and cannot log when `false`.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//logs
  tags: Log,Message
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/logs-post-openapi.md
- name: Mattermost API Get WebRTC token
  x-api-slug: mattermost-api
  description: |-
    Get a valid WebRTC token, STUN and TURN server URLs along with TURN credentials to use with the Mattermost WebRTC service. See https://docs.mattermost.com/administration/config-settings.html#webrtc-beta for WebRTC configutation settings. The token returned is for the current user's session.
    ##### Permissions
    Must be authenticated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//webrtc/token
  tags: WebRTC,Token
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/webrtctoken-get-openapi.md
- name: Mattermost API Get analytics
  x-api-slug: mattermost-api
  description: |-
    Get some analytics data about the system. This endpoint uses the old format, the `/analytics` route is reserved for the new format when it gets implemented.

    The returned JSON changes based on the `name` query parameter but is always key/value pairs.

    __Minimum server version__: 4.0

    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//analytics/old
  tags: Analytics
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/analyticsold-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/analyticsold-get-openapi.md
- name: Mattermost API Create a custom emoji
  x-api-slug: mattermost-api
  description: |-
    Create a custom emoji for the team.
    ##### Permissions
    Must be authenticated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//emoji
  tags: Custom,Emoji
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/emoji-post-openapi.md
- name: Mattermost API Get a list of custom emoji
  x-api-slug: mattermost-api
  description: |-
    Get a page of metadata for custom emoji on the system. Since server version 4.7, sort using the `sort` query parameter.
    ##### Permissions
    Must be authenticated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//emoji
  tags: List,Of,Custom,Emoji
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/emoji-get-openapi.md
- name: Mattermost API Get a custom emoji
  x-api-slug: mattermost-api
  description: |-
    Get some metadata for a custom emoji.
    ##### Permissions
    Must be authenticated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//emoji/{emoji_id}
  tags: Custom,Emoji
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/emojiemoji-id-get-openapi.md
- name: Mattermost API Delete a custom emoji
  x-api-slug: mattermost-api
  description: |-
    Delete a custom emoji.
    ##### Permissions
    Must have the `manage_team` or `manage_system` permissions or be the user who created the emoji.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//emoji/{emoji_id}
  tags: Custom,Emoji
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/emojiemoji-id-delete-openapi.md
- name: Mattermost API Get a custom emoji by name
  x-api-slug: mattermost-api
  description: |-
    Get some metadata for a custom emoji using its name.
    ##### Permissions
    Must be authenticated.

    __Minimum server version__: 4.7
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//emoji/name/{emoji_name}
  tags: Custom,Emoji,By,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/emojinameemoji-name-get-openapi.md
- name: Mattermost API Get custom emoji image
  x-api-slug: mattermost-api
  description: |-
    Get the image for a custom emoji.
    ##### Permissions
    Must be authenticated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//emoji/{emoji_id}/image
  tags: Custom,Emoji,Image
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/emojiemoji-idimage-get-openapi.md
- name: Mattermost API Search custom emoji
  x-api-slug: mattermost-api
  description: |-
    Search for custom emoji by name based on search criteria provided in the request body. A maximum of 200 results are returned.
    ##### Permissions
    Must be authenticated.

    __Minimum server version__: 4.7
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//emoji/search
  tags: Search,Custom,Emoji
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/emojisearch-post-openapi.md
- name: Mattermost API Autocomplete custom emoji
  x-api-slug: mattermost-api
  description: |-
    Get a list of custom emoji with names starting with or matching the provided name. Returns a maximum of 100 results.
    ##### Permissions
    Must be authenticated.

    __Minimum server version__: 4.7
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//emoji/autocomplete
  tags: Autocomplete,Custom,Emoji
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/emojiautocomplete-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/emojiautocomplete-get-openapi.md
- name: Mattermost API Create an incoming webhook
  x-api-slug: mattermost-api
  description: |-
    Create an incoming webhook for a channel.
    ##### Permissions
    `manage_webhooks` for the channel the webhook is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//hooks/incoming
  tags: Incoming,Webhook
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksincoming-post-openapi.md
- name: Mattermost API List incoming webhooks
  x-api-slug: mattermost-api
  description: |-
    Get a page of a list of incoming webhooks. Optionally filter for a specific team using query parameters.
    ##### Permissions
    `manage_webhooks` for the system or `manage_webhooks` for the specific team.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//hooks/incoming
  tags: List,Incoming,Webhooks
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksincoming-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksincoming-get-openapi.md
- name: Mattermost API Get an incoming webhook
  x-api-slug: mattermost-api
  description: |-
    Get an incoming webhook given the hook id.
    ##### Permissions
    `manage_webhooks` for system or `manage_webhooks` for the specific team or `manage_webhooks` for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//hooks/incoming/{hook_id}
  tags: Incoming,Webhook
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksincominghook-id-get-openapi.md
- name: Mattermost API Update an incoming webhook
  x-api-slug: mattermost-api
  description: |-
    Update an incoming webhook given the hook id.
    ##### Permissions
    `manage_webhooks` for system or `manage_webhooks` for the specific team or `manage_webhooks` for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//hooks/incoming/{hook_id}
  tags: Incoming,Webhook
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksincominghook-id-put-openapi.md
- name: Mattermost API Create an outgoing webhook
  x-api-slug: mattermost-api
  description: |-
    Create an outgoing webhook for a team.
    ##### Permissions
    `manage_webhooks` for the team the webhook is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//hooks/outgoing
  tags: Outgoing,Webhook
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksoutgoing-post-openapi.md
- name: Mattermost API List outgoing webhooks
  x-api-slug: mattermost-api
  description: |-
    Get a page of a list of outgoing webhooks. Optionally filter for a specific team or channel using query parameters.
    ##### Permissions
    `manage_webhooks` for the system or `manage_webhooks` for the specific team/channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//hooks/outgoing
  tags: List,Outgoing,Webhooks
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksoutgoing-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksoutgoing-get-openapi.md
- name: Mattermost API Get an outgoing webhook
  x-api-slug: mattermost-api
  description: |-
    Get an outgoing webhook given the hook id.
    ##### Permissions
    `manage_webhooks` for system or `manage_webhooks` for the specific team or `manage_webhooks` for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//hooks/outgoing/{hook_id}
  tags: Outgoing,Webhook
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksoutgoinghook-id-get-openapi.md
- name: Mattermost API Delete an outgoing webhook
  x-api-slug: mattermost-api
  description: |-
    Delete an outgoing webhook given the hook id.
    ##### Permissions
    `manage_webhooks` for system or `manage_webhooks` for the specific team or `manage_webhooks` for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//hooks/outgoing/{hook_id}
  tags: Outgoing,Webhook
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksoutgoinghook-id-delete-openapi.md
- name: Mattermost API Update an outgoing webhook
  x-api-slug: mattermost-api
  description: |-
    Update an outgoing webhook given the hook id.
    ##### Permissions
    `manage_webhooks` for system or `manage_webhooks` for the specific team or `manage_webhooks` for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//hooks/outgoing/{hook_id}
  tags: Outgoing,Webhook
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksoutgoinghook-id-put-openapi.md
- name: Mattermost API Regenerate the token for the outgoing webhook.
  x-api-slug: mattermost-api
  description: |-
    Regenerate the token for the outgoing webhook.
    ##### Permissions
    `manage_webhooks` for system or `manage_webhooks` for the specific team or `manage_webhooks` for the channel.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//hooks/outgoing/{hook_id}/regen_token
  tags: Regenerate,Tokenthe,Outgoing,Webhook.
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/hooksoutgoinghook-idregen-token-post-openapi.md
- name: Mattermost API Get metadata
  x-api-slug: mattermost-api
  description: |-
    Get SAML metadata from the server. SAML must be configured properly.
    ##### Permissions
    No permission required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//saml/metadata
  tags: Metadata
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/samlmetadata-get-openapi.md
- name: Mattermost API Upload IDP certificate
  x-api-slug: mattermost-api
  description: |-
    Upload the IDP certificate to be used with your SAML configuration. This will also set the filename for the IdpCertificateFile setting in your `config.json`.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//saml/certificate/idp
  tags: Upload,IDP,Certificate
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/samlcertificateidp-post-openapi.md
- name: Mattermost API Remove IDP certificate
  x-api-slug: mattermost-api
  description: |-
    Delete the current IDP certificate being used with your SAML configuration. This will also disable SAML on your system as this certificate is required for SAML.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//saml/certificate/idp
  tags: Remove,IDP,Certificate
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/samlcertificateidp-delete-openapi.md
- name: Mattermost API Upload public certificate
  x-api-slug: mattermost-api
  description: |-
    Upload the public certificate to be used for encryption with your SAML configuration. This will also set the filename for the PublicCertificateFile setting in your `config.json`.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//saml/certificate/public
  tags: Upload,Public,Certificate
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/samlcertificatepublic-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/samlcertificatepublic-post-openapi.md
- name: Mattermost API Remove public certificate
  x-api-slug: mattermost-api
  description: |-
    Delete the current public certificate being used with your SAML configuration. This will also disable encryption for SAML on your system as this certificate is required for that.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//saml/certificate/public
  tags: Remove,Public,Certificate
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/samlcertificatepublic-delete-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/samlcertificatepublic-delete-openapi.md
- name: Mattermost API Upload private key
  x-api-slug: mattermost-api
  description: |-
    Upload the private key to be used for encryption with your SAML configuration. This will also set the filename for the PrivateKeyFile setting in your `config.json`.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//saml/certificate/private
  tags: Upload,Private,Key
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/samlcertificateprivate-post-openapi.md
- name: Mattermost API Remove private key
  x-api-slug: mattermost-api
  description: |-
    Delete the current private key being used with your SAML configuration. This will also disable encryption for SAML on your system as this key is required for that.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//saml/certificate/private
  tags: Remove,Private,Key
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/samlcertificateprivate-delete-openapi.md
- name: Mattermost API Get certificate status
  x-api-slug: mattermost-api
  description: |-
    Get the status of the uploaded certificates and keys in use by your SAML configuration.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//saml/certificate/status
  tags: Certificate,Status
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/samlcertificatestatus-get-openapi.md
- name: Mattermost API Create report
  x-api-slug: mattermost-api
  description: |-
    Create and save a compliance report.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//compliance/reports
  tags: Report
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/compliancereports-post-openapi.md
- name: Mattermost API Get reports
  x-api-slug: mattermost-api
  description: |-
    Get a list of compliance reports previously created by page, selected with `page` and `per_page` query parameters.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//compliance/reports
  tags: Reports
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/compliancereports-get-openapi.md
- name: Mattermost API Get a report
  x-api-slug: mattermost-api
  description: |-
    Get a compliance reports previously created.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//compliance/reports/{report_id}
  tags: Report
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/compliancereportsreport-id-get-openapi.md
- name: Mattermost API Download a report
  x-api-slug: mattermost-api
  description: |-
    Download the full contents of a report as a file.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//compliance/reports/{report_id}/download
  tags: Download,Report
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/compliancereportsreport-iddownload-get-openapi.md
- name: Mattermost API Sync with LDAP
  x-api-slug: mattermost-api
  description: |-
    Synchronize any user attribute changes in the configured AD/LDAP server with Mattermost.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//ldap/sync
  tags: Sync,LDAP
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/ldapsync-post-openapi.md
- name: Mattermost API Test LDAP configuration
  x-api-slug: mattermost-api
  description: |-
    Test the current AD/LDAP configuration to see if the AD/LDAP server can be contacted successfully.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//ldap/test
  tags: Test,LDAP,Configuration
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/ldaptest-post-openapi.md
- name: Mattermost API Get cluster status
  x-api-slug: mattermost-api
  description: |-
    Get a set of information for each node in the cluster, useful for checking the status and health of each node.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//cluster/status
  tags: Cluster,Status
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/clusterstatus-get-openapi.md
- name: Mattermost API Get brand image
  x-api-slug: mattermost-api
  description: |-
    Get the previously uploaded brand image. Returns 404 if no brand image has been uploaded.
    ##### Permissions
    No permission required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//brand/image
  tags: Brand,Image
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/brandimage-get-openapi.md
- name: Mattermost API Upload brand image
  x-api-slug: mattermost-api
  description: |-
    Uploads a brand image.
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//brand/image
  tags: Upload,Brand,Image
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/brandimage-post-openapi.md
- name: Mattermost API Create a command
  x-api-slug: mattermost-api
  description: |-
    Create a command for a team.
    ##### Permissions
    `manage_slash_commands` for the team the command is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//commands
  tags: Command
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/commands-post-openapi.md
- name: Mattermost API List commands for a team
  x-api-slug: mattermost-api
  description: |-
    List commands for a team.
    ##### Permissions
    `manage_slash_commands` if need list custom commands.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//commands
  tags: List,Commandsa,Team
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/commands-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/commands-get-openapi.md
- name: Mattermost API List autocomplete commands
  x-api-slug: mattermost-api
  description: |-
    List autocomplete commands in the team.
    ##### Permissions
    `view_team` for the team.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//teams/{team_id}/commands/autocomplete
  tags: List,Autocomplete,Commands
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idcommandsautocomplete-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/teamsteam-idcommandsautocomplete-get-openapi.md
- name: Mattermost API Update a command
  x-api-slug: mattermost-api
  description: |-
    Update a single command based on command id string and Command struct.
    ##### Permissions
    Must have `manage_slash_commands` permission for the team the command is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//commands/{command_id}
  tags: Command
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/commandscommand-id-put-openapi.md
- name: Mattermost API Delete a command
  x-api-slug: mattermost-api
  description: |-
    Delete a command based on command id string.
    ##### Permissions
    Must have `manage_slash_commands` permission for the team the command is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//commands/{command_id}
  tags: Command
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/commandscommand-id-delete-openapi.md
- name: Mattermost API Generate a new token
  x-api-slug: mattermost-api
  description: |-
    Generate a new token for the command based on command id string.
    ##### Permissions
    Must have `manage_slash_commands` permission for the team the command is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//commands/{command_id}/regen_token
  tags: Generate,New,Token
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/commandscommand-idregen-token-put-openapi.md
- name: Mattermost API Execute a command
  x-api-slug: mattermost-api
  description: |-
    Execute a command on a team.
    ##### Permissions
    Must have `use_slash_commands` permission for the team the command is in.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//commands/execute
  tags: Execute,Command
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/commandsexecute-post-openapi.md
- name: Mattermost API Register OAuth app
  x-api-slug: mattermost-api
  description: |-
    Register an OAuth 2.0 client application with Mattermost as the service provider.
    ##### Permissions
    Must have `manage_oauth` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//oauth/apps
  tags: Register,OAuth,App
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/oauthapps-post-openapi.md
- name: Mattermost API Get OAuth apps
  x-api-slug: mattermost-api
  description: |-
    Get a page of OAuth 2.0 client applications registered with Mattermost.
    ##### Permissions
    With `manage_oauth` permission, the apps registered by the logged in user are returned. With `manage_system_wide_oauth` permission, all apps regardless of creator are returned.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//oauth/apps
  tags: OAuth,Apps
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/oauthapps-get-openapi.md
- name: Mattermost API Get an OAuth app
  x-api-slug: mattermost-api
  description: |-
    Get an OAuth 2.0 client application registered with Mattermost.
    ##### Permissions
    If app creator, must have `mange_oauth` permission otherwise `manage_system_wide_oauth` permission is required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//oauth/apps/{app_id}
  tags: OAuth,App
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/oauthappsapp-id-get-openapi.md
- name: Mattermost API Update an OAuth app
  x-api-slug: mattermost-api
  description: |-
    Update an OAuth 2.0 client application based on OAuth struct.
    ##### Permissions
    If app creator, must have `mange_oauth` permission otherwise `manage_system_wide_oauth` permission is required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//oauth/apps/{app_id}
  tags: OAuth,App
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/oauthappsapp-id-put-openapi.md
- name: Mattermost API Delete an OAuth app
  x-api-slug: mattermost-api
  description: "Delete and unregister an OAuth 2.0 client application \n##### Permissions\nIf
    app creator, must have `mange_oauth` permission otherwise `manage_system_wide_oauth`
    permission is required."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//oauth/apps/{app_id}
  tags: OAuth,App
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/oauthappsapp-id-delete-openapi.md
- name: Mattermost API Regenerate OAuth app secret
  x-api-slug: mattermost-api
  description: |-
    Regenerate the client secret for an OAuth 2.0 client application registered with Mattermost.
    ##### Permissions
    If app creator, must have `mange_oauth` permission otherwise `manage_system_wide_oauth` permission is required.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//oauth/apps/{app_id}/regen_secret
  tags: Regenerate,OAuth,App,Secret
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/oauthappsapp-idregen-secret-post-openapi.md
- name: Mattermost API Get info on an OAuth app
  x-api-slug: mattermost-api
  description: |-
    Get public information about an OAuth 2.0 client application registered with Mattermost. The application's client secret will be blanked out.
    ##### Permissions
    Must be authenticated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//oauth/apps/{app_id}/info
  tags: Info,On,OAuth,App
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/oauthappsapp-idinfo-get-openapi.md
- name: Mattermost API Get authorized OAuth apps
  x-api-slug: mattermost-api
  description: |-
    Get a page of OAuth 2.0 client applications authorized to access a user's account.
    ##### Permissions
    Must be authenticated as the user or have `edit_other_users` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//users/{user_id}/oauth/apps/authorized
  tags: Authorized,OAuth,Apps
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/usersuser-idoauthappsauthorized-get-openapi.md
- name: Mattermost API Test Elasticsearch configuration
  x-api-slug: mattermost-api
  description: |-
    Test the current Elasticsearch configuration to see if the Elasticsearch server can be contacted successfully.
    Optionally provide a configuration in the request body to test. If no valid configuration is present in the
    request body the current server configuration will be tested.

    __Minimum server version__: 4.1
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//elasticsearch/test
  tags: Test,Elasticsearch,Configuration
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/elasticsearchtest-post-openapi.md
- name: Mattermost API Purge all Elasticsearch indexes
  x-api-slug: mattermost-api
  description: |-
    Deletes all Elasticsearch indexes and their contents. After calling this endpoint, it is
    necessary to schedule a new Elasticsearch indexing job to repopulate the indexes.
    __Minimum server version__: 4.1
    ##### Permissions
    Must have `manage_system` permission.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//elasticsearch/purge_indexes
  tags: Purge,,Elasticsearch,Indexes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/elasticsearchpurge-indexes-post-openapi.md
- name: Mattermost API Get the data retention policy details.
  x-api-slug: mattermost-api
  description: |-
    Gets the current data retention policy details from the server, including what data should be purged and the cutoff times for each data type that should be purged.
    __Minimum server version__: 4.3
    ##### Permissions
    Requires an active session but no other permissions.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//data_retention/policy
  tags: Data,Retention,Policy,Details.
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/data-retentionpolicy-get-openapi.md
- name: Mattermost API Upload plugin
  x-api-slug: mattermost-api
  description: |-
    Upload a plugin compressed in a .tar.gz file. Plugins and plugin uploads must be enabled in the server's config settings.

    ##### Permissions
    Must have `manage_system` permission.

    __Minimum server version__: 4.4
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//plugins
  tags: Upload,Plugin
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/plugins-post-openapi.md
- name: Mattermost API Get plugins
  x-api-slug: mattermost-api
  description: |-
    Get a list of inactive and a list of active plugin manifests. Plugins must be enabled in the server's config settings.

    ##### Permissions
    Must have `manage_system` permission.

    __Minimum server version__: 4.4
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//plugins
  tags: Plugins
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/plugins-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/plugins-get-openapi.md
- name: Mattermost API Remove plugin
  x-api-slug: mattermost-api
  description: |-
    Remove the plugin with the provided ID from the server. All plugin files are deleted. Plugins must be enabled in the server's config settings.

    ##### Permissions
    Must have `manage_system` permission.

    __Minimum server version__: 4.4
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//plugins/{plugin_id}
  tags: Remove,Plugin
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/pluginsplugin-id-delete-openapi.md
- name: Mattermost API Activate plugin
  x-api-slug: mattermost-api
  description: |-
    Activate a previously uploaded plugin. Plugins must be enabled in the server's config settings.

    ##### Permissions
    Must have `manage_system` permission.

    __Minimum server version__: 4.4
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//plugins/{plugin_id}/activate
  tags: Activate,Plugin
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/pluginsplugin-idactivate-post-openapi.md
- name: Mattermost API Deactivate plugin
  x-api-slug: mattermost-api
  description: |-
    Deactivate a previously activated plugin. Plugins must be enabled in the server's config settings.

    ##### Permissions
    Must have `manage_system` permission.

    __Minimum server version__: 4.4
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//plugins/{plugin_id}/deactivate
  tags: Deactivate,Plugin
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/pluginsplugin-iddeactivate-post-openapi.md
- name: Mattermost API Get webapp plugins
  x-api-slug: mattermost-api
  description: |-
    Get a list of web app plugins installed and activated on the server.

    ##### Permissions
    No permissions required.

    __Minimum server version__: 4.4
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//plugins/webapp
  tags: Webapp,Plugins
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/pluginswebapp-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/pluginswebapp-get-openapi.md
- name: Mattermost API Get a role
  x-api-slug: mattermost-api
  description: |-
    Get a role from the provided role id.

    ##### Permissions
    Requires an active session but no other permissions.

    __Minimum server version__: 4.9
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//roles/{role_id}
  tags: Role
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/rolesrole-id-get-openapi.md
- name: Mattermost API Get a role
  x-api-slug: mattermost-api
  description: |-
    Get a role from the provided role name.

    ##### Permissions
    Requires an active session but no other permissions.

    __Minimum server version__: 4.9
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//roles/name/{role_name}
  tags: Role
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/rolesnamerole-name-get-openapi.md
- name: Mattermost API Patch a role
  x-api-slug: mattermost-api
  description: |-
    Partially update a role by providing only the fields you want to update. Omitted fields will not be updated. The fields that can be updated are defined in the request body, all other provided fields will be ignored.

    ##### Permissions
    `manage_system` permission is required.

    __Minimum server version__: 4.9
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//roles/{role_id}/patch
  tags: Role
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/rolesrole-idpatch-put-openapi.md
- name: Mattermost API Get a list of roles by name
  x-api-slug: mattermost-api
  description: |-
    Get a list of roles from their names.

    ##### Permissions
    Requires an active session but no other permissions.

    __Minimum server version__: 4.9
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4//roles/names
  tags: List,Of,Roles,By,Name
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/rolesnames-post-openapi.md
- name: Mattermost API
  x-api-slug: mattermost-api
  description: Open source, private cloud Slack-alternative, Workplace messaging for
    web, PCs and phones. MIT-licensed. Hundreds of contributors. 14 languages. Secure,
    configurable, and scalable from teams to the enterprise.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/mattermost-logo.png
  humanURL: https://mattermost.com
  baseURL: https://your-mattermost-url.com//api/v4
  tags: Mattermost
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/mattermost/master/_listings/mattermost/openapi.md
x-common:
- type: x-blog
  url: https://about.mattermost.com/blog/
- type: x-blog-rss
  url: https://about.mattermost.com/feed/
- type: x-crunchbase
  url: https://crunchbase.com/organization/mattermost
- type: x-developer
  url: https://api.mattermost.com/
- type: x-github
  url: https://github.com/mattermost
- type: x-pricing
  url: https://about.mattermost.com/pricing/
- type: x-security
  url: https://docs.mattermost.com/overview/security.html
- type: x-twitter
  url: https://twitter.com/mattermosthq
- type: x-website
  url: https://mattermost.com
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---