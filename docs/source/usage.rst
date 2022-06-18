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
       :scale: 100 %
       :align: center
       :alt: Create dataset

       Рисунок 1
       
       
 .. figure:: https://github.com/Zenkin/mag_tutorial/blob/main/docs/pictures/Релоад.png
       :scale: 100 %
       :align: center
       :alt: Reload

       Рисунок 2       

После создания первого набора данных вы можете авторизоваться в Remo. Кнопку, которую нужно нажать для начала авторизации, вы можете найти в левом верхнем углу. Если после авторизации ваш ник не отображается в окне кабинета, нажмите на "Reload" еще раз.

Давайте разметим изображения. Щелкните на пустом наборе данных, который был создан ранее, а затем нажмите "ADD DATA" (рис. 3). На данном этапе у вас еще нет аннотаций, поэтому на следующем шаге выберите "Add image only". Затем, используя открывшееся окно, залейте подготовленные изображения (можно загрузить неархивированную папку).

.. figure:: https://github.com/Zenkin/mag_tutorial/blob/main/docs/pictures/CREATE_DATASET.png
       :scale: 100 %
       :align: center
       :alt: Reload

       Рисунок 2

Creating recipes
----------------

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']
