# Оглавление:
1. Two sums [[#Two sums]]
2. Isomorphic Strings [[#Isomorphic Strings (Изоморфные строки)]]

# Two sums:
#week_1
## Ссылка на задачу
https://leetcode.com/problems/two-sum/description/
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
                lst.append(dct[target - nums[i]]) 
                
            else:
                dct[nums[i]] = i       
        return lst 
```        
 


# Isomorphic Strings (Изоморфные строки)
#week_1 

## Ссылка на задачу
https://leetcode.com/problems/isomorphic-strings/description/
## Условия задачи
205. Isomorphic Strings
Easy
Topics
Companies
Given two strings s and t, determine if they are isomorphic.

Two strings s and t are isomorphic if the characters in s can be replaced to get t.

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character, but a character may map to itself.

 

Example 1:

Input: s = "egg", t = "add"

Output: true

Explanation:

The strings s and t can be made identical by:

Mapping 'e' to 'a'.
Mapping 'g' to 'd'.
Example 2:

Input: s = "foo", t = "bar"

Output: false

Explanation:

The strings s and t can not be made identical as 'o' needs to be mapped to both 'a' and 'r'.

Example 3:

Input: s = "paper", t = "title"

Output: true

Example 4:
Input: S = "aaabbb", t = "cccddd"
Output: true

Constraints:

1 <= s.length <= 5 * 104
t.length == s.length
s and t consist of any valid ascii character.

## Регистрация мыслей
Идея в том, чтобы с помощью хеш-мэп составить соответствие для каждого символа между строками и если оно выполняется, то возвращаем истину, а если нет, то ложь. Так же можно сразу проверить длину строк.

Сложность по времени будет O(n) и по памяти O(n)


## Ошибки
Ошибок не было, так как задачу помнил - уже решал в рамках ДЗ к стриму

## Код решения

``` Python
class Solution:
    def isIsomorphic(self, s: str, t: str) -> bool:
        st_m = {}
        ts_m = {}
        if len(s) != len(t):
            return False
        for i in range(len(s)):
            if s[i] not in st_m:
                st_m[s[i]] = t[i]
            else:
                if t[i] != st_m[s[i]]:
                    return False
            if t[i] not in ts_m:
                ts_m[t[i]] = s[i]
            else:
                if s[i] != ts_m[t[i]]:
                    return False
        return True
```