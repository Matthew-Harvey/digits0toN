# How Many Digits between 1 and N
https://edabit.com/challenge/j9zed4GnykS48W6vh My solution to this problem in Python and JavaScript.

## Python

def digits(number):
	number-=1
	n = 10**(len(str(number))-1)
	digits = 0
	while n>=1:
		digits+=(number-n+1)*len(str(number))
		number=n-1
		n//=10
	return digits
  
  ## JavaScript
  
  function digits(number) {
  if (typeof number === 'bigint') {
    return bigIntDigits(number)
  }

	let amountOfDigits = 0

  for (let i = 1; i <= number; i *= 10) {
    amountOfDigits += number - i
  }

  return amountOfDigits
}

function bigIntDigits(number) {
  const bigNumber = BigInt(number)
	let amountOfDigits = 0n

  for (let i = 1n; i <= bigNumber; i *= 10n) {
    amountOfDigits += bigNumber - i
  }

  return amountOfDigits
}
