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


