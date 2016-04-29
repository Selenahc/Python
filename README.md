# Python
Python codes

#Description
1.       Write a program that prompts the user for a filename. Open the file, and read it one line at a time. For each line split the line into a list of words called line_list. For each word in the current line_list, look to see if it is in a list called script_list. If the word is not in script_list, add it to the script_list. Sort the script_list alphabetically.

2.       Within the same program define a function called freq_count(). This function accepts a str and a list of words as arguments. It traverses the list of words and searches each word and counts the occurrences of the substring str within the word. Print each word along with the number of substring occurrences found.

3.       Test your program with the romeo.txt file that comes as a text file resource with our textbook. After reading the file to build and sort script_list, pass script_list into the freq_count() function.

#Here is my code:

fname = raw_input('Please enter the file name:')
fhand = open(fname)

script_list = list()   
for line in fhand:
     line_list = line.split()
     for word in line_list:
         if word not in script_list:
            script_list.append(word)
script_list.sort()
print(script_list)


def freq_count(substr,list):
     start_po = 0
     count = 0
     for word in list:
         if word.find(str(substr)) != -1:
             start_po = word.find(str,start_po)
             count = count + 1
     return(str(word) + str(count))
