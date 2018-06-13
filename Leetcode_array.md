#### 268. Missing Number
```ruby
class Solution:
    def missingNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums.sort()
        miss_v = len(nums)
        for i,j in enumerate(nums):
            #using XOR
            miss_v ^= i^j
        return miss_v
 ```
#### 217. Contains Duplicate
```ruby
class Solution:
    def containsDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """
        nums.sort()
        for i in range(len(nums)-1):
            if nums[i+1]- nums[i] ==0:
                return True
        return False
 ```
 #### 122. Best Time to Buy and Sell Stock II
 ```ruby
 class Solution:
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        profit = 0
        for i in range(len(prices)-1):
            profit += max(0,prices[i+1]-prices[i])
        return profit
 ```
 
 #### 169. Majority Element
 ```ruby
 class Solution:
    def majorityElement(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        s = set(nums)
        for i in s:            
            if nums.count(i) > len(nums)/2:
                return i
 ```
 
 #### 283. Move Zeroes
 ```ruby 
 class Solution:
    def moveZeroes(self, nums):
        """
        :type nums: List[int]
        :rtype: void Do not return anything, modify nums in-place instead.
        """
        for i in nums:
            if i == 0:
                nums.remove(i)
                nums.append(0)
                
 ```
 
 ### 121. Best Time to Buy and Sell Stock
 ```python
 class Solution:
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        min_price,max_profit = float('inf'),0
        for price in prices:
            min_price = min(price,min_price)
            max_profit = max(max_profit,price-min_price)
        return max_profit
 ```
