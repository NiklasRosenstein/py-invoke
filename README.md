# pyinvoke

Pyinvoke is a very simple module that is intended to make invoking Python
applications in modules less pain. Since Python's `-m` option will load the
module as `__main__` module and not as the module it is intended to be loaded
as, you can get interesting errors.

    $ python -m module.main
    Traceback (most recent call last):
      File "module/main.py", line 7, in <module>
        from .stuff import ham
    SystemError: Parent module '' not loaded, cannot perform relative import

Well, shucks! Works as expected with pyinvoke!

    $ pip3 install pyinvoke
    $ python3 -m pyinvoke module:main
