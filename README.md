# base git Commands

**git config --global** <br>
**git init** - инициализация репа <br>
**git rm -rf .git** - удалить папку с репозиторием <br>
**git status** - гит статус <br>
**git status --ignored**  -гит статус + игнорируемые файлы <br>
**git add ${file}** - отслеживать ${file} <br>
**git add --all** - отслеживать состояние всех файлов в папке <br>
**git add .** - добавить текующую папку для отслеживания ( все файлы в папке, автоматом будут добавлены)  <br>
**git commit -m**  - добавить коммит <br>
**git log**   - просмотреть историю коммитов <br>
**git remote add origin {url репа}** - добавить удалённый репозиторий в локальный  <br>
**git remote -v**  - Показывает связанные удалённые репозитрии  <br>
**git push -u origin master**                 Флаг -u(связывает локальную ветку с одноименной удалённой, надо юзать при первом связывании локального и удалённого)  <br>
**git commit --amend -m**   - изменить сообщение последнего коммита (head)  <br>
**git commit --amend --no-edit** - добавить новый файл в коммит <br>
**git restore --staged <file>**  - убрать файл из стейдж <br>
**git restore --staged .** - убрать все файлы папки из стейдж <br>
**git reset --hard <hash>** - откатиться до <hash> коммита ( все коммиты идущие перед ним будут стёрты, он станет head) <br>
**git restore <file>** - откатить изменения, которые не попали ни в стейдж ни в коммит(файлы модифайд) <br>
**git diff** - Эта команда сравнит последнюю закоммиченную версию файла  с текущей (модифайд) версией. (по умолчанию команда git diff не показывает изменения в staged-файлах — только в modified.
Чтобы всё-таки просмотреть изменения в staged, нужно использовать флаг --staged: git diff --staged. ) <br> 
**git clone <url реппозитория>** - Она создаст копию удалённого репозитория на вашем компьютере  <br>
Команда git clone автоматически связывает локальный и удалённый репозиторий.  <br>
То есть если в GitHub-репозитории что-то поменяется (например, добавятся коммиты), вам не нужно будет заново клонировать его. <br>
Достаточно будет выполнить команду, которая обновит вашу копию. <br>
**git branch** - просмотреть ветки проекта <br>
**git branch <название_ветки>** - добавить ветку <br>
**git checkout <название_ветки>** - переключиться на другую ветку <br>
**git checkout -b <название_ветки>** - создать ветку и сразу переключиться на неё <br>
**git diff <название_ветки1> <название_ветки2>** - сравнить две ветки <br>
**git merge <название векти>** - слияние веток <br>
**git branch -D <название ветки>** - удалить ветку(поглащаемую)  Удаление локальной ветки через Git не удаляет ветку на GitHub! <br> 
**git pull** - Забрать изменения из удалённого репозитория <br>



<br> <br> <br>
## .gitignore 
Если строка начинается с #, то это комментарий, и .gitignore не будет его учитывать.
вот так можно писать комментарии; <br>
**<file>**  - git будет игноривать абсолютно все файлы с именем <file> <br>
Символ звёздочки (*) соответствует любой строке, включая пустую. Если такой символ используется в шаблоне в .gitignore, значит, файл будет проигнорирован вне зависимости от того, что будет на месте звёздочки. <br>
игнорировать все файлы, которые заканчиваются на .jpeg <br>
**/*.jpeg**
Косая черта, или слеш (/), указывает на каталоги. Если шаблон в .gitignore начинается со слеша, то Git проигнорирует файлы или каталоги только в корневой директории. <br>
игнорировать todo.txt в корне репозитория <br>
**/todo.txt** <br>
**!<file>**- не игнорировать файлы с названием <file> <br>
<br> <br> <br>
## Fork 
«Форк» создаёт копию репозитория в аккаунте GitHub. Такая копия будет полностью независима. Изменения, которые вы внесёте, не будут синхронизированы с исходным репозиторием. <br>
В процессе «форка» создаётся копия всех файлов, истории коммитов и веток. Эта копия сохраняется в вашей учётной записи GitHub. <br> <br> <br>

## Пулл реквест
Пул-реквест — это запрос на рассмотрение предлагаемых изменений и часть процесса ревью. <br>
Запрос на изменения можно инициировать двумя способами: через ссылку, которую Git выводит после создания ветки, или через интерфейс GitHub. <br>
После создания пул-реквеста ваши коллеги сделают ревью — оценят предложенные вами правки и оставят свои комментарии. <br>
По результатам ревью ваши правки могут быть приняты в основную ветку проекта или возвращены на доработку.  <br>

## Подробное описание git 

Обычно git pull — это первая команда, которую вводит разработчик, как только открывает код проекта, чтобы начать с ним работать. <br>
Дополнительно git pull и git merge выполняют перед тем, как создать пул-реквест. <br>
При командной работе, особенно в больших командах, основная ветка часто успевает «убежать» вперёд, пока вы подготавливаете свои изменения. <br>
Поэтому перед созданием пул-реквеста рекомендуется сначала подтянуть изменения из основной ветки, объединить их с вашей, решить все возможные конфликты и лишь затем сделать push.<br>

**$ git checkout main # перешли в main**<br>
**$ git pull # подтянули новые изменения в main** <br>
**$ git checkout my-branch # вернулись в рабочую ветку my-branch** <br>
**$ git merge main # влили main в новую ветку my-branch** <br>
**$ git push -u origin my-branch** # отправили ветку my-branch в удалённый репозиторий ** <br>
<br>

## Работа с удалённым репозиторием шпаргалки
**git push -u origin my-branch**(от англ. push, «толкнуть», «протолкнуть») — отправь новую ветку my-branch в удалённый репозиторий и свяжи локальную ветку с удалённой,  <br>
чтобы при дополнительных коммитах можно было писать просто git push без -u; <br>
**git push my-branch** — отправь дополнительные изменения в ветку my-branch, которая уже существует в удалённом репозитории; <br>



## Алгоритм-шпаргалка для создания PR  

1. Склонировать репозиторий. <br>
- Если вы не участник проекта, предварительно сделать «форк» исходного репозитория. <br>
2. На странице репозитория или «форка» нажать кнопки: Code → SSH → скопировать ссылку. <br>
3. Выполнить команду git clone <ссылка на репозиторий>. <br>
4. Создать ветку для вашей задачи: git checkout -b my-task-branch-name. <br>
5. Добавить и «закоммитить» изменения, которые вы хотите внести в проект. <br>
6. «Запушить» ветку: git push --set-upstream origin HEAD или git push -u origin my-task-branch-name. <br>
- GitHub (с помощью Git) выведет ссылку на создание PR. По ней нужно перейти. <br>
- PR можно также создать через интерфейс GitHub. <br>
7. Сообщить о пул-реквесте ревьюеру. <br>
- Иногда ревьюеры назначаются автоматически, тогда сообщать не нужно. <br>
8. Обсуждать с ревьюером предлагаемые изменения и вносить правки, пока эти изменения не будут одобрены (пока не будет получен «апрув»).  <br>


+ Если кто-то добавил конфликтующие изменения в main, пока ваш PR был на ревью, нужно разрешить конфликт:  <br>
1. Обновить main: git checkout main && git pull. <br>
2. Влить main в свою ветку: git checkout my-task-branch-name && git merge main. <br>
3. Разрешить конфликты слияния с помощью IDE или вручную. <br>
4. Создать коммит слияния: git commit --no-edit или git commit -m 'merge main'. <br>
5. Сделать git push своей ветки. <br>
6. Нажать кнопку Merge или подождать, пока её нажмёт кто-то ещё.  <br>
7. Ещё раз обновить main, чтобы «подтянуть» ваши изменения в основную ветку локального репозитория: git checkout main && git pull. <br>


## Алгоритм-шпаргалка для разрешения конфликтов слияния <br>

1. Открыть проект в IDE (VS Code, IDEA или другие). <br>
2. Открыть файл, в котором есть конфликт. <br>
3. Выбрать, какие части файла нужно взять из одной ветки, а какие — из другой. <br>
4. Когда конфликты разрешены, сделать коммит: git commit --no-edit или git commit -m 'merge branch <название ветки>'. <br>
