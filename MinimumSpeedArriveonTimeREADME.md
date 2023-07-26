# leet-day12

# Minimum Speed to Arrive on Time

You are given a floating-point number `hour`, representing the amount of time you have to reach the office. To commute to the office, you must take `n` trains in sequential order. You are also given an integer array `dist` of length `n`, where `dist[i]` describes the distance (in kilometers) of the ith train ride.

Each train can only depart at an integer hour, so you may need to wait in between each train ride.

You need to find the minimum positive integer speed (in kilometers per hour) that all the trains must travel at for you to reach the office on time, or return -1 if it is impossible to be on time.

## Approach and Algorithm

To find the minimum speed required for the person to reach the office on time, we can use binary search. We will set the speed limits for binary search from 1 to some upper bound (e.g., 10^7) based on the given constraints.

1. Initialize the `left` and `right` pointers for binary search to 1 and 10^7 + 1, respectively.
2. While `left` is less than `right`, perform binary search:
   - Calculate the `mid` point as `(left + right) / 2`.
   - Calculate the total time taken to travel using this `mid` speed. For each train ride distance `dist[i]`, we calculate `timeTaken += ceil(dist[i] / mid)`.
   - If `timeTaken` is less than or equal to `hour`, update `right = mid`.
   - Else, update `left = mid + 1`.
3. Finally, return `left` as the minimum speed required. If `left` is equal to 10^7 + 1, return -1 as it indicates that it's impossible to reach on time.

## Complexity Analysis

The time complexity of this approach is O(n * log(m)), where `n` is the size of the `dist` vector and `m` is the upper bound of the binary search (10^7 in this case). The space complexity is O(1) as no extra space is used except for variables.
