# Python Lambda Function

### a small, anonymous function that can be defined in a single line of code

    variable_name = lambda arguments: expression

Example #1

    square = lambda x: x**2
    result = square(5)
    print(result)

    #Output: 25

Example #2

    add = lambda x, y: x + y
    result = add(5, 6)
    print(result)

    #Output: 11

### Lambda function can also be used as parameter for other functions

    my_list = [1, 2, 3, 4, 5]
    result = list(map(lambda x: x**2, my_list))
    print(result)

`map()` function applies given function to each elements of list

    #Output: [1, 4, 9, 16, 25]
***

    my_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    result = list(filter(lambda x: x%2 == 0, my_list))
    print(result)

`filter()` function creates a list of elements for which function is True

    #Output: [2, 4, 6, 8, 10]
***

    my_list = [1, 2, 3, 4, 5]
    result = reduce(lambda x, y: x*y, my_list)
    print(result)

`reduce()` function is used to apply a particular function passed in its argument to all of the list elements mentioned in the sequence passed along.

    #Output: 120