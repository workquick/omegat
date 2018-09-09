Начальные настройки
*******************

Создание проекта
================

Посмотрите 10-минутное видео на сайте http://omegat.org/ в разделе Get Started
для ознакомления с программой в целом. Коммент к видео:

- Начальная часть про глоссарий в эксель - можно пока не обращать внимания - не существенно
- В видео на начало сентября 2018 года версия программы 4.0.1, мы устанавливаем другую, интерфейс в части содержания меню различается, shortcuts немного другие.
- в конце видео говорят про tags - мы это не используем (речь про форматирование)
- обратить внимание на структуру папок, которую создает программа при создании проекта


Шаги для начала работы с программой (смотрите также картинку ниже):

- Создайте новую директорию под названием omegat (или любым удобным для вас), лучше в директории Documents
- Затем откройте программу OmegaT.
- Project -> New
- В окне Create a New Project найдите созданную вами директорию omegat и кликните на нее два раза курсором
- В окне Create a New Project в поле Folder Name допишите \\sanctions-EN
- нажмите Save
- В появившемся окне настроек выберите языки en-us, ru-ru
- отметьте галочкой Remove Tags
- нажмите OK

.. figure::  images/create_new_project00.jpg
   :align:   center

   Создаем проект под названием sanctions-EN в директории omegat


.. figure::  images/create_new_project01_remove_tags.jpg
   :align:   center

   Языки и Remove Tags


.. figure::  images/create_new_project02_proj_files_win_close.jpg
   :align:   center

   Это окно можно пока закрыть

Editor
======

- Options -> Editor
- Галочка у Insert the best fuzzy match
- Minimal similarity: 75
- Удалить "Fuzzy" в поле Prefix
- Галочка у Allow translation to be equal to source

.. figure::  images/editor_view.jpg
   :align:   center


Cпелл-чекеры
============

Чтобы в программе работала проверка орфографии, нужно:

- Создать директорию spellcheckers (конкретное название не важно) в директории omegat (можно в любом другом удобном месте)
- Затем идем Options -> Preferences -> Spellcherker
- Отметить галочкой Automatically check the spelling of text
- Скоприровать url и перейти на страницу по url в интернете в вашем веб-браузере
- Скачать файл en_US.zip и сохранить его в созднанной на этапе 1 папке spellcheckers
- Скачать файл ru_RU.zip и сохранить его там же
- Распаковать zip-файлы (не создавая при этом вложенные директории внутри папки spellcheckers)
- В окне Preference - Spellcherker, нажав на кнопку Browse..., указать путь к папке с файлами спелл-чекера
- В поле Dictionaries already installed должны появиться названия словарей

См. картинки ниже

.. figure::  images/spellcheckers_en_US_zip_donwload.jpg
   :align:   center

   Скачивание файлов со словариями для орфографии

.. figure::  images/spellcheckers_ru_RU_zip_donwload.jpg
  :align:   center

.. figure::  images/spellcheckers_unzipped_files.jpg
   :align:   center

   Распакованные файлы со словарями

.. figure::  images/spellcheckers_view.jpg
   :align:   center

   Так должно выглядеть в финале

.. warning::
   Названия языков каждого из созданных проектов должны совпадать с языками в спелл-чекере.

Открыв проект, перейдите Project -> Properties, и убедитесь, что там точно
такие же названия языков, что и в Options -> Preferences -> Spellcherker,
а именно en-us, ru-ru

Подробности или для лучшего понимания сайт разработчиков:
http://omegat.sourceforge.net/manual-latest/en/chapter.spellchecker.html

Сегментирование
===============

Этот раздел можно пропустить при начальной настройке.
Речь идет о дополнительных правилах разбивки текста на предложения.
Добавлять правила можно постепенно по мере работы с программой.

- Options -> Segmentation
- Кнопка Add ближе к правому верхнему углу
- Замените текст в поле New Language and Country на my-rules, а в соседнем поле на .*
- Кнопкой Move up поднимите эту новую строку на самый верх
- Затем, нажимая другую кнопку Add, которая ниже и относится к Segmentation rules, можно добавлять правила сегментирования - используемые мною приведены ниже
- Когда все или часть правил добавлены, нажимаем ок


Одно полезное правил для принудительной разбивки предложения.
В поле break/exception поставьте галочку. В поле **before** впишите ``\.”``,
а в поле **after** впишите	``\s``.

Остальные правила, чтобы программа не разбивала предложения там, где не надо.
Перед этими правилами ставить галочку НЕ нужно.

Правила сегментирования применяются сразу ко всем проектам

=====================   ==============================
before	                after
=====================   ==============================
``стр\.``               \\s
``[А-Я]\.[А-Я]\.``      \\s
``г\.``                 \\s[А-я]
``д\.``                 \\s\\d
``долл\.``              \\s[США]|\\s[а-я]
``[A-Z]\.[A-Z]\.``      \\s
``U\.S\.``              \\s[a-z]|\\sGovernment|\\sLNG
``L\.L\.P\.``           \\s[a-z]
``U\.K\.``              \\s
``Stat\.``              \\s\\d
``S\.A\.``              \\s[a-z]
``E\.O\.``              \\s[0-9]|\\s[a-z]
``U\.S\.C\.``           \\s\\d
``SEC\.``               \\s\\d
``Sec\.``               \\s\\d
``sec\.``               \\s\\d
=====================   ==============================

.. figure::  images/segm_setup_00_init_view.jpg
   :align:   center

   Начальный вид

.. figure::  images/segm_setup_01_add_my_rules_move_up.jpg
   :align:   center

.. figure::  images/segm_setup_02_my_rules_at_top.jpg
   :align:   center

   Переместили наши правила на самый верх

.. figure::  images/segm_setup_02_add_rules.jpg
   :align:   center

   Пример добавленных правил

Подробное описание правил в документации разработчиков:

- http://omegat.sourceforge.net/manual-latest/en/chapter.segmentation.html
- http://omegat.sourceforge.net/manual-latest/en/chapter.regexp.html

TM Matches
===========

Options -> Editor -> TM Matches

Заменить весь текст в поле Match display template следующим текстом::

  ${id}. ${diff}
  ${targetText}
  <${score}/${noStemScore}/${adjustedScore}%>
  ${fileShortPath}

.. figure::  images/TM_matches_view.JPG
   :align:   center

Подробности на сайте разработчиков:
http://omegat.sourceforge.net/manual-latest/en/chapter.user.interface.html#match.viewer

View
====

В меню View, отметьте первые две опции по цветам - Mark Translated/Untranslated Segments

Опционально
===========

Автозаполнение
