# leetCode_TwoSum
/*
Given an array of integers nums and an integer target, return indices of the two numbers
such that they add up to target.
You may assume that each input would have exactly one solution,
and you may not use the same element twice.
You can return the answer in any order.

Input: numbers = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
*/

fun main(args: Array<String>) {
    //val input = intArrayOf(2,7,11,15)
    var solution = Solution()
    println(solution.twoSum(intArrayOf(2,7,11,15), 22).contentToString())
}

class Solution {
    /*fun twoSum(nums: IntArray, target: Int): IntArray {
    //O(n*n)
        for(i in nums.indices){
            for (j in nums.indices){
                if(nums[i] + nums[j] == target){
                    return intArrayOf(i,j)
                }
            }
        }
        return intArrayOf()
    }*/
    fun twoSum(nums: IntArray, target: Int): IntArray {
        //O(n)
        val memo = HashMap<Int, Int>()
        for(i in nums.indices){
            if(memo.containsKey(nums[i])){
                return intArrayOf(memo[nums[i]]!!, i)
                //memo.get(nums[i])!!
            }
            memo[target - nums[i]] = i
            //memo.put(target - nums[i], i)
        }
        return intArrayOf()
    }
}
