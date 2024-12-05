<h1>Update a File Through a Python Algorithm</h1>

<h2>Project description</h2>

At my health care company, restricted content can only be accessed by employees with an IP address that are in <code>"allow_list.txt"</code> file. For employees that should no longer have access to this content, their IP address appears in a list named <code>"remove_list"</code>. I created an algorithm using Python to check whether the allow list contains any IP addresses identified in <code>"remove_list"</code>. If so, my algorithm removes those IP addresses from <code>"allow_list.txt"</code>. 


<h2>Open the file that contains the allow list</h2>
We need to assign the file string/path for <code>"allow_list.txt"</code> to the variable <code>import_file</code>. Next, we use a <code>with</code> statement to open it. We use the vairable file to store the file while we work with it inside the <code>with</code> statement. To open the file, we use the <code>open()</code> function and pass the parameters <code>import_file</code> and string <code>"r"</code> to indicate that we are opening the file for the purpose of reading it:

![Python01](https://github.com/user-attachments/assets/23d60b84-5ae8-4a90-81a7-ee70bb796bce)

<h2>Read the file contents</h2>
Next, we use the <code>.read()</code> method to convert the contents of the allow list file into a string so that we can read it. This string will be stored in a variable called <code>ip_addresses</code> and will follow the <code>with</code> header:

![Python02](https://github.com/user-attachments/assets/ad91d032-6d06-45d8-a9e1-d8fb24871c1e)
 
<h2>Convert the string into a list</h2>
In order to remove individual IP addresses from the allow list, IP addresses need to be in a list format. Therefore, we use the <code>.split()</code> method to convert the <code>ip_addresses</code> string into a list:

![Python03](https://github.com/user-attachments/assets/2dd44ba7-1c1f-42da-b6eb-776d38da6568)
 
<h2>Iterate through the remove list</h2>
A second list called <code>remove_list</code> contains all of the IP addresses that should be removed from the <code>ip_addresses list</code>:

![Python04](https://github.com/user-attachments/assets/f880ce7c-ebe1-4f3e-88fa-edaa8001ac1e)

The following is the header for a <code>for</code> loop that will iterate through the <code>remove_list</code>. <code>element</code> will be used as the loop variable:

![Python05](https://github.com/user-attachments/assets/d1916f4f-0136-41de-b939-49ccbf42ef04)

<h2>Remove IP addresses that are on the remove list</h2>
In the body of the iterative statement, we will add code that will remove all the IP addresses from the allow list that are also on the remove list. First, we create a conditional that evaluates if the loop variable <code>element</code> is part of the <code>remove_list</code>. Then, within that conditional, we apply the <code>.remove()</code> method to the <code>ip_addresses</code> list and remove the IP addresses identified in the loop variable <code>element</code>:

![Python06](https://github.com/user-attachments/assets/a94a14ee-b392-4dd8-b3f6-61390fdbdafc)

<h2>Update the file with the revised list of IP addresses</h2>
Now that these IP addresses have been removed from the <code>ip_addresses</code> variable, we can complete the algorithm by updating the file with this revised list. To do this, we must first convert the <code>ip_addresses</code> list back into a string using the <code>.join()</code> method. We apply <code>.join()</code> to the string <code>"\n"</code> in order to separate the elements in the file by placing them on a new line:

![Python07](https://github.com/user-attachments/assets/c9d2da8f-1a15-4bf1-b812-43bd575476ba)

Finally, we use another <code>with</code> statement and the <code>.write()</code> method to write over the file assigned to the <code>import_file</code> variable. We use the string <code>"w"</code> as a parameter to indicate that we are opening the file for the purpose of writing to it:

![Python08](https://github.com/user-attachments/assets/79d75cd4-04b5-4163-b4a0-31fbfc027c2c)
 
<h2>Summary</h2>
The following is the complete algorithm:
 
![Python09](https://github.com/user-attachments/assets/3a0ad88c-a96e-4df1-b2f2-1823f95d7e9a)

To summarize, we first imported a file named <code>allow_list.txt</code> and then opened it in order to read it and save the contents into a string variable. Next, we split this string into a list format. We then iterated through each of the IP addresses in this list and checked using a conditional if the IP address is also in the remove list. If so, we removed it from our allow list. Lastly, we converted the list back into string format and reopened <code>allow_list.txt</code> to overwrite its contents with our updated allow list.

