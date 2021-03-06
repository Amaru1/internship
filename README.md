# internship

## Команды linux:

### Работа в репозитории:

**mkdir** *folder_name* — создание директории с именем folder_name.  
**cd** *folder_name* — перейти в директорию folder_name.  
**cd ..** — выход из текущей директории.  
**touch** *file_name* — создание файла file_name.  
**git init** — создание git репозитория из выбранной директории.  
**git status** — проверка текущего состояния репозитория.  
	-s — краткий вид изменений.  
  
**git clone** *URL* — клонирование репозитория.  
**git push** — внесение изменений в удалённую ветку.  
	-u origin master — если удаленная ветка не установлена как отслеживаемая, то сделать ее такой.  

**git pull** — получение изменения из репозитория.  
**git pull origin** *Name_branch* — получение определённой ветки с удалённого репозитория.  
**clear** — отчистка консоли.  
  
**git rm** *file_name* — удалить файл *file_name* из рабочей директории и добавить в индекс информацию об удалении.  
	--cached *file_name* — удалить файл *file_name* из репозитория, но сохранить его локально.  
  
  
  
  
### Просмотр истории:  
  
**git diff** — показать изменения в файлах, которые еще не были добавлены в индекс коммита (staged).  
	--staged — показать что было добавленно в индекс с помощью git add, но еще не было закоммиченно.  
	HEAD — показать что изменилось с последнего коммита.  
	HEAD^ — показать что изменилось с предпоследнего коммита.  
	*branch* — сравнить текущую ветку с заданной *branch*.  
	--stat — показать статистику какие файлы были изменены и как.  
	*<first_branch>..<second_branch>* — посмотреть различия между двумя заданными ветками.  
  
**git log** — список изменения текущей ветки.  
	--follow *file_name* — список изменения файла *file_name*, включая переименования.  
	--pretty=format:"%h %s" --graph — изменение вида отображения истории изменений.  
	--author='Name' --after={1.week.ago} --pretty=oneline --abbrev-commit — посмотреть над чем работал заданный пользователь последнюю неделю.  
	--no-merges master.. — посмотреть историю изменений только для текущей ветки.  
  
  
  
  
### Git remote:  
  
**git remote add** *remote_name* *remote_url* — создание удалённого каталога через URL(используется в директории локального репозитория).  
**git remote add** *remote_name* *remote_ssh(git@...)* — создание удалённого каталога через SSH(используется в директории локального репозитория).  
**git remote -v** — просмотр списка удалённых соединений.  
  
  
  
  
### Ветки:  

**git branch** — список всех локальных веток в текущей дериктории.  
	-a  — посмотреть полный список локальных и удаленных веток.  
  
**git branch** *branch_name* — создание ветки с именем *branch_name*.  
**git checkout** *branch_name* — переключение на ветку *branch_name*.  
				**ИЛИ**  
**git checkout -b** *branch_name* — создание ветки с именем *branch_name* и переключение на неё.  
**git branch -d** *branch_name* — удаление ветки *branch_name*.  
	-D *branch* — принудительно удалить заданную ветку, игнорируя ошибки.  
	-m *<oldname>* *<newname>* — переименовать ветку.  
  
**git merge** *branch_name* — слияние ветки *branch_name* и основной ветки проекта (нужно переключиться на основную ветку).  
**git merge** *first_branch*/*second_branch* — слить изменения локальной ветки *second_branch* и заданной удаленной *first_branch*.  
**git merge --abort** — отменить процесс слияния.  
  
  
  
  
### Добавление/удаление и коммит файлов в репозиторий:  
  
**git add** *file_name* — добавление файла file_name в выбранный репозиторий.  
	--all** — добавление всех файлов выбранной директории в выбранный репозиторий.  
	'*.txt' — добавить только файлы, соответствующие указанному выражению.  
	--patch filename — позволяет выбрать какие изменения из файла добавятся в коммит.  
**git commit** — Создание новой записи, которая содержит текущее содержимое индекса и сообщение журнала с описанием изменений.  
	-m(--message) — добавление сообщения коммиту.  
	-am(add --message) — проиндекирует файлы и закоммитит их.  
	--allow-empty-message — создание пустого сообщения коммита.  
	-amend -m "msg" — редактирование последнего коммита.  
  
##### Отмена коммитов:  
  
**git reset** — убрать изменения из индекса коммита, сами изменения останутся.  
	*commit/tag* — отменить все коммиты после указанного коммита *commit/tag*, изменения будут сохранены локально.  
	--hard *commit* — принудительно вернутся к указанному коммиту *commit*, не сохраняя историю и изменения.  
  
  
  
### Переименование/перемещение файла/каталога/символической ссылки:  
  
**git mv** *<file/directory/symlink>* — переименование файла, каталога или символической ссылки.  
**git mv** *<file/directory/symlink>...<destination directory>* — перемещение файла, каталога или символической ссылки.  
	-f (--force) — принудительное переименование или перемещение, даже если целевой объект существует.  
	-k -- пропустить перемещение или переименование, которое приведёт к ошибке.  
	-n (--dry-run) — ничего не делает, просто показывает, что будет дальше.  
	-v (--verbose) — сообщает имена файлов по мере их перемещения.  
  
  
  
  
### Отмены:  
  
**git reset HEAD** *file_name* — отмена индексации.  
**git checkout** *file_name* — копирует файлы в рабочую дерикторию (удобно использовать для сброса нежелательных изменений в рабочей дериктории).  
  
  
  
  
## Получение SSH-ключа:  
  
1. Подключение к репозиторию через SSH;  
2. Сгенерировать ключ командой ssh-keygen -t rsa -C "your.email@example.com(почта разработчика)" -b 4096;  
3. Выполнить команду cat ~/.ssh/id_rsa.pub;  
4. Сгенерированный вывод разместить в интерфейсе GitHub;  
  
## Отслеживание файлов  
  
.gitignore — текстовый файл, в котором задаются правила для исключения файлов из репозитория.  
Например:  
*.log  
build/  
temp-*  
git ls-files --other --ignored --exclude-standard — список всех игнорируемых файлов  
  
  
  
  
## Настройки:  
  
git config --global user.name "username" — установить имя, которое будет прикреплено к коммиту.  
git config --global user.email "email address" — установить email, который будет прикреплен к коммиту.  
git config --global color.ui auto — включить полезную подсветку командной строки.  
git config --global push.default current — обновлять удаленную ветку с таким же именем, что и локальная, при пуше изменений (если не указано иного).  
git config --global core.editor editor — установить редактор для редактирования сообщений коммита.  
git config --global diff.tool tool — установить программу для разрешения конфликтов при слиянии.  
  