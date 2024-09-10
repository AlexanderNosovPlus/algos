# Оглавление:
1. Two sums [[#Two sums]]

# Two sums:
## Условия задачи


 1. Two Sum
 Easy
 Topics
 Companies
 Hint
 Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

 You may assume that each input would have exactly one solution, and you may not use the same element twice.

 You can return the answer in any order.

Example 1:

 Input: nums = [2,7,11,15], target = 9
 Output: [0,1]
 Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
 Example 2:

 Input: nums = [3,2,4], target = 6
 Output: [1,2]
 Example 3:

 Input: nums = [3,3], target = 6
 Output: [0,1]
 

 Constraints:

 2 <= nums.length <= 104
 -109 <= nums[i] <= 109
 -109 <= target <= 109
 Only one valid answer exists.
 

 Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?

[1, 2 ,3], target = 5
Output: [1,2]

## Регистрация мыслей

 Идея регистрировать в хешмепе число и индекс. пробегаться по массиву и искать есть ли в мэпе число, соответствующее разнице таргета и текущего числа.
 По идее это O(n) по времени и по памяти


## Ошибки
[[Algos. Bugs#Задача Two sums.#]]

## Код решения

``` python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        dct = {}
        lst = []
        for i in range(len(nums)):
            if (target - nums[i]) in dct:
                lst.append(i)
                lst.append(nums[dct - nums[i]]) 
                
            else:
                dct[nums[i]] = i       
        return lst 
```        
 

 
