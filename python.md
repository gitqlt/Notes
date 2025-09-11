Python3: Interpreted, interactive, object-oriented programming language
====

#### -B : don't write .pyc (__pycache__) files on import
    $ python3 -B <script>

#### debug output with trace
    $ python3 -B -m trace --trace <script> <arg>

#### interactive input
    $ echo 'import myMock; myMock.mock()' | PYTHONPATH=/... python3 -B <script> <interactive-environment starting subcommand>

#### pdb with interactive input
    $ PYTHONPATH=/... python3 -B -m pudb <script> <interactive-environment starting subcommand>
    >>> import myMock; myMock.mock()
