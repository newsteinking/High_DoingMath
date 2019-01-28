chapter 3: Describing Data With Statstics
==============================================
이 장에서는 통계치를 가지고 한번 파이썬 코드를 짜보자.


3.1 Finding the Mean
------------------------------


.. code-block:: python

    >>> shortlist = [1, 2, 3]
    >>> sum(shortlist)
    6

    >>> len(shortlist)
    3


.. code-block:: python


    '''
    Calculating the mean
    '''
    def calculate_mean(numbers):
        s = sum(numbers)
        N = len(numbers)
    # Calculate the mean
        mean = s/N
        return mean


    if __name__ == '__main__':
        donations = [100, 60, 70, 900, 100, 200, 500, 500, 503, 600, 1000, 1200]
        mean = calculate_mean(donations)
        N = len(donations)
        print('Mean donation over the last {0} days is {1}'.format(N, mean))


Finding the Median
~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python


    samplelist = [4, 1, 3]
    samplelist.sort()
    samplelist
    [1, 3, 4]

    '''
    Calculating the median
    '''
    def calculate_median(numbers):
        N = len(numbers)
        numbers.sort()
        # Find the median
        if N % 2 == 0:
            # if N is even
            m1 = N/2
            m2 = (N/2) + 1
            # Convert to integer, match position
            m1 = int(m1) - 1
            m2 = int(m2) - 1
            median = (numbers[m1] + numbers[m2])/2
        else:
            m = (N+1)/2
            # Convert to integer, match position
            m = int(m) - 1
            median = numbers[m]
        return median

    if __name__ == '__main__':
        donations = [100, 60, 70, 900, 100, 200, 500, 500, 503, 600, 1000, 1200]
        median = calculate_median(donations)
        N = len(donations)
        print('Median donation over the last {0} days is {1}'.format(N, median))

Finding the Mode and Creating a Frequency Table
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Finding the Most Common Elements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python


    >>> simplelist = [4, 2, 1, 3, 4]
    >>> from collections import Counter
    >>> c = Counter(simplelist)
    >>> c.most_common()
    [(4, 2), (1, 1), (2, 1), (3, 1)]

    >>> c.most_common(1)
    [(4, 2)]

    >>> c.most_common(2)
    [(4, 2), (1, 1)]

    >>> mode = c.most_common(1)
    >>> mode
    [(4, 2)]
    v >>> mode[0]
    (4, 2)
    w >>> mode[0][0]
    4

Finding the Mode
~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python


    '''
    Calculating the mode
    '''
    from collections import Counter
    def calculate_mode(numbers):
        c = Counter(numbers)
        mode = c.most_common(1)
        return mode[0][0]
    if __name__=='__main__':
        scores = [7, 8, 9, 2, 10, 9, 9, 9, 9, 4, 5, 6, 1, 5, 6, 7, 8, 6, 1, 10]
        mode = calculate_mode(scores)
        print('The mode of the list of numbers is: {0}'.format(mode))