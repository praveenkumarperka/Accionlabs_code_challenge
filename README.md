# Accionlabs_code_challenge

This challenge is to ensure, we generate a randomly generated list (arbitrary).
And to write a code which can partition it based on equal sums.

Below is the code, I have written to address the above challenge. Please comment if anything is not clear.

# AccionLabs List Partitioning Challenge
# import random function for arbitrary generation of list
import random as rn

# Arbitrary list of integers of any length and in any order
mylist = []
results = []
mylist_length = rn.randint(8, 20)
for list_items in range(1, mylist_length):
    mylist.append(rn.randint(0, mylist_length))
# mylist = [1, 6, 2, 3, 4, 1, 7, 6, 4]
# sorting the list for easy partitioning and to sum them up
mylist.sort(reverse=True)

# dividing the list in 2 equal partitions with length
list_partition = int(len(mylist)/2)
index = 0
list_part1 = mylist[index:list_partition]
list_part2 = mylist[list_partition:len(mylist)]


# Setting up a conditional loop on the descending ordered sorted list
while sum(list_part1) > sum(list_part2):
    list_part2.append(list_part1.pop(len(list_part1) - 1))
if sum(list_part1) == sum(list_part2):
    print("List can be partitioned")
    print("Partitioned Lists are {},{}".format(list_part1, list_part2))

else:
    print("This list cannot be partitioned")
    print("Nearest partitioned list for list1: {}\n "
          "list2:{}\n "
          "list1 Sum is:{}\n "
          "list2 Sum is:{}".format(list_part1,list_part2,sum(list_part1),sum(list_part2)))



