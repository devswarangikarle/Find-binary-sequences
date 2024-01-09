# Find-binary-sequences
You're given an integer n. Find out the number of all binary sequences of length 2*n such that sum of first n bits is same as sum of last n bits. The anwer can be very large. So, you have to return answer modulo 109+7.

def count_binary_sequences(n):
    MOD = 10**9 + 7

   
    def mod_inverse(x):
        return pow(x, MOD - 2, MOD)

    
    def factorial_mod(x):
        result = 1
        for i in range(1, x + 1):
            result = (result * i) % MOD
        return result

   
    result = factorial_mod(2 * n)
    result = (result * mod_inverse(factorial_mod(n))) % MOD
    result = (result * mod_inverse(factorial_mod(n))) % MOD

    return result


n = int(input())
result = count_binary_sequences(n)
print(result)
