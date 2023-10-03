## Task 3

## Question 1: Amber turning has hoping for Frothly to be acquired by a potential competitor which fell through, but visited their website to find contact information for their executive team. What is the website domain that she visited? 

First, find Ambers IP address.
```
index="botsv2" Amber sourcetype="pan:traffic"
```
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/7ebd75b3-7200-487b-ad0e-dbacc99fe998)

Next we want to find the website that Amber visited, we have the following information
- She is in the beer industry
- Her IP address is 10.0.101
```
index="botsv2" 10.0.2.101 sourcetype="stream:http" "*Beer*" 
| dedup site
| table site
```
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/0dbc44fe-81b7-4826-ba01-e496ba017652)

Break down of the final command
- index="botsv2": This restricts the search to the "botsv2" index, meaning it only looks for data within this particular index.

- 10.0.2.101: This filters the data based on the IP address "10.0.2.101". It narrows down the search to events originating from this specific IP address.

- sourcetype="stream:http": This narrows the search further by specifying the sourcetype "stream:http". Sourcetypes help Splunk identify the format of the data being indexed. In this case, it looks for events specifically of the type "stream:http".

- "*Beer*": This part of the search queries for events where the term "Beer" appears anywhere in the data. The asterisks (*) are wildcards, meaning they match any characters (or none) in the specified position. So, it searches for occurrences of "Beer" within any part of the events.

- | dedup site: After retrieving events based on the specified criteria, the dedup command is used to remove duplicates. It ensures that only unique values of the "site" field are retained in the results. If there are multiple events with the same "site" value, only one of them will appear in the output.

- | table site: Finally, the table command is used to format the output. It restricts the output to only show the values of the "site" field in tabular format. This means the results will display a single column showing unique "site" values from the filtered events.

Answer: www.berkbeer.com

## Question 2
Amber found the executive contact information and sent him an email.  What image file displayed the executive's contact information? 
```
index="botsv2" 10.0.2.101 sourcetype="stream:http" site="www.berkbeer.com"
| table uri_path
```
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c91daf35-d089-4bb3-82b7-3c59632513f8)

Answer: images/ceoberk.png

## Question 3
What is the CEO's name? Provide the first and last name.
Narrow down the search result by using the following search.
```
index="botsv2" sourcetype="stream:smtp" Amber berkbeer.com
```
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/3b5d92d1-998c-4c5a-8007-0d6713e365de)

Answer: Martin Berk

# Question 4
What is the CEO's email address?

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/0574586b-955f-4972-a44f-d978bbbfa288)

Answer: mberk@berkbeer.com

## Question 5
After the initial contact with the CEO, Amber contacted another employee at this competitor. What is that employee's email address?
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/e6b1ba0e-cecb-46f2-a804-2558d20bc6c5)


Answer: hbernhard@berkbeer.com 

# Question 6
What is the name of the file attachment that Amber sent to a contact at the competitor?


Answer: 
