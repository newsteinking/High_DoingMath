chapter 2: visualizing Data with Graphs
============================================
이 장에서는 다양한 데이터를 mathplotlib를 통해 표현하는 방법을 배우도록 하겠다.


2.1 Understanding the Cartesian Coordinate Plane
-----------------------------------------------------

다음처럼 숫자가 새겨진 라인을 생각해 보자.


.. image:: ./img/chapter2-1.png

아래는 Cartesian coordinate plane 을 나타낸다.


.. image:: ./img/chapter2-1.png

Working with Lists and Tuples
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
그래프를 그릴때 list,tuple을 많이 사용하게 될것이다.


Iterating over a List or Tuple
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python

    >>> l = [1, 2, 3]
    >>> for item in l:
    print(item)

    >>> l = [1, 2, 3]
    >>> for index, item in enumerate(l):
    print(index, item)


Creating Graphs with Matplotlib
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python

    >>> x_numbers = [1, 2, 3]
    >>> y_numbers = [2, 4, 6]

    >>> from pylab import plot, show
    >>> plot(x_numbers, y_numbers)
    [<matplotlib.lines.Line2D object at 0x7f83ac60df10>]

    plot(x_numbers, y_numbers, marker='o')

    plot(x_numbers, y_numbers, 'o')


Graphing the Average Annual Temperature in New York City
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python

    from pylab import plot, show

    nyc_temp = [53.9, 56.3, 56.4, 53.4, 54.5, 55.8, 56.8, 55.0, 55.3, 54.0, 56.7, 56.4, 57.3]


    years = range(2000, 2013)



    #plot(nyc_temp, marker='o')

    years = range(2000, 2013)
    plot(years, nyc_temp, marker='o')

    show()

Comparing the Monthly Temperature Trends of New York City
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python

    from pylab import plot,show
    from pylab import legend
    legend([2000, 2006, 2012])


    nyc_temp_2000 = [31.3, 37.3, 47.2, 51.0, 63.5, 71.3, 72.3, 72.7, 66.0, 57.0, 45.3, 31.1]
    nyc_temp_2006 = [40.9, 35.7, 43.1, 55.7, 63.1, 71.0, 77.9, 75.8, 66.6, 56.2, 51.9, 43.6]
    nyc_temp_2012 = [37.3, 40.9, 50.9, 54.8, 65.1, 71.0, 78.8, 76.7, 68.8, 58.0, 43.9, 41.5]

    months = range(1, 13)

    #plot(months, nyc_temp_2000, months, nyc_temp_2006, months, nyc_temp_2012)

    #===============================================================================
    # plot(months, nyc_temp_2000)
    # plot(months, nyc_temp_2006)
    # plot(months, nyc_temp_2012)
    #===============================================================================

    plot(months, nyc_temp_2000, months, nyc_temp_2006, months, nyc_temp_2012)

    show()

Customizing Graphs
~~~~~~~~~~~~~~~~~~~~~~~


Adding a Title and Labels
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python

    from pylab import plot, show, title, xlabel, ylabel, legend

    months = range(1, 13)

    nyc_temp_2000 = [31.3, 37.3, 47.2, 51.0, 63.5, 71.3, 72.3, 72.7, 66.0, 57.0, 45.3, 31.1]
    nyc_temp_2006 = [40.9, 35.7, 43.1, 55.7, 63.1, 71.0, 77.9, 75.8, 66.6, 56.2, 51.9, 43.6]
    nyc_temp_2012 = [37.3, 40.9, 50.9, 54.8, 65.1, 71.0, 78.8, 76.7, 68.8, 58.0, 43.9, 41.5]


    plot(months, nyc_temp_2000, months, nyc_temp_2006, months, nyc_temp_2012)

    title('Average monthly temperature in NYC')
    xlabel('Month')
    ylabel('Temperature')
    legend([2000, 2006, 2012])

    show()