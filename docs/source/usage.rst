Обучение алгоритмов МО
=====

.. _installation:

Введение
------------

Эта инструкция написана для того, чтобы любой желающий мог повторить наш эксперимент и обучить алгоритм ИИ, способный обнаруживать объекты интереса на изображении. Для обучения моделей были использованы ресурсы Google Colab, поэтому требования к аппаратуре довольно низкие. Любой современный ноутбук легко позволит вам выполнить все пункты. Однако для корректной работы потребуется стабильное подключение к Интернету. Эти инструкции были написаны для пользователей, не имеющих опыта работы с ИИ. Если вы относитесь к числу новичков, просто выполняйте шаги по порядку. Примечание: Предполагается, что на момент начала у вас уже есть набор данных из ~ 1000 немаркированных кадров (видео, которое содержит не менее 1000 кадров).

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

