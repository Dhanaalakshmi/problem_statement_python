# Problem_statement_python
# Name: DHANALAKSHMI A
# Reg no: 212223040033

# 1. Student Attendance Analysis
A college maintains the daily attendance details of its students in the form of a list containing student IDs. Some students may have attended multiple sessions on the same day. The administration wants to identify the longest continuous sequence of sessions in which no student ID is repeated. Develop a solution that determines the maximum length of such a sequence.

# Code
```
arr = [101, 102, 103, 101, 104, 105]

left = 0
max_length = 0
seen = set()

for right in range(len(arr)):

    while arr[right] in seen:
        seen.remove(arr[left])
        left += 1

    seen.add(arr[right])

    max_length = max(max_length, right - left + 1)

print(max_length)
```
# Output:
<img width="957" height="623" alt="Screenshot 2026-09-25 112923" src="https://github.com/user-attachments/assets/9cf30587-fc1f-4692-8805-c6d2a65380cc" />

# 2. Online Shopping Price Analysis
An online shopping application stores the prices of products viewed by a customer during a browsing session. The customer wants to identify a continuous range of products that provides the maximum possible total discount value. Given the discount values, determine the maximum value that can be obtained from any continuous range.

# Code
```
arr=list(map(int,input().split()))
curr_sum=arr[0]
max_sum=arr[0]
for i in range(1,len(arr)):
  curr_sum=max(arr[i],curr_sum+arr[i])
  max_sum=max(curr_sum,max_sum)
print(max_sum)
```
# Output:
<img width="572" height="288" alt="Screenshot 2026-09-25 115126" src="https://github.com/user-attachments/assets/b43789ab-d85f-4e84-b6c6-89253607bf44" />

# 3. Rainwater Collection System
A city installs buildings of different heights along a straight road. During rainfall, water gets collected between taller buildings. The engineering team needs to calculate the total amount of water that can remain trapped after heavy rainfall based on the heights of the buildings.

# Code
```
def trap_prefix(height):
    if not height:
        return 0
    n = len(height)
    
    left_max = [0] * n
    right_max = [0] * n
    
    left_max[0] = height[0]
    for i in range(1, n):
        left_max[i] = max(left_max[i-1], height[i])
    
    right_max[n-1] = height[n-1]
    for i in range(n-2, -1, -1):
        right_max[i] = max(right_max[i+1], height[i])
    
    water = 0
    for i in range(n):
        water += min(left_max[i], right_max[i]) - height[i]
    
    return water
print(trap_prefix([3, 0, 2, 0, 4])) 
print(trap_prefix([0,1,0,2,1,0,1,3,2,1,2,1]))
```
# Output:
<img width="1247" height="627" alt="image" src="https://github.com/user-attachments/assets/d18f669d-c37f-422d-b16e-9315a24be17e" />


# 4. Employee Performance Analysis
A company stores the monthly performance scores of an employee for several months. The scores may contain both positive and negative values depending on the employee's performance. Management wants to identify the continuous period during which the employee achieved the highest overall performance.

# Code
```
arr=list(map(int,input().split()))
curr_sum=arr[0]
max_sum=arr[0]
for i in range(1,len(arr)):
  curr_sum=max(arr[i],curr_sum+arr[i])
  max_sum=max(curr_sum,max_sum)
print(max_sum)
```
# Output:
<img width="572" height="288" alt="Screenshot 2026-09-25 115126" src="https://github.com/user-attachments/assets/b43789ab-d85f-4e84-b6c6-89253607bf44" />

# 5. Product Sales Analysis
A retail company stores the daily sales quantity of a product for several consecutive days. Due to seasonal changes, some days may have negative adjustments. The company wants to identify the period that produced the highest multiplication of sales-related values. Develop a solution to determine this maximum product.

# Code
```
def max_sales_product_brute(nums):
    if not nums:
        return 0
    
    result = nums[0]
    for i in range(len(nums)):
        prod = 1
        for j in range(i, len(nums)):
            prod *= nums[j]
            result = max(result, prod)
    
    return result
print(max_sales_product_brute([2, 3, -2, 4]))
```
# Output:
<img width="967" height="472" alt="image" src="https://github.com/user-attachments/assets/5ec69f3e-273c-47f1-bc1a-5020075ea422" />

# 6. Customer Purchase History
An e-commerce application stores the product IDs purchased by a customer in chronological order. The same product may appear multiple times. The system needs to determine the longest sequence of consecutive purchases in which every product ID is unique.

# Code
```
arr = [101, 102, 103, 101, 104, 105]

left = 0
max_length = 0
seen = set()

for right in range(len(arr)):

    while arr[right] in seen:
        seen.remove(arr[left])
        left += 1

    seen.add(arr[right])

    max_length = max(max_length, right - left + 1)

print(max_length)
```
# Output:
<img width="957" height="623" alt="Screenshot 2026-09-25 112923" src="https://github.com/user-attachments/assets/9cf30587-fc1f-4692-8805-c6d2a65380cc" />

# 7. Bank Transaction Analysis
A bank stores transaction amounts for a customer's account. A continuous group of transactions may add up to a specific target amount. The auditing system needs to determine how many different continuous transaction groups produce exactly the specified amount.
# Code :
```
def count_subarrays_sum_k(transactions, target):
    prefix_count = {0: 1}
    prefix_sum = 0
    count = 0
    
    for t in transactions:
        prefix_sum += t
        if prefix_sum - target in prefix_count:
            count += prefix_count[prefix_sum - target]
        prefix_count[prefix_sum] = prefix_count.get(prefix_sum, 0) + 1
    
    return count
print(count_subarrays_sum_k([1, 2, 3, -2, 5], 3))
```
# Output:
<img width="826" height="412" alt="image" src="https://github.com/user-attachments/assets/c209a1b0-e0f2-4fed-ade7-b669d3644bce" />

# 8. Employee Skill Grouping
A company receives a list of employee skill codes represented as strings. Employees having the same set of characters in their skill codes belong to the same skill category, even if the characters appear in a different order. The HR system needs to organize employees into appropriate skill groups.
# Code :
```
def group_skills(codes):
    groups = {}
    
    for code in codes:
        key = ''.join(sorted(code))
        groups.setdefault(key, []).append(code)
    
    return list(groups.values())
print(group_skills(["abc", "bca", "cab", "xyz", "zyx"]))
```
# Output:
<img width="702" height="297" alt="image" src="https://github.com/user-attachments/assets/b4e951e1-6c66-4179-a9dd-7b49928c74ca" />

# 9. Network Packet Analysis
A network monitoring system receives packet identifiers in chronological order. The system must determine the longest sequence of consecutive packets whose identifiers form a continuous numerical sequence, regardless of their original order in the incoming data.
# Code:
```
def longest_consecutive_packets_sort(packets):
    if not packets:
        return 0
    
    nums = sorted(set(packets))
    longest = 1
    current = 1
    
    for i in range(1, len(nums)):
        if nums[i] == nums[i-1] + 1:
            current += 1
        else:
            current = 1
        longest = max(longest, current)
    
    return longest
print(longest_consecutive_packets_sort([100, 4, 200, 1, 3, 2]))
```
# Output:
<img width="767" height="525" alt="image" src="https://github.com/user-attachments/assets/5450e1c8-6320-4ccf-bf38-ff0b7f5a4959" />

# 10. Hospital Appointment Scheduling
A hospital receives appointment requests represented by starting and ending times. Some appointments overlap with each other. The scheduling system needs to combine overlapping appointment periods so that the final schedule contains only non-overlapping time ranges.
# Code;
```
def merge_appointments(intervals):
    if not intervals:
        return []
    
    intervals.sort(key=lambda x: x[0])
    merged = [intervals[0]]
    
    for start, end in intervals[1:]:
        if start <= merged[-1][1]:
            merged[-1][1] = max(merged[-1][1], end)
        else:
            merged.append([start, end])
    
    return merged
print(merge_appointments([[1,3],[2,6],[8,10],[15,18]]))
```
# Output;
<img width="788" height="415" alt="image" src="https://github.com/user-attachments/assets/bd3f0af9-870b-43ca-a669-c344b7847cd5" />



