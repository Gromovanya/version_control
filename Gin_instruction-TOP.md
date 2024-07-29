# Инструкция по терминам GIT (подробная)

## 1. Инструкция для создания репозитория

1. >Чтобы создать репозиторий, нужно в нужной папке ввести следующее:
```sh
git init
```
2. >Дальше, если это твой первый репозиторий, чтобы можно было им пользоваться. Нужно представиться, для этого нужно сделать следующее:
```sh
git config --global user.name "Ваше_имя"или"Ваше_новое_имя"
```
```sh
git config --global user.email "адрес@example.com"
```

## 2. Инструкция для работы с версиями

1. > Чтобы работать с разными версиями, нужно создать файл, в котором вы будете сохранять версии. Затем необходимо проверить информацию от Git о его текущем состоянии, чтобы сделать это:
```sh
git status
```
2. > Как только будет проведена проверка, если файл будет изменён или не сохранён, тогда нужно добавить его (или их) к следующему коммиту. Чтобы сделать это:
```sh
git add <нужный файл>
```
3. > Также есть противоположная функция, которая отменяет все изменения:
```
git restore <нужный файл>
```
4. > Далее нужно сделать коммит репозитория. Для этого нужно:
```sh
git commit -m "Сообщение"
```
5. > После этого нужно открыть историю всех коммитов с их хеш кодами. Для этого нужно:
```sh
git log
```
6. > Или использовать сокращённую версию (git log) без времени и без информации о том, кем был создан коммит. Для этого нужно:
```sh
git log --oneline
```
7. > Далее, чтобы переключиться на другую версию (другой коммит), обязательно укажите хеш-код нужной версии. Чтобы переключиться, нужно сделать следующее:
```sh
git checkout <хеш код нужного>
```
8. > И чтобы вернуться назад, нужно сделать следующее:
```sh
git checkout master
```
__Вот все базовые советы, которые помогут работать с разными версиями.__

## 3. Инструкция для работы с ветвями
1. >Чтобы посмотреть существующие ветви, нужно сделать следующее:
```sh
git branch
```
2. >Также, чтобы создать новую ветвь, нужно сделать следующее:
```sh
git branch <название ветки например brain_name>
```
3. >Далее, чтобы переключиться на созданную новую или существующую ветку, нужно сделать следующее:
```sh
git checkout <название ветки например brain_name>
```
4. >И вот, ты находишься в другой ветке, и все созданные изменения в ней не относятся к главной ветке или другим веткам.

5. >Далее, чтобы перенести все изменения из этой ветки в главную (master), нужно сделать следующее:
```sh
git merge <название ветки например brain_name>
```
6. >Также важно учитывать, что нужно находиться в той ветке, куда ты хочешь перенести данные. Например, __если ты находишься в ветке (master), и ты переносишь данные из ветки (brain_name).__

7. >Также, когда ты перенесёшь данные из дополнительной ветки в главную, нужно удалить эту дополнительную ветку. Это можно сделать вот так:
```sh
git branch -d <название ветки>
```
8. >Также можно просмотреть все ветки с помощью истории коммитов, чтобы увидеть, как ветки сливаются и так далее. Чтобы сделать это, нужно следующее:
```sh
git log --graph 
```
__Вот эти функции помогут работать с ветвями.__

## 4. Инструкция для работы с удалёнными репозиториями

### Создание удалённого репозитория
1. >Для начала нужно зарегистрироваться на GitHub (github.com), а потом нажать на плюсик в правом верхнем углу. Затем нужно выбрать "New repository" (новый репозиторий) и в открывшейся вкладке дать название репозиторию. И всё, он создан!

### Управление удалённым репозиторием

1. >Для начала, после его создания, ты можешь подключить свой локальный репозиторий к удалённому. Это делается с помощью:
```sh
git remote add origin <ссылка своего репозитория>
```
* Ссылку можно найти в своём удалённом репозитории. Нужно нажать на зелёную кнопку "Code", и там будет HTTPS-ссылка — вот она и нужна. Также "origin" — это, по сути, название удалённого репозитория.
2. >Потом нужно будет поменять название главной ветки, так как это требуется самому GitHub. Это делается с помощью:
```sh
git branch -M main
```
3. >Дальше нужно будет выполнить push. Но если ты делаешь это в первый раз, то нужно подключить GitHub к Visual Studio. Для этого необходимо ввести следующее:
```sh
git push -u origun main
```
* Потом можно будет просто вводить следующее:
```sh
git push
```
* Это позволит загружать изменения на удалённый репозиторий.

4. >Также, если кто-то другой (друг, соучастники и т.д.) загрузит изменения в удалённый репозиторий, у тебя будет старая версия проекта. Нужно сделать следующее, чтобы получить изменения из удалённого репозитория в свой локальный. Это также работает как merge:
```sh
git pull
```
5. >Также может возникнуть ошибка при попытке сделать push из-за того, что у тебя есть свои коммиты, а кто-то загрузил свои изменения в удалённый репозиторий и там есть другие коммиты. Чтобы исправить эту ошибку, нужно сделать следующее:
```sh
git pull --rebase
```
* Это позволяет тебе пересоздать историю коммитов (rebase). Если два изменения из разных коммитов находятся на одной строке, нужно просто вручную подкорректировать или выбрать варианты в меню и сохранить. Затем с помощью команды (add) можно будет выполнить следующее:
```sh
git rebase --continue
```
* Это помогает продолжить rebase, создаёт новый коммит, а потом можно сделать push, и всё — конфликт исправлен.

* Также есть команда --abort, которая может вернуть изменения в начало rebase. Как её вызвать:
```sh
git rebase --abort
```

* И есть функция skip, которая позволяет пропустить конфликтный коммит. Как её вызвать:
```sh
git rebase --skip
```

6. >Ещё есть возможность клонировать любой публичный репозиторий и начать работать с ним локально. Как её вызвать:
```sh
git clone <ссылка на репозиторий>
```
### Как сделать pull request

1. >Pull request — это предложение внести изменения в чужой проект разработчика.

2. >Чтобы это сделать, нужно сначала сделать fork. Это позволяет клонировать чужой проект на свой аккаунт GitHub, и, по сути, эта копия становится твоей.

3. >Дальше нужно создать папку, куда ты клонируешь этот репозиторий, с помощью команды git clone <ссылка на репозиторий>. Затем создайте ветку, в которой ты будешь корректировать этот репозиторий.

4. >Дальше нужно выталкнуть эту ветку на сервер GitHub, но когда ты будешь делать push, он скажет, что ты выталкиваешь главную ветку, а не ту, в которой ты находишься. Чтобы это исправить, нужно сделать следующее:
```
git push --set-upstream origin <название этой ветки>
```

5. >Потом нужно будет перезагрузить свою страницу удалённого репозитория, и там появится окно с зелёной кнопкой "Compare & pull request". Это означает, что ты можешь предложить изменения владельцу репозитория.

6. >Когда ты нажмёшь на эту кнопку, у тебя откроется меню, где ты можешь дать название и оставить комментарий. Когда ты нажмёшь на зелёную кнопку в правом нижнем углу, произойдёт создание pull request.

7. >После этого владельцу этого репозитория придет твоё предложение которое он может принять или отказаться.

**Вот это все базовые знания которые помогут разобраться с удалёнными репозиториями.**

## 5. Инструкция о дополнительных функциях

1. >Также можно просмотреть версию GIT. Чтобы сделать это, нужно:
```sh
git --version
```
2. >Также можно сравнить изменения с предыдущим коммитом или с несколькими предыдущими коммитами. Для этого нужно ввести хеш-код коммита. Чтобы сделать это, нужно:
```sh
git diff <хеш код>
```
3. >Ещё есть функция, позволяющая посмотреть все возможные подсказки по GIT. Чтобы её вызвать, нужно сделать следующее:
```sh
git --help
```
__Вот некоторые дополнительные функции, которые присутствуют.__