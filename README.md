# The Shadow Algorithm

## Introduction


The Shadow algorithm is an algorithm for generating random digits that 
utilizes an standard (and popular) algorithm as the core generator. This
algorithm is called LFSR (Linear Feedback Shift Register). The algorithm then uses Python's built-in random number generator the further scramble the output of the LFSR.

## Installation
```
git clone https://github.com/rsdate/scrng
cd scrng
pip install .
```

## A Simple Example (in Python)

```
import scrng.main as scrng
print(scrng.scrng())
```
Some dummy output:
```
['2460403941444260529181716075179723041634946086076450300405774318506821593208121188927143953150202887']
```
This example shows the barebones functionality of the ```scrng()``` function. See Parameters for details about customizing the function.
## Parameters
* numsToGen (```int```): How many numbers to generate (default=1)
* lenOfSeed (```int```): How long the the returned numbers should be (default=100)
* strength (```tuple[int, list[int]]```): The first value determines the size of the core generator and the second value determines the taps for the generator (Read about [LFSR](https://en.wikipedia.org/wiki/Linear-feedback_shift_register)) (default=(127, [1, 2, 7]))
## Notes
* IMPORTANT! The **maximum** number of digits generated is 5000. If you request more than 5000 digits, the program will throw an ```OverflowError```. Make sure that numsToGen * lenOfSeed is not over 5000.
* This is the first and **only** version of the package that will be released.

