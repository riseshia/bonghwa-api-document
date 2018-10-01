# Data model

This document will describe required data model and its minimum columns.
Please add more columns you need. i.e. PK, created_at, ...
Feel free to rename model/column name if you want.

## Member

- email: string[256] not null, unique
  - email should be valid with `/\w[\w.+\-]*{1,63}@[\w-]+\.\w+(\W|$)/`
- hashed_password: string[256] not null
  - use SHA256(not required)
- name: string[64] not null, unique
  - name should be valid with `/\w+/`
- is_admin: boolean not null, default false
- is_approved: boolean not null, default false

## Token

- member_id: FK
- access_token: string[64] not null, unique
- refresh_token: string[64] not null, unique
- expired_at: datetime
  - treated as permanent token if null

## Channel

- name: string[128] not null, unique
  - name should be valid with `/\w+/`
- is_archived: bool not null, default false
- is_general: bool not null, default false

## JoinStatus

Store user joined status.

- member_id: FK
- channel_id: FK
- set(member_id / channel_id) unique

## Message

Store public messages in channel.

- id: PK
- member_id: FK
- channel_id: FK
- body: string[512]
  - message should have image if body is null.
- created_at: datetime
- image_id: FK

## DirectMessage

Store direct messages.

- id: PK
- sender_id: FK
- recipient_id: FK
- body: string[512]
  - message should have image if body is null.
- created_at: datetime
- image_id: FK

## Image

Support jpg, jpeg, png.
Maximum size of image is 1MB.

- filename: string, not null
