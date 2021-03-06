# Powers

## Pseudo-code

1. The base case $$n = 0$$, and $$x^0 = 1$$
2. If $$n$$ is positive compute recursively $$y=x^{(n/2)}$$
3. If $$n$$ is positive and odd, recursively compute $$x^{(n - 1)}$$
4. If $$n$$ is negative, compute $$x^{-n}$$ until n is positive. Then $$x^n = 1/x^{-n}$$

## Implementation

```javascript

var isEven = function(n) {
    return n % 2 === 0;
};

var isOdd = function(n) {
    return !isEven(n);
};

var power = function(x, n) {
    println("Computing " + x + " raised to power " + n + ".");
    // base case
    if(n === 0) {
        return 1;
    }
    // recursive case: n is negative 
    if(n < 0) {
        return 1 / power(x, -n);
    }
    
    // recursive case: n is odd
    if(isOdd(n)) {
        return x * power(x, n - 1);
    }
    // recursive case: n is even
    if(isEven(n)) {
        var y = power(x, n/2);
        return y * y;
    }
};

var displayPower = function(x, n) {
    println(x + " to the " + n + " is " + power(x, n));
};

displayPower(3, 0);
Program.assertEqual(power(3, 0), 1);
displayPower(3, 1);
Program.assertEqual(power(3, 1), 3);
displayPower(3, 2);
Program.assertEqual(power(3, 2), 9);
displayPower(3, -1);
Program.assertEqual(power(3, -1), 1/3);
Program.assertEqual(power(4, -1), 1/4);
Program.assertEqual(power(5, -5), Math.pow(5, -5));

```