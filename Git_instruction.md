![logo](Git-Logo-2Color.png)

# Работа с Git

## 1. Проверка наличия установленного Git.
В терминале выполнить команду `git version`.
Если Git установлен, появится сообщение с информацией о версии программы.
Иначе будет сообщение об ошибке.

## 2. Установка Git.
Загружаем последнюю версию Git с сайта: https://git-scm.com/downloads. Устанавливаем с настройками по умолчанию.

## 3. Настройка Git.
При первом использовании Git необходимо представиться.
Для этого в терминале нужно выполнить две команды:
```
• git config --global user.name «Ваше имя английскими буквами»
• git config --global user.email ваша почта@example.com
```

## 4. Инициализация локального депозитория в Git.
После первоначальной настройки Git необходимо инициализировать депозиторий, в котором будет храниться информация о различных версиях файлов.
Для этого в терминале необходимо ввести команду `git init`.
Если сообщений об ошибке в терминале не появилось, то инициализация успешно завершена.

## 5. Запись изменений депозитория в Git.
После инициализации депозитория и последующих изменений в файле необходимо периодически, по мере необходимости, осуществлять сохранение версий файла. Для проверки наличия изменений и их фиксации используем следующие команды:
 
 ```
 • git status - для получения информации от git о текущем состоянии;
• git add имя файла- для добавления (подготовки) файла к фиксации изменений;
• git commit - для фиксации текущей версии файла.
```
В процессе работы с помощью команды `git diff` отслеживаем разницу между текущим состоянием файла и сохраненной версией. Если разница есть, то в терминале появится информация обо всех добавленных/удаленных знаках файла по сравнению с последней сохраненной версией.

## 6. Просмотр изменений депозитория в Git.

В процессе работы с файлом и создании его различных версий возникает необходимость просмотра его различных состояний (версий). Для этого мы используем команду `git log` для вывода в терминале полного списка сохранений (коммитов).

Далее выбираем интересующий нас коммит и с помощью команды `git checkout` с указанием хэш-кода коммита выводим в рабочей области соответствующую сохраненную версию файла.


***Внимание!***
После просмотра сохранненой версии файла необходимо обязательно вернуться к текущей версии для продолжения работы с помощью команды `git checkout master`, либо `git switch -`.

## 7. Игнорирование файлов.

Для того, чтобы исключить из отслеживания репозиторием определенные файлы или папки необходимо создать файл ***`.gitignore`*** и записать в него их названия или шаблоны, соотв. таким файлам или папкам.

## 8. Создание веток в Git.

Создать ветку можно командой:
```
git branch <имя новой ветки>
```
В результате создается новый указатель на текущий коммит.
Ветка в Git - это простой перемещаемый указатель на один из коммитов, обычно последний в цепочке коммитов.

По умолчанию имя основной ветки в Git - *master*.

Список веток в репозитории можно посмотреть с помощью команды
```
git branch
```
Текущая ветка будет отмечена звездочкой: **\*master**

## 9. Перемещение между ветками, возможности *`checkout`*.

Для перемещения между ветками в Git используется команда `git checkout <название ветки>`.

С помощью данной команды так же можно одновременно создавать новую ветку. Для этого в команду добавить символы через пробел <-b>. Например:
```
git checkout -b <название новой ветки>
```

## 10. Слияние веток и разрешение конфликтов.

Для слияния выбранной ветки с текущей нужно выполнить команду:
```
git merge <название выбранной ветки>
```
Если была изменена одна и та же часть файла в обеих ветках, то может возникнуть конфликт, который потребует участия пользователя. VSCode предложит варианты разрешения:

* оставить вариант текущей версии;
* принять входящее изменение;
* сохранить оба варианта;
* сравнить изменения.

После разрешения конфликта необходимо создать коммит о результатах слияния и разрешении конфликта (при наличии).

## 11. Удаление веток в Git.

В процессе работы над проектом возникает необходимость удаления ненужных веток. Для корректного удаления ветки необходимо сначала совершить слияние ветки с основной с помощью `git merge <название выбранной ветки>`. Далее оставаясь в основной ветке набрать команду `git branch -d <название выбранной ветки>.

Если слияние не производилось (по какой-либо причине), то после команды `git branch -d <название выбранной ветки>` в териминале появится сообщение об ошибке. В таком случае необходимо либо сначала выполнить слияние, либо принудительно удалить ветку с помощью команды команду `git branch -D <название выбранной ветки>`.

## 12. Добавление картинки в Markdown.

Для добавления картинки в проект необходимо файл с картинкой добавить в папку с репозиторием. Далее добавить этот файл в `*.gitignore*`. После этого файл с картинкой не будет отслеживаться депозиторием.
Далее в строке рабочей области необходимо добавить следующие символы:
```
![<сообщение>](<имя файла с расширением>)
```
Например,
![Привет! Я Ромка](IMG_2737.jpg)

## 13. Работа с удаленными репозиториями.

В процессе создания сложных пректов необходима работа в команде, поэтому неизбежно возникает необходимость делиться или получать коды других участников, расположенных не в одном офисе, а порой и в разных концах света. Для этого были созданы специальные веб-сервисы для работы с удаленными репозиториями. Одним из такх сервисов и является GitHub.com.

*`Из основных возможностей работы с удаленными репозиториями на GitHub.com можно выделить:`*

- создание удаленного репозитория;
- получение ```(pull)``` актуального состояния удаленного репозитория и внесение ```(push)``` изменений в него;
- клонирование ```(clone)``` любого удаленного репозиторапрапрапрапия и дальнейшая работа с ним на локальном уровне;
- совместная работа над проектами с помощью ```Pull Request```.

`ВАЖНО!` *`Для начала работы с удаленными репозиториями необходимо создать аккаунт на GitHub.com.`*

## 13.1. Создание удаленного репозитория.

Для создании удаленного репозиапрапрапртория необходимо ввести новый репозиторий на GitHub.com. Далее связать удаленный репозиторий с локальным, переименовать ветку локального репозитория в ```main``` и отправить с помощью ```push``` локальный репозиторий в удаленный (на GitHub.com), при этом, возможно, нужно будет авторизоваться на удаленном репозитории.

Для этого, в случаях когда локального репозитория не существует, рекомендуется создать папку и выполнить следующие действия:
```
echo "# Git_instruction" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main                
git remote add origin https://github.com/Chernyimisha/Git_instruction.git
git push -u origin main
```
В случаях когда локальный репозиторий готов, то остается выполнить следующие действия:
```
git remote add апрапрапраorigin https://github.com/Chernyimisha/Git_instruction.git
git branch -M main
git push -u origiапрапрапрn main
```


   




