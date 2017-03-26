Lexer Kata
==========

Facilitator notice: Introduce steps one at the time.

Goals:
    - deal with your own legacy: introducing new cases gradualy prevent you
      from knowing what you will need to handle.
    - think about the domain: you know intutivly how to do it in your head, but
      what are the rules ?


Description
-----------

Make a function/method that given string produce the expected tokens.

Plus operator::

    --- File content ---
    1+1
    --- Produced Tokens ---
    INTEGER "1"
    OPERATOR "+"
    INTEGER "1"

Minus operator::

    --- File content ---
    1-1
    --- Produced Tokens ---
    INTEGER "1"
    OPERATOR "-"
    INTEGER "-1"

Ingore useless spaces::

    --- File content ---
    1 + 1
    --- Produced Tokens ---
    INTEGER "1"
    OPERATOR "+"
    INTEGER "1"

Longer integers::

    --- File content ---
    10 + 10
    --- Produced Tokens ---
    INTEGER "10"
    OPERATOR "+"
    INTEGER "10"

Negative intergers::

    --- File content ---
    -1 + 1
    --- Produced Tokens ---
    INTEGER "-1"
    OPERATOR "+"
    INTEGER "1"

Floats::

    --- File content ---
    1.0 + 1.0
    --- Produced Tokens ---
    FLOAT "1.0"
    OPERATOR "+"
    FLOAT "1.0"

Strings::

    --- File content ---
    "abc" + "def"
    --- Produced Tokens ---
    STRING "abc"
    OPERATOR "+"
    STRING "def"

Strings containing spaces::

    --- File content ---
    "a b c" + "d e f"
    --- Produced Tokens ---
    STRING "a b c"
    OPERATOR "+"
    STRING "d e f"

Strings containing escaped newline::

    --- File content ---
    "a\nb" + "c\nd"
    --- Produced Tokens ---
    STRING "a\\nb"
    OPERATOR "+"
    STRING "c\\nd"

Strings containing escaped quote::

    --- File content ---
    "\"a\"" + "\"b\""
    --- Produced Tokens ---
    STRING "\\"a\\""
    OPERATOR "+"
    STRING "\\"b\\""

Multiline string::

    --- File content ---
    """a
    b""" + """c
    d"""
    --- Produced Tokens ---
    STRING "a\nb"
    OPERATOR "+"
    STRING "c\nd"
