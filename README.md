# Harry-Potter-Kata
HarryPotter kata with TDD implementation in Java :
To be honest, i wrote some parts using TDD, but for advanced parts i wrote the code first and then the tests. The tests gave me the opportunity to refactor the code.

# Problem Description
Once upon a time there was a series of 5 books about a very English hero called Harry. 

One copy of any of the five books costs **8 EUR**. 
If, however, you buy two different books from the series, you get a **5% discount** on those two books. 
If you buy 3 different books, you get a **10% discount**. 
With 4 different books, you get a **20% discount**. 
If you go the whole hog, and buy all 5, you get a huge **25% discount**.

Note that if you buy, say, four books, of which 3 are different titles, you get a 10% discount on the 3 that form part of a set, but the fourth book still costs 8 EUR.
 
The mission is to write a piece of code to calculate the price of **any conceivable shopping basket**, giving **as big a discount as possible**.

For example, this set of books costs 51.20 EUR

- 2 copies of the first book (0)
- 2 copies of the second book (1)
- 2 copies of the third book (2)
- 1 copy of the fourth book (3)
- 1 copy of the fifth book (4)

#Some of implemented test cases :

Basic tests
  - assert_equal(0, price([])) // No books ordered
  - assert_equal(8, price([1])) // Book 2 
  - assert_equal(8, price([2])) // Book 3
  - assert_equal(8, price([3])) // Book 4
  - assert_equal(8, price([4])) // Book 5
  - assert_equal(8 * 3, price([1, 1, 1])) 3 * Book 2 ordered 
end

Simple discounts
  - assert_equal(8 * 2 * 0.95, price([0, 1])) // Book 1 + Book 2
  - assert_equal(8 * 3 * 0.9, price([0, 2, 4])) // Book 1 + Book 3 + Book 5
  - assert_equal(8 * 4 * 0.8, price([0, 1, 2, 4])) // Book 1 + Book 2 + Book 3 + Book 5
  - assert_equal(8 * 5 * 0.75, price([0, 1, 2, 3, 4])) // Book 1 + Book 2 + Book 3 + Book 4 + Book 5
end

Several discounts
  - assert_equal(8 + (8 * 2 * 0.95), price([0, 0, 1])) // 2 * Book 1 + Book 2
  - assert_equal(2 * (8 * 2 * 0.95), price([0, 0, 1, 1])) // 2 * Book 1 + 2 * Book 2
  - assert_equal((8 * 4 * 0.8) + (8 * 2 * 0.95), price([0, 0, 1, 2, 2, 3])) // 2 * Book 1 + Book 2 +  2 * Book 3 + Book 4
  - assert_equal(8 + (8 * 5 * 0.75), price([0, 1, 1, 2, 3, 4])) // Book 1 + 2* Book 2 +  Book 3 + Book 4 +  Book 5
end

