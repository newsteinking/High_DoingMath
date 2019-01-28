chapter 1: Working with numbers
=======================================


1.1 Basic Mathematical Operations
-------------------------------------

... code-block:: python

    >>> 1 + 2
    3
    >>> 1 + 3.5
    4.5
    >>> -1 + 2.5
    1.5
    >>> 100 – 45
    55
    >>> -1.1 + 5
    3.9

    >>> 3 * 2
    6
    >>> 3.5 * 1.5
    5.25

    >>> 3 / 2
    1.5
    >>> 4 / 2
    2.0

    >>> 3 // 2
    1

    >>> -3 // 2
    -2

    >>> 9 % 2
    1

    >>> 2 ** 2
    4
    >>> 2 ** 10
    1024
    >>> 1 ** 10
    1

    >>> 8 ** (1/3)
    2.0

    >>> 5 + 5 * 5
    30
    >>> (5 + 5) * 5
    50

1.2 Labels: Attaching Names to Numbers
-------------------------------------


... code-block:: python

    >>> a = 3
    >>> a + 1
    4
    >>> a = 5
    >>> a + 1
    6

1.3 Different Kinds of Numbers
-------------------------------------

... code-block:: python

    >>> type(3)
    <class 'int'>
    >>> type(3.5)
    <class 'float'>
    >>> type(3.0)
    <class 'float'>

    >>> int(3.8)
    3
    >>> int(3.0)
    3

    >>> float(3)
    3.0

1.4 Working with Fractions
----------------------------

... code-block:: python

    u >>> from fractions import Fraction
    v >>> f = Fraction(3, 4)
    w >>> f
    Fraction(3, 4)

    >>> Fraction(3, 4) + 1 + 1.5
    3.25

    >>> Fraction(3, 4) + 1 + Fraction(1/4)
    Fraction(2, 1)

1.5 Complex Numbers
----------------------------

... code-block:: python

    >>> a = 2 + 3j
    >>> type(a)
    <class 'complex'>

    >>> a = complex(2, 3)
    >>> a
    (2 + 3j)

    >>> b = 3 + 3j
    >>> a + b
    (5 + 6j)
    >>> a - b
    (-1 + 0j)

    >>> a * b
    (-3 + 15j)
    >>> a / b
    (0.8333333333333334 + 0.16666666666666666j)

    >>> z = 2 + 3j
    >>> z.real
    2.0
    >>> z.imag
    3.0

    >>> z.conjugate()
    (2 - 3j)

    >>> (z.real ** 2 + z.imag ** 2) ** 0.5
    3.605551275463989

    >>> abs(z)
    3.605551275463989


1.6 Getting User Input
----------------------------

... code-block:: python


    u >>> a = input()
    v 1

    >>> a
    w '1'

    >>> s1 = 'a string'
    >>> s2 = "a string"

    >>> a = '1'
    >>> int(a) + 1
    2
    >>> float(a) + 1
    2.0

    >>> int('2.0')
    Traceback (most recent call last):
    File "<pyshell#26>", line 1, in <module>
    int('2.0')
    ValueError: invalid literal for int() with base 10: '2.0'

    >>> a = float(input())
    3/4
    Traceback (most recent call last):
    File "<pyshell#25>", line 1, in <module>
    a=float(input())
    ValueError: could not convert string to float: '3/4'

1.8 Handling Exceptions and Invalid Input
---------------------------------------------

... code-block:: python

    >>> try:
    a = float(input('Enter a number: '))
    except ValueError:
    print('You entered an invalid number')

    Enter a number: 3/4
    u You entered an invalid number

    >>> a = input('Input an integer: ')

    >>> a = int(input())
    1
    >>> a + 1
    2

    >>> a = int(input())
    1.0
    Traceback (most recent call last):
    File "<pyshell#42>", line 1, in <module>
    a=int(input())
    ValueError: invalid literal for int() with base 10: '1.0'

    >>> 1.1.is_integer()
    False

    >>> 1.0.is_integer()
    True

1.9 Fractions and Complex Numbers as Input
---------------------------------------------

... code-block:: python

    >>> a = Fraction(input('Enter a fraction: '))
    Enter a fraction: 3/4
    >>> a
    Fraction(3, 4)

    >>> a = Fraction(input('Enter a fraction: '))
    Enter a fraction: 3/0
    Traceback (most recent call last):
    File "<pyshell#2>", line 1, in <module>
    a = Fraction(input('Enter a fraction: '))
    File "/usr/lib64/python3.3/fractions.py", line 167, in __new__
    raise ZeroDivisionError('Fraction(%s, 0)' % numerator)
    ZeroDivisionError: Fraction(3, 0)

    >>> try:
    a = Fraction(input('Enter a fraction: '))
    except ZeroDivisionError:
    print('Invalid fraction')
    Enter a fraction: 3/0
    Invalid fraction

    >>> z = complex(input('Enter a complex number: '))
    Enter a complex number: 2+3j
    >>> z
    (2+3j)

    >>> z = complex(input('Enter a complex number: '))
    Enter a complex number: 2 + 3j
    Traceback (most recent call last):
    File "<pyshell#43>", line 1, in <module>
    z = complex(input('Enter a complex number: '))
    ValueError: complex() arg is a malformed string


1.10 Writing Programs That Do the Math for You
--------------------------------------------------

Calculating the Factors of an Integer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

... code-block:: python

    >>> def is_factor(a, b):
    if b % a == 0:
    return True
    else:
    return False

    >>> is_factor(4, 1024)
    True

    >>> for i in range(1, 4):
    print(i)

    >>> for i in range(5):
    print(i)

    >>> for i in range(1,10,2):
    print(i)

    '''
    Find the factors of an integer
    '''
    def factors(b):
    u for i in range(1, b+1):
    if b % i == 0:
    print(i)
    if __name__ == '__main__':
    b = input('Your Number Please: ')
    b = float(b)
    v if b > 0 and b.is_integer():
    factors(int(b))
    else:
    print('Please enter a positive integer')

    Your Number Please: 25
    1
    5
    25

    Your Number Please: 15.5
    Please enter a positive integer


Generating Multiplication Tables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

... code-block:: python


    '''
    enhanced_multi_table.py

    Multiplication table printer: Enter the number and the number
    of multiples to be printed
    '''

    def multi_table(a, n):
        for i in range(1, n+1):
            print('{0} x {1} = {2}'.format(a, i, a*i))

    if __name__ == '__main__':
        try:
            a = float(input('Enter a number: '))
            n = float(input('Enter the number of multiples: '))
            if not n.is_integer() or n < 0:
                print('The number of multiples should be a positive integer')
            else:
                multi_table(a, int(n))
        except ValueError:
            print('You entered an invalid input')

Converting Units of Measurement
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

... code-block:: python

    '''
    enhanced_unit_converter_exit_power.py

    Unit converter:

    Miles and Kilometers
    Kilograms and Pounds
    Celsius and Fahrenheit

    '''

    def print_menu():
        print('1. Kilometers to Miles')
        print('2. Miles to Kilometers')
        print('3. Kilograms to Pounds')
        print('4. Pounds to Kilograms')
        print('5. Celsius to Fahrenheit')
        print('6. Fahrenheit to Celsius')

    def km_miles():
        km = float(input('Enter distance in kilometers: '))
        miles = km / 1.609

        print('Distance in miles: {0}'.format(miles))

    def miles_km():
        miles = float(input('Enter distance in miles: '))
        km = miles * 1.609

        print('Distance in kilometers: {0}'.format(km))

    def kg_pounds():
        kg = float(input('Enter weight in kilograms: '))
        pounds = kg * 2.205

        print('Weight in pounds: {0}'.format(pounds))

    def pounds_kg():
        pounds = float(input('Enter weight in pounds: '))
        kg = pounds / 2.205

        print('Weight in kilograms: {0}'.format(kg))

    def cel_fahren():
        celsius = float(input('Enter temperature in celsius: '))
        fahrenheit =  celsius* (9 / 5) + 32
        print('Temperature in fahrenheit: {0}'.format(fahrenheit))

    def fahren_cel():
        fahrenheit = float(input('Enter temperature in fahrenheit: '))
        celsius = (fahrenheit - 32)*(5/9)
        print('Temperature in celsius: {0}'.format(celsius))

    if __name__ == '__main__':
        print_menu()

        while True:
            choice = input('Which conversion would you like to do? ')

            if choice == '1':
                km_miles()
            if choice == '2':
                miles_km()

            if choice == '3':
                kg_pounds()
            if choice == '4':
                pounds_kg()

            if choice == '5':
                cel_fahren()
            if choice == '6':
                fahren_cel()

            answer = input('Do you want to exit? (y) for yes ')
            if answer == 'y':
                break


Finding the Roots of a Quadratic Equation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

... code-block:: python


    '''
    Quadratic equation root calculator
    '''
    def roots(a, b, c):
        D = (b*b - 4*a*c)**0.5
        x_1 = (-b + D)/(2*a)
        x_2 = (-b - D)/(2*a)
        print('x1: {0}'.format(x_1))
        print('x2: {0}'.format(x_2))
    if __name__ == '__main__':
        a = input('Enter a: ')
        b = input('Enter b: ')
        c = input('Enter c: ')
        roots(float(a), float(b), float(c))