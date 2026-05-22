# Работа с историей и изменениями в Git

Репозиторий: https://github.com/hashicorp/terraform

---

## 1. Найдите полный хеш и комментарий коммита, хеш которого начинается на `aefea`

Команда:

```bash
git show --no-patch --pretty=oneline aefea
```

Результат:

```text
aefead2207ef7e2aa5dc81a34aedf0cad4c32545 Update CHANGELOG.md
```

Ответ:

- Полный хеш: `aefead2207ef7e2aa5dc81a34aedf0cad4c32545`
- Комментарий: `Update CHANGELOG.md`

---

## 2. Какому тегу соответствует коммит `85024d3`

Команды:

```bash
git tag --contains 85024d3
```

```bash
git describe --exact-match 85024d3
```

Результат:

```text
v0.12.23
```

Ответ:

- Коммит `85024d3` соответствует тегу `v0.12.23`

---

## 3. Сколько родителей у коммита `b8d720`

Команда:

```bash
git show --no-patch --pretty=%P b8d720
```

Результат:

```text
56cd7859e05c36c06b56d013b55a252d0bb7e158
9ea88f22fc6269854151c571162c5bcf958bee2b
```

Ответ:

Коммит имеет двух родителей:

1. `56cd7859e05c36c06b56d013b55a252d0bb7e158`
2. `9ea88f22fc6269854151c571162c5bcf958bee2b`

---

## 4. Перечислите хеши и комментарии всех коммитов между тегами `v0.12.23` и `v0.12.24`

Команда:

```bash
git log --oneline v0.12.23..v0.12.24
```

Результат:

```text
33ff1c03bb v0.12.24
b14b74c493 [Website] vmc provider links
3f235065b9 Update CHANGELOG.md
6ae64e247b registry: Fix panic when server is unreachable
5c619ca1ba website: Remove links to the getting started guide's old location
06275647e2 Update CHANGELOG.md
d5f9411f51 command: Fix bug when using terraform login on Windows
4b6d06cc5d Update CHANGELOG.md
dd01a35078 Update CHANGELOG.md
225466bc3e Cleanup after v0.12.23 release
```

---

## 5. Найдите коммит, в котором была создана функция `providerSource`

Команды:

```bash
git grep "func providerSource"
```

```bash
git log -S"func providerSource" --oneline
```

Результат:

```text
8c928e8358 main: Consult local directories as potential mirrors of providers
```

Дополнительная проверка:

```bash
git show 8c928e8358 -- provider_source.go
```

Ответ:

Функция `providerSource` была создана в коммите:

```text
8c928e83589d90a031f811fae52a81be7153e82f
main: Consult local directories as potential mirrors of providers
```

---

## 6. Найдите все коммиты, в которых была изменена функция `globalPluginDirs`

Поиск функции в историческом коммите:

```bash
git grep "func globalPluginDirs" 8364383c35
```

Результат:

```text
8364383c35:plugins.go:func globalPluginDirs() []string {
```

Просмотр истории файла:

```bash
git log --follow --oneline -- plugins.go | grep -i plugin
```

Результат:

```text
52dbf94834 keep .terraform.d/plugins for discovery
41ab0aef7a Add missing OS_ARCH dir to global plugin paths
66ebff90cd move some more plugin search path logic to command
8364383c35 Push plugin discovery down into command package
```

Ответ:

Функция `globalPluginDirs` изменялась в коммитах:

1. `52dbf94834 keep .terraform.d/plugins for discovery`
2. `41ab0aef7a Add missing OS_ARCH dir to global plugin paths`
3. `66ebff90cd move some more plugin search path logic to command`
4. `8364383c35 Push plugin discovery down into command package`

---

## 7. Кто автор функции `synchronizedWriters`

Команды:

```bash
git log -S"func synchronizedWriters" --oneline
```

```bash
git show --no-patch --pretty=fuller 5ac311e2a9
```

Результат:

```text
Author: Martin Atkins <mart@degeneration.co.uk>
```

Ответ:

Автор функции `synchronizedWriters` — `Martin Atkins`.

Коммит создания функции:

```text
5ac311e2a91e381e2f52234668b49ba670aa0fe5
main: synchronize writes to VT100-faker on Windows
```
