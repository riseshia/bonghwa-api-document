# Scenario

This document defines fundamental behaviors of backend. These will be used on
Specification Validator.

Disclaimer: These scenario describes how to use service roughly.
Don't forget this document defines how to be backend service, not frontend service.
Check each protocol request/response if you want to know actual behavior, especially error response.

## Authentication / Authorization

- Authentication will be worked with tokens(see below).
- All behavior required authentication except sign up.
- There are only 2 roles, normal user and administrator.
- tokens will be sent protocol specific way.
- service will give access token and shared token.
  - access token will be used for all request except renew.
  - shared token will be used for renew access token.
  - access token should be renewed if it expired.
  - access token will be expired in 15 mins.

## Sign up

- guest can sign up.

## Generate/Expire token

token will be used for authentication, which token should be valid 15 mins.

- user who got approve from administrator can generate token.
- user who haven't get approve from administrator can't generate token.
- user who have token could expire it. i.e. logout

## Behavior in system

- new user will be joined `general` automatically.
- user could join another channel.
- user could leave channel except `general`.
- user could see only one channel or DM.
- system could fetch/be pushed new messages from server in all channels joined by user.

## Behavior in channel

- user could see who is joined.
- user could see channel's messages.
- user could send message.
- user could send message with image(base64 encoded).
- user could delete user's own message.
  - image won't be accessible if related message destroyed.
- user could see new messages in (near) realtime.
- user could see messages order by sent datetime.
  - new message should be came at the bottom of messages.

## Behavior in DM

- user could see direct messages by sent user.
- user could send direct message.
- user could send direct message with image(base64 encoded).
- user could delete user's own message.
  - image won't be accessible if related message destroyed.
- user couldn't leave each DM.
  - in the other words, DM is treated as it exists always.
- user could see messages order by sent datetime.
  - new message should be came at the bottom of messages.

## Behavior in admin view

- admin could see channel list.
- admin could create channel.
- admin could archive channel.
- admin could rename channel.
- admin could see user list.
- admin could approve user to sign-in.
