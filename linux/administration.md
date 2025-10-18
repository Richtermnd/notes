# administration

## su

```sh
su <user> <cmd>
```


## sudoers
Позволяет управлять правами пользователей и групп.

`user | %group = HOST (FROM USER) COMMANDS`

`man sudoers`


## useradd

`/etc/default/useradd` - дефолтные параметры useradd (можно посмотреть через `useradd -D`)
`/etc/login.defs` - Ещё дефолтные параметры, но больше и круче.
