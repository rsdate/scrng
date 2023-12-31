# The Shadow Algorithm

## Introduction

The Shadow algorithm is an algorithm for generating random digits that utilizes an standard (and popular) algorithm as the core generator. This algorithm is called LFSR (Linear Feedback Shift Register). The algorithm first uses LFSR to generate a random string of digits. The algorithm then uses Python's built-in random number generator the further scramble the output of the LFSR.

## Installation
You can check out this repository directly and then build the
package:
```
git clone https://github.com/rsdate/scrng
cd scrng
pip install .
```
Or you can simply install the official package from PyPI:
```
pip install scrng
```
It is up to you which approach you use to install this package.

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

## Distrubution
When you check out this repository, you might see that there is
already a ```dist``` folder. This folder is ignored by default when
the package is being built, but is included folder for the
sake of distrubution. If you want, you can distrubute the
pre-built tar archive to your friends.

## Notes
* IMPORTANT! The **maximum** number of digits generated with the best possible randomness is 5000. Although you can request more than 5000 digits, they might not be generated using the full power of the generator.  Make sure that numsToGen * lenOfSeed is not over 5000 if you want the best random numbers from this algorithm.
* A follow up to this package called ```sctest``` is being planned. I will most likely release this package in the near future.