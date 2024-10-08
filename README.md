# Гайд по использованию шаблона
## Создание репозитория из шаблона
1. В шапке репы (возле кнопки `star`) нажать на `use this template`
2. Выбрать `create a new repository`
3. В `owner` выбрать правильный аккаунт-владелец репозитория (TennisBird), задать название репозитория
4. **ВАЖНО! проставить галочку `include all branches`**
5. Настроить по вкусу и завершить создание
## О работе с репозиторием
Как обычно, pull идет до push
- main - ветка для разработки, но напрямую в нее пушить нельзя
  если надо что то добавить, то алгоритм такой
  1. Создать новую ветку из main
  2. Сделать в ней что надо
  3. Запушить
  4. Оформить pull request из этой ветки в main
  5. [если стриггерилась проверка на изменение чужого кода] дождаться ревью от владельцев кода, который вы поменяли
  6. Вмержить pr в main, не забыть нажать на `delete branch` (там должно быть имя ветки, в которой вы работали до pr)
- release - ветка, из которой берется релизная версия. В нее все мержится **только из main**  
  > Чтобы не засорять историю коммитов и не видеть сообщение "release has recent commits" с предложением вмержить его обратно в main (это нельзя отключить, приколы гитхаба), лучше выбирать не "merge pull request", а "rebase pull request" (тогда не будет лишних коммитов и оно просто засинхронизирует ветки)
## Инфа о структуре шаблона
- [src](/.src) - исходники

    > **Важно**  
    > фреймворки/заголовочные файлы сюда не складывать; если надо делать инклуды, добавьте директорию include/
  
- [test](/test) - тесты
- [dep](/dep) - внешние зависимости
- [doc](/doc) - документация
- [res](/res) - ресурсные файлы
- [samples](/samples) - какие то шаблоны
- [tools](/tools) - инструменты, служебные скрипты, qol штуки и т.п
- [.config](/.config) - про конфигурацию
- [.build](/.build) - скрипты именно по сборке
- [.github/CODEOWNERS](/.github/CODEOWNERS) - информация о владельцах кода, см. в самом файле
