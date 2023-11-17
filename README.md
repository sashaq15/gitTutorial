# base git Commands

git config --global <br>
git init - инициализация репа <br>
git rm -rf .git - удалить папку с репозиторием <br>
git status - гит статус <br>
git add ${file} - отслеживать ${file} <br>
git add --all - отслеживать состояние всех файлов в папке <br>
git add . - добавить текующую папку для отслеживания ( все файлы в папке, автоматом будут добавлены)  <br>
git commit -m   - добавить коммит <br>
git log   - просмотреть историю коммитов <br>
git remote add origin {url репа} - добавить удалённый репозиторий в локальный  <br>
git remote -v   - Показывает связанные удалённые репозитрии  <br>
git push -u origin master                 Флаг -u(связывает локальную ветку с одноименной удалённой, надо юзать при первом связывании локального и удалённого)  <br>











```mermaid
graph LR;
  untracked -- "git add" --> staged;
  staged    -- "???"     --> tracked/comitted;

%% стрелка без текста для примера: 
  A --> B;
``` 