
[Height Checker](https://leetcode.com/explore/learn/card/fun-with-arrays/523/conclusion/3228/)  

O(n) solution
```
class Solution {
    func heightChecker(_ heights: [Int]) -> Int {
        var heightCounts = Array(repeating: 0, count: 101)
        for h in heights {
            heightCounts[h] += 1
        }
        var count = 0
        var index = 0
        for i in 0..<heights.count {
            while heightCounts[index] == 0 {
                index += 1
            }
            if heights[i] != index {
                count += 1
            }
            heightCounts[index] -= 1
        }
        return count
    }
}
```
