Prime-numbers
=============

Came-up with it personally don't know if it exists, working on something harder, been so for the past year.

def prime_numbers(n):
    '''prints the set of prime numbers efficiently'''
    primes = [2,3,5,7]
    int_odd1 = 3
    int_odd2 = 5
    while (int_odd1**2) < n:
        odd_list = []
        i = (int_odd1**2) + 2
        while i < (int_odd2**2):
            odd_list.append(i)
            i += 2
        for p in primes:
            for k in primes:
                if odd_list.count(p*k) == 1:
                    odd_list.remove(p*k)
        for num in odd_list:
            primes.append(num)
        int_odd1 += 2
        int_odd2 += 2
    prime_nums = ""
    counter = 0
    for i in primes:
        counter += 1
        if (counter == 20):
            prime_nums += "\n"
            counter = 0
        prime_nums += str(i) + " "
    print(prime_nums)
