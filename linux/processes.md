# processes

## ps
```sh
ps -ef  # all processes 
ps -ejH # process tree
```

## nice
nice - устанавливает приоритет процессу от -20 (высший) до 19 (низший)
> [!NOTE]
> Обычный пользователь не может задать высокий приоритет, но может задать приоритет ниже.

```sh
nice -n <prio> <pid>
```

> [!NOTE]
> `renice` - То же самое что и найс, но делает всё на ходу.

## kill, pkill, killall

```sh
kill -<code> pid
pkill -<code> pattern
killall -<code> name  # полное совпадение
```

> [!TIP]
> `pgrep` - `grep` по процессам


