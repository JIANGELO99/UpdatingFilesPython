<h1>Update a file through a Python algorithm</h1>

<h2>Project Description</h2>
At my organization, access to restricted content is controlled with an allow list of IP addresses. The "allow_list.txt" file identifies these IP addresses. A separate remove list identifies IP addresses that should no longer have access to this content. I created an algorithm to automate updating the "allow_list.txt" file and remove these IP addresses that should no longer have access.
<br />

<h2>Project walk-through:</h2>
For the first part of the algorithm, I opened the "allow_list.txt" file. First, I assigned this file name as a string to the import_file variable: <br/>
<p align="center">
<img width="358" height="62" alt="image" src="https://github.com/user-attachments/assets/ec4a8f9f-0b73-4a29-a706-202a0929ec0b" /></p>
<p align="center">
Then, I used a with statement to open the file:<br />
<img width="543" height="64" alt="image" src="https://github.com/user-attachments/assets/50f26d72-c307-4dde-8ef4-c0ce57ec2010" /></p>
In my algorithm, the with statement is used with the .open() function in read mode to open the allow list file for the purpose of reading it. The purpose of opening the file is to allow me to access the IP addresses stored in the allow list file. The with keyword will help manage the resources by closing the file after exiting the with statement. In the code with open(import_file, "r") as file:, the open() function has two parameters. The first identifies the file to import, and then the second indicates what I want to do with the file. In this case, "r" indicates that I want to read it. The code also uses the as keyword to assign a variable named file; file stores the output of the .open() function while I work within the with statement.<br />

<p align="center">
<br />
Reading the file contents:  <br/>
<img width="628" height="92" alt="image" src="https://github.com/user-attachments/assets/4f89caca-3fa0-40e2-8df2-043f6ead2698" /></p>

<p align="center">
<br />
Convert the string into a list: <br/>
<img width="524" height="65" alt="image" src="https://github.com/user-attachments/assets/925278a3-818b-4e4c-8f1d-0885bd4b9352" /></p>


<br />
A key part of my algorithm involves iterating through the IP addresses that are elements in the remove_list. To do this, I incorporated a for loop: <br/>
<p align="center">
<img width="329" height="97" alt="image" src="https://github.com/user-attachments/assets/8872ad52-2913-40dc-80c2-097f578b7c79" /></p>
The for loop in Python repeats code for a specified sequence. The overall purpose of the for loop in a Python algorithm like this is to apply specific code statements to all elements in a sequence. The for keyword starts the for loop. It is followed by the loop variable element and the keyword in. The keyword in indicates to iterate through the sequence ip_addresses and assign each value to the loop variable element.<br />


<br />
My algorithm requires removing any IP address from the allow list, ip_addresses, that is also contained in remove_list.  Because there were not any duplicates in ip_addresses, I was able to use the following code to do this:  <br/>
<p align="center">
<img width="535" height="167" alt="image" src="https://github.com/user-attachments/assets/c859881f-18c1-4ed5-bd13-50dfe6012c37" /></p>

<p align="center">
<br />
Updating the file with the revised list of IP addresses:  <br/>
<img width="625" height="66" alt="image" src="https://github.com/user-attachments/assets/c6ed8272-216c-4267-84ca-e21dd65998d8" />
<img width="427" height="119" alt="image" src="https://github.com/user-attachments/assets/68a365cd-b0a9-4405-8ddd-0a406d015124" />
</p>
<br />In this case I wanted to write the updated allow list as a string to the file "allow_list.txt". This way, the restricted content will no longer be accessible to any IP addresses that were removed from the allow list. To rewrite the file, I appended the .write() function to the file object file that I identified in the with statement. I passed in the ip_addresses variable as the argument to specify that the contents of the file specified in the with statement should be replaced with the data in this variable.<br />

<h2> Summary</h2>
I created an algorithm that removes IP addresses identified in a remove_list variable from the "allow_list.txt" file of approved IP addresses. This algorithm involved opening the file, converting it to a string to be read, and then converting this string to a list stored in the variable ip_addresses. I then iterated through the IP addresses in remove_list. With each iteration, I evaluated if the element was part of the ip_addresses list. If it was, I applied the .remove() method to it to remove the element from ip_addresses.. After this, I used the .join() method to convert the ip_addresses back into a string so that I could write over the contents of the "allow_list.txt" file with the revised list of IP addresses.<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
