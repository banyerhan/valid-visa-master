# valid-visa-master

### author : Nightfury

It is mean that valid your visa, master card for online purpose check payment.

I was explained below.

 1. Prefix 4xxxxx -> this card is VISA
  2. Issuer Identifier: 440804
  3. Account number   : 123456789
  4. Run Luhn Algo to check if card number valid
     Step 1:
       Double the alternate digits starting from the first digit.
       From card number:
	   4408 0412 3456 7890
           ^ ^  ^ ^  ^ ^  ^ ^  --> to double on step 1

       (4+4) (0+0) (0+0) (1+1) (3+3) (5+5) (7+7) (9+9)
         8     0     0     2     6     10    14    18

     Step 2:
        For each result of step 1, if the value is bigger than
	9 we need to substract by 9 so each value is less than 10.
	After that we append all of them

        8     0     0     2     6     10    14    18
	                               ^     ^     ^ --> need to substract by 9

        Hence we have:

	8  +  0  +  0  +  2  +  6  +  1  +  5  +  9 = 31

     Step 3:
        Now add all the non-doubled digits from the credit card number
        From card number:
	  4408 0412 3456 7890
           ^ ^  ^ ^  ^ ^  ^ ^ --> to process on step 3

	   Hence we have: 4 + 8 + 4 + 2 + 4 + 6 + 8 + 0 = 36

      Step 4:
       Add the values calculated in step 2 and step 3 together
       We have 31+36 = 67

      Step 5 :
        Take the value calculated in step 4 and calculate the remainder when it is
	divided by 10. If the remainder is zero, then it's a valid number, otherwise
	it's invalid.

	So we have 67 % 10, reminder is 7 not 0 means this card number is invalid

      If we change the check digit to 3 we will have on step 3 values 39 and hence we have
      70 on step 4 and 70 % 0 -> reminder is 0 -> means card number is valid.


