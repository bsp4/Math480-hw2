Math480-hw2
===========

This is my implementation for the Euclidean division algorithm



def gcd1(a,b):
    try:
        a/b
    except ZeroDivisionError, err:
        print err
        
    a = abs(a)
    b = abs(b)
    if a%b == 0:
        return b
    if a == 0:
        return b  
        
    count = 0
    if a > b:
        while a != b:
            c = 0
            while a - b > c:
                count += 1
                c = count * b
            r = a - c
            a = b
            b = r
            count = 0
        return b 
    else:
        while a != b:
            c = 0
            while b - a > c:
                count += 1
                c = count * a
            r = b - c
            b = a
            a = r
            count = 0
        return a
