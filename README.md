# CAP-392-

# CAP392-CA3
Q 1 
class Solution {
    public int[] runningSum(int[] nums) {
        
        for (int i = 1; i < nums.length; i++) {
            nums[i] = nums[i] + nums[i - 1];
        }
        
        return nums;
    }
}

Q2

class Solution {
    public int maximumWealth(int[][] accounts) {
        
        int max = 0;
        
        for (int i = 0; i < accounts.length; i++) {
            
            int sum = 0;
            
            for (int j = 0; j < accounts[i].length; j++) {
                sum = sum + accounts[i][j];
            }
            
            if (sum > max) {
                max = sum;
            }
        }
        
        return max;
    }
}

Q3

class Solution {
    public boolean containsDuplicate(int[] nums) {
        
        for (int i = 0; i < nums.length; i++) {
            
            for (int j = i + 1; j < nums.length; j++) {
                
                if (nums[i] == nums[j]) {
                    return true;
                }
            }
        }
        
        return false;
    }
}

Q4

class Solution {
    public void reverseString(char[] s) {
        
        int start = 0;
        int end = s.length - 1;
        
        while (start < end) {
            
            char temp = s[start];
            s[start] = s[end];
            s[end] = temp;
            
            start++;
            end--;
        }
    }
}

Q5 

class Solution {
    public boolean isPalindrome(String s) {
        
        s = s.toLowerCase();
        
        String newString = "";
        
        for (int i = 0; i < s.length(); i++) {
            
            char ch = s.charAt(i);
            
            if ((ch >= 'a' && ch <= 'z') ||
                (ch >= '0' && ch <= '9')) {
                
                newString = newString + ch;
            }
        }
        
        int start = 0;
        int end = newString.length() - 1;
        
        while (start < end) {
            
            if (newString.charAt(start) != newString.charAt(end)) {
                return false;
            }
            
            start++;
            end--;
        }
        
        return true;
    }
}

Q8

import java.util.*;

class RecentCounter {
    
    Queue<Integer> q;

    public RecentCounter() {
        q = new LinkedList<>();
    }

    public int ping(int t) {
        
        q.add(t);
        
        while (q.peek() < t - 3000) {
            q.remove();
        }
        
        return q.size();
    }
}


Q9

class Solution {
    public int[] shuffle(int[] nums, int n) {
        int[] result = new int[nums.length];

        int index = 0;

        for (int i = 0; i < n; i++) {
            result[index] = nums[i];
            index++;

            result[index] = nums[i + n];
            index++;
        }

        return result;
    }
}

Q10

class Solution {
    public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) {
                    return new int[]{i, j};
                }
            }
        }

        return new int[]{};
    }
}

Q11

class Solution {
    public int maxProfit(int[] prices) {
        int maxProfit = 0;

        for (int i = 0; i < prices.length; i++) {
            for (int j = i + 1; j < prices.length; j++) {
                int profit = prices[j] - prices[i];

                if (profit > maxProfit) {
                    maxProfit = profit;
                }
            }
        }

        return maxProfit;
    }
}
