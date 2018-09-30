# Gram-Schmidt

Sage wouldn't start up for me one day and the one Gram-Schmidt orthogonalization calculator I could find online was being extremely slow due to poor Wi-Fi, so I decided to write up my own implementation of the algorithm using a custom defined Vector class similar to the one used by Sage (albeit skeletonized).  

# Requirements

* Python 3.x

# Usage

The following are examples denoting usages of the gram_schmidt class:

    from gram_schmidt import *
    from vector import Vector
    
    v1 = Vector([1, 0, 0, 1])
    v2 = Vector([-1, 0, 2, 1])
    v3 = Vector([0, 1, 2, 0])
    v4 = Vector([0, 0, -1, 1])

The below two expressions are equivalent:

    result1 = gram_schmidt(v1, v2, v3, v4)
    result2 = gram_schmidt([v1, v2, v3, v4])
    assert result1 == result2

```normalize``` flag causes gram_schmidt() to return an orthonormal set of vectors (such that magnitude v for v in vectors = 1) with floating point components.

    result1 = gram_schmidt([v1, v2, v3, v4], normalize=True)
    result2 = gram_schmidt(v1, v2, v3, v4, normalize=True)
    assert result1 == result2

```fraction``` flag causes gram_schmidt() to return a set of vectors with fraction components (if the vector components are not already integers) as to improve readability.

    result1 = gram_schmidt([v1, v2, v3, v4], fraction=True)
    result2 = gram_schmidt(v1, v2, v3, v4, fraction=True)
    assert result1 == result2

    # Prints result
    print(result1)

# TODO

* Write a better README
* Optimize code
* Implement the Lenstra–Lenstra–Lovász lattice basis reduction algorithm for factoring polynomials with rational coefficients, which uses the Gram-Schmidt orthogonalization method. 








