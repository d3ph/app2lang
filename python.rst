Почему python?
--------------
Python — интерпретируемый язык программирования. Интерпретируемые языки программирования исполняются инструкция за инструкцией, в отличии от компилируемых языков программирования, которые полностью транслируются в исполняемое представление(например в машинный код). Интерпретируемые языки программирования обычно предоставляют интерактивный интерпретатор, в котором можно выполнять инструкции.

.. code-block:: python

    >>> 1 + 2
    3
    >>> help([])
    >>> a = []
    >>> a.append(1)
    >>> a
    [1]
    >>> import this

Модуль
------
Файл содержащий определения и инструкции написанные на python. [#]_

.. code-block:: python

    import grep  # подключение модуля grep

Пакет
-----
группа модулей объединённая общим пространством имён. [#]_

.. code-block:: python

    import test.test_grep # подключение модуля test_grep из пакета test

Функция
-------
именованная последовательность инструкций, которая может быть повторно использована. [#]_ [#]_

.. code-block:: python

    # всё что следует до возврата отступа на уровень def является
    # определением функции grep, принимающей два аргумента line_source и pattern
    def grep(line_source, pattern): 
        # инструкция pass означает, что ничего делать не надо
        # используется она для удовлетворения интерпретатора python
        # который очень строго относится к структуре кода и отступов
        pass 
    grepper.grep(["a","b","c",], "[ab]")  # вызов функции grep. определение функции закончилось строчкой ранее

Класс
-----
шаблон для создания объектов [#]_ [#]_

.. code-block:: python

    class Grepper:  # всё что следует до возврата отступа на уровень class является определением класса Grepper
    # определение метода grep, идентичного функции grep объявленной выше. 
    # Отличается тем, что первым аргументом(self) методу передаётся объект на котором был вызван этот метод
    # объект передаётся явно, потому что иначе нельзя получить доступ к аттрибутам и методам объекта
        def grep(self, line_source, pattern):  
            pass
    grepper = Grepper()  # создание объекта grepper класса Grepper. определение класса закончилось строчкой ранее
    grepper.grep(["a", "b", "c", ], "[ab]")  # вызов метода grep на объекте grepper
    # внутри метода self будет указывать на grepper

Итератор
--------
Объект позволяющий проходить по всем элементам контейнера. [#]_ [#]_

.. code-block:: python

    >>> lines = [ 'line1', 'line2', 'line3', ]
    >>> for line in lines:
    ...     print(line)
    ... 
    line1
    line2
    line3
    >>> line_iterator = lines.__iter__()
    >>> try:
    ...     while True:
    ...             line = line_iterator.__next__()
    ...             print(line)
    ... except StopIteration:
    ...     pass
    ... 
    line1
    line2
    line3

__name__
--------
Имя модуля если модуль импортируется или __main__ если модуль исполняется. [#]_

.. code-block:: python

    # ivan.py
    print(__name__)

    # interpreter
    >>> import ivan
    ivan

.. code-block:: sh

    $ python ivan.py 
    __main__

sys.argv
--------
Список аргументов переданных программе. Аргументы являются строками.
Первым аргументом указывается путь к исполняемому модулю. [#]_

.. code-block:: python

    # ivan.py
    import sys
    print(sys.argv)

.. code-block:: sh

    $ python ivan.py 
    ['ivan.py']

    $ python ivan.py 1 b
    ['ivan.py', '1', 'b']

Стандартные потоки ввода-вывода
-------------------------------
Соединяют приложение со средой исполнения позволяя получать(stdin) и выводить(stdout) текст. [#]_

.. code-block:: python

    >>> import sys
    >>> sys.stdin
    <_io.TextIOWrapper name='<stdin>' mode='r' encoding='UTF-8'>
    >>> sys.stdout
    <_io.TextIOWrapper name='<stdout>' mode='w' encoding='UTF-8'>


.. [#] http://docs.python.org/3/tutorial/modules.html
.. [#] http://docs.python.org/3/tutorial/modules.html#packages
.. [#] http://en.wikipedia.org/wiki/Subroutine
.. [#] http://docs.python.org/3/tutorial/controlflow.html#defining-functions
.. [#] http://en.wikipedia.org/wiki/Object-oriented_programming
.. [#] http://en.wikipedia.org/wiki/Class_(computer_science)
.. [#] http://en.wikipedia.org/wiki/Iterator
.. [#] http://docs.python.org/3/library/stdtypes.html#iterator-types
.. [#] http://docs.python.org/3/library/sys.html#sys.argv
.. [#] http://stackoverflow.com/questions/419163/what-does-if-name-main-do
.. [#] http://en.wikipedia.org/wiki/Standard_streams
