# Tabelas e atributos

Esquema do PostgreSQL 16, extraído do banco gerado pela migration
`0001_initial_schema`. Tipos na notação do próprio PostgreSQL.

Os tipos `user_role` e `user_status` são ENUMs nativos:

```
user_role:   admin | teacher
user_status: invite_pending | active | inactive
```

---

## Contas e acesso

```
USERS:
id             bigint
email          varchar(255)
password_hash  varchar(255)
role           user_role
status         user_status
full_name      varchar(255)
school         varchar(255)
created_at     timestamptz
updated_at     timestamptz

INVITES:
id          bigint
user_id     bigint
token_hash  varchar(255)
expires_at  timestamptz
used_at     timestamptz
created_at  timestamptz
updated_at  timestamptz

PASSWORD_RESET_TOKENS:
id          bigint
user_id     bigint
token_hash  varchar(255)
expires_at  timestamptz
used_at     timestamptz
created_at  timestamptz
updated_at  timestamptz

REFRESH_TOKENS:
id          bigint
user_id     bigint
token_hash  varchar(255)
expires_at  timestamptz
revoked_at  timestamptz
created_at  timestamptz
updated_at  timestamptz
```

## Acervo

```
THEMES:
id           bigint
name         varchar(120)
description  text
created_at   timestamptz
updated_at   timestamptz

EDUCATION_LEVELS:
id          bigint
name        varchar(120)
sort_order  smallint
created_at  timestamptz
updated_at  timestamptz

BOOKS:
id                  bigint
title               varchar(255)
author              varchar(255)
synopsis            text
isbn                varchar(20)
page_count          integer
edition             varchar(50)
cover_url           text
store_url           text
education_level_id  bigint
created_at          timestamptz
updated_at          timestamptz
```

## Vínculos

```
BOOK_THEMES:
book_id   bigint
theme_id  bigint

TEACHER_THEMES:
user_id   bigint
theme_id  bigint

TEACHER_EDUCATION_LEVELS:
user_id             bigint
education_level_id  bigint

SAVED_BOOKS:
user_id     bigint
book_id     bigint
created_at  timestamptz
```

## Conteúdo institucional

```
INSTITUTIONAL_PAGES:
id            bigint
slug          varchar(80)
title         varchar(160)
body          text
external_url  text
sort_order    smallint
is_published  boolean
created_at    timestamptz
updated_at    timestamptz
```
