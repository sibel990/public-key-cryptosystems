# implementation of First System of http://dx.doi.org/10.37394/23209.2022.19.10
from random import randint
from sympy.polys.domains import ZZ

def generate_keys(q, d):
    """
    Generates public and private keys for a user using the given parameters.

    Args:
    q: The size of the finite field GF(q).
    d: The degree of the public polynomial p(x).

    Returns:
    A tuple containing the public key (p(x), Q(x)) and the private key f(x).
    """

    # 1. Select a random polynomial p(x) of degree d.
    p = [randint(0, q - 1) for _ in range(d)]

    # 2. Get an irreducible polynomial Q(x) of degree d+1.
    Q = find_irreducible_polynomial(q, d + 1)

    # 3. Use the Euclidean algorithm to find f(x) satisfying p(x)f(x) = 1 (mod Q(x)).
    f = extended_gcd(p, Q, q)[1]

    # 4. Return the public key (p(x), Q(x)) and the private key f(x).
    return (p, Q), f

def find_irreducible_polynomial(q, degree):
    """
    Finds an irreducible polynomial of the given degree over GF(q).

    Args:
    q: The size of the finite field GF(q).
    degree: The desired degree of the irreducible polynomial.

    Returns:
    An irreducible polynomial of degree `degree` over GF(q).
    """

    # Implementation of a polynomial irreducibility test is needed here.
    # This can be done using various algorithms like Rabin's test.
    # For simplicity, we'll assume a function `is_irreducible` is available.

    while True:
        # Generate random polynomials of the desired degree until an irreducible one is found.
        poly = [randint(0, q - 1) for _ in range(degree + 1)]
        poly = ZZ.map(poly)
        if is_irreducible(poly, q):
            return poly


def extended_gcd(a, b, q):
    """
    Computes the extended Euclidean algorithm for polynomials over GF(q).

    Args:
    a: The first polynomial.
    b: The second polynomial.
    q: The size of the finite field GF(q).

    Returns:
    A tuple containing the greatest common divisor (gcd) of a and b,
    and the coefficients s and t such that gcd(a, b) = s * a + t * b.
    """
    # Implementation of the extended Euclidean algorithm for polynomials is needed here.
    # This involves polynomial arithmetic operations in GF(q).
    from sympy.polys.galoistools import gf_gcdex
    return gf_gcdex(a, b, q, ZZ)


def is_irreducible(poly, q):
    """
    Checks if a polynomial is irreducible over GF(q).

    Args:
    poly: The polynomial to test.
    q: The size of the finite field GF(q).

    Returns:
    True if the polynomial is irreducible, False otherwise.
    """

    # Implementation of an irreducibility test is needed here.
    # This can be done using various algorithms like Rabin's test.

    from sympy.polys.galoistools import gf_irred_p_rabin
    return gf_irred_p_rabin(poly, q, ZZ)


# Example usage:
q = 257 # Size of the finite field (must be prime)
d = 128 # Degree of the public polynomial
public_key, private_key = generate_keys(q, d)

print("Public key:", public_key)
print("Private key:", private_key)
