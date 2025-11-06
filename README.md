# count-primes
class Solution(object):
    def countPrimes(self, n):
        if n < 3:
            return 0

        # Initialize a list to track prime numbers
        is_prime = [True] * n
        is_prime[0] = is_prime[1] = False

        # Implement the Sieve of Eratosthenes
        for i in range(2, int(n ** 0.5) + 1):
            if is_prime[i]:
                for j in range(i * i, n, i):
                    is_prime[j] = False

        # Count and return the number of primes
        return sum(is_prime)
