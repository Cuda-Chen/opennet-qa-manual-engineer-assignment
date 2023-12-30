# opennet-qa-manual-engineer-assignment

## Requirements

- waydroid (since I am using Linux host for testing)

## Test cases

### basic (RAD)

- plus
    - 1 + 2 ?= 3
    - 0.1 + 0.2 ?= 0.3
    - (-1) + (-3) ?= -4
    - (-1) + 3 ?= 2
    - 2^31 - 1 + 1 (overflow?)
    - 2^64 - 1 + 1 (overflow?)
- minus
    - 5 - 3 ?= 2
    - 0.2 - 0.2 ?= 0
    - 4 - (-4) ?= 8
    - (-4) - 5 ?= -9
    - 2^(-31) - 1 (overflow?)
    - 2^(-64) - 1 (overflow?)
- multiplication
    - 3 * 4 ?= 12
    - 0 * 5 ?= 0
- division
    - 2 / 3 ?= 0.6...
    - 7 / 2 ?= 3.5
    - -1 / -1 ?= 1
    - 12 / (-4) ?= -3
    - 11 / 0 ?= (something invalid)
- calculation precedence
    - 2^64 * 2^64 ?= 2^128
    - 3 * (4 + 5) ?= 27
    - (2 / (1 * (42 /21))) ?= 1
- sin
    - sin(0) ?= 0
    - sin(pi / 2) ?= 1
    - sin(pi) ?= 0
    - sin(2 pi) ?= 0
- cos
    - cos(0) ?= 1 
    - cos(pi / 2) ?= 0
    - cos(pi) ?= -1
    - cos(2 pi) ?= 1
- tan
    - tan(0) ?= 0
    - tan(pi / 2) ?= INF
    - tan(pi) ?= 0
    - tan(2 pi) ?= 0
- ln
    - ln(10) ?= 2.3025...
    - ln(e) ?= 1
    - ln(1) ?= 0
    - ln(0) ?= (something invalid)
    - ln(-3.3) ?= (something invalid)
- log
    - log(100) ?= 2
    - log(4) ?= 0.6020...
    - log(1) ?= 0
    - log(0) ?= (something invalid)
    - log(-3) ?= (something invalid)
- factorial
    - 5! ?= 120
    - 1! ?= 1
    - 32! ?= ... 
    - 0! ?= 1
    - !3 ?= (something invalid)
- pi
    - pi ?= 3.1415...
    - 2 pi / pi ?= 2
    - 2 pi * 2 pi ?= 4 pi^2
    - pi 3 ?= 3 * pi
- exp
    - e ?= 2.7182...
    - e 2 ?= 2 * 2
    - e / (4 * e) ?= 0.25
- power
    - 2^3 ?= 8
    - (-1)^3 ?= -1
    - 0^3 ?= 0
    - -2^3 ?= -8
    - 3^(-1) ?= 0.3...
    - 0^0 ?= (something invalid) (X)
    - 10^(10^10) ?= 10^1000 (X)
- square root
    - sqrt(25) ?= 5
    - sqrt(2) ?= 1.414...
    - sqrt(-1) ?= (something invalid)
- percentage
    - 6% ?= 0.06
    - -1% ?= -0.01
    - 0% ?= 0
    - 0.1% ?= 0.001
    - %3 ?= (something invalid)

### INV (when pressed)

- sin -> arcsin
- cos -> arccos
- tan -> arctan
- ln -> e^x
- log -> 10^x
- sqrt -> x^2
- 3 * (-4(5 - 6)) ?= 12

### INV

- arcsin
    - arcsin(-1) ?= - pi / 2
    - arcsin(1) ?= pi / 2
    - arcsin(-2) ?= (something invalid)
    - arcsin(1.001) ?= (something invalid)
- arccos
    - arccos(-1) ?= pi
    - arccos(1) ?= pi
    - arccos(-2) ?= (something invalid)
    - arccos(1.001) ?= (something invalid) 
- arctan
    - arctan(-1) ?= -0.785398163...
    - arctan(1) ?= 0.785398163...
- e^x
    - e^1 ?= e
    - e^-2 ?= 1 / e^2
    - e^0 ?= 1
- 10^x
    - 10^2 ?= 100
    - 10^0 ?= 1
    - 10^-4 ?= 0.0001
    - 10^(10^10) ?= 10^100 (X)
    - 3 * 10^3 ?= 3000
- x^2
    - 2^2 ?= 4
    - 1.1^2 ?= 1.21
    - -1^2 ?= -1
    - (-3)^2 ?= 9

### RAD -> DEG

- The top-left corner should flash "DEG"
- (4 / 5) * -3 ?= -2.4

### MISC

- clear (C)
- backspace
