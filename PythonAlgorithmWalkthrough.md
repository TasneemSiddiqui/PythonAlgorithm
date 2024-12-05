<h1>Update a File Through a Python Algorithm</h1>

Algorithm for file updates in Python
Project description
Scenario: I am a security professional who is required to regularly update a file that identifies the employees who can access restricted content at a health care company. The contents of the file change based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses that are allowed to sign into the restricted subnetwork, and a remove list that identifies which employees must be removed from this allow list.

My task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, I must remove those IP addresses from the file containing the allow list.
Open the file that contains the allow list
The name of the file is "allow_list.txt". We need to assign this file string/path to the variable import_file. Next, we use a with statement to open it. We use the vairable file to store the file while we work with it inside the with statement. To open the file, we use the open() function and pass the parameters import_file and string "r" to indicate that we are opening the file for the purpose of reading it:
 
Read the file contents
Next, we use the .read() method to convert the contents of the allow list file into a string so that we can read them. This string will be stored in a variable called ip_addresses and will follow the with header:

 
Convert the string into a list
In order to remove individual IP addresses from the allow list, IP addresses need to be in a list format. Therefore, we use the .split() method to convert the ip_addresses string into a list:

 
Iterate through the remove list
A second list called remove_list contains all of the IP addresses that should be removed from the ip_addresses list:

 

The following is the header for a for loop that will iterate through the remove_list. element will be used as the loop variable:

 
Remove IP addresses that are on the remove list
In the body of the iterative statement, we will add code that will remove all the IP addresses from the allow list that are also on the remove list. First, we create a conditional that evaluates if the loop variable element is part of the remove_list. Then, within that conditional, we apply the .remove() method to the ip_addresses list and remove the IP addresses identified in the loop variable element:

 
Update the file with the revised list of IP addresses 
Now that these IP addresses have been removed from the ip_address variable, we can complete the algorithm by updating the file with this revised list. To do this, we must first convert the ip_addresses list back into a string using the .join() method. We apply .join() to the string "\n" in order to separate the elements in the file by placing them on a new line:

 

Finally, we use another with statement and the .write() method to write over the file assigned to the import_file variable. We use the string "w" as a parameter to indicate that we are opening the file for the purpose of writing to it:

 
Summary
The following is the complete algorithm:
 

To summarize, we first imported a file named allow_list.txt and then opened it in order to read it and save the contents into a string variable. Next, we split this string into a list format. We then iterated through each of the IP addresses in this list and checked using a conditional if the IP address is also in the remove list. If so, we removed it from our allow list. Lastly, we converted the list back into string format and reopened allow_list.txt to overwrite its contents with our updated allow list.
