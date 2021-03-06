Обучение алгоритмов МО
=====

.. _installation:

Введение
------------

Эта инструкция написана для того, чтобы любой желающий мог повторить наш эксперимент и обучить алгоритм ИИ, способный обнаруживать объекты интереса на изображении. Для обучения моделей были использованы ресурсы Google Colab, поэтому требования к аппаратуре довольно низкие. Любой современный ноутбук легко позволит вам выполнить все пункты. Однако для корректной работы потребуется стабильное подключение к Интернету. Эти инструкции были написаны для пользователей, не имеющих опыта работы с ИИ. Если вы относитесь к числу новичков, просто выполняйте шаги по порядку. Примечание: Предполагается, что на момент начала у вас уже есть набор данных из ~ 1000 немаркированных кадров (видео, которое содержит не менее 1000 кадров).

Разметка набора данных
----------------

Установка RemoApp
~~~~~~~~~~~~~~~~~~

RemoApp_ - это приложение, в котором будет производиться разметка изображений. Установка производится через командную строку.
Сначала необходимо установить библиотеку:

.. _RemoApp: https://remo.ai 

>>> pip install remo

Затем инициализировать и запустить:

>>> python -m remo_app init python -m remo_app

Если установка не удалась, попробуйте команду ниже, а затем повторите команды выше.

>>> apt-get update pip install psycopg2==2.8.6

Обработка изображений
~~~~~~~~~~~~~~~~~~

Сначала создайте набор данных, нажав кнопку "CREATE DATASET" (рис. 1) в левом верхнем углу окна программы. Если пустое окно набора данных не появилось, нажмите кнопку "Reload" (рис. 2) на вкладке "Вид" на панели инструментов.

.. figure:: https://github.com/Zenkin/mag_tutorial/blob/main/docs/pictures/CREATE_DATASET.png
   :scale: 50 %
   :align: center
   :alt: map to buried treasure
