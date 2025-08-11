# Pico-CTF
web exploitation CTFs

Today i will be tackling the easy cookie monster CTF. This is my first attempt at CTFs after a very long hiatus. 
Here is what you need to know

Difficulty
------------------------------
easy
------------------------------

Type 
------------------------
web exploitation
------------------------

Description
----------------------
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?
You can access the Cookie Monster 'here' and good luck
------------------------

The steps i took were the following 

1. i click on the hyperlink and it brings me to the following webpage
 <img width="1902" height="1033" alt="image" src="https://github.com/user-attachments/assets/cdf88cfe-60f8-4b89-9c5f-61d73e9ca1de" />
 i enter a random unsername and password to hopfully get more information within the errors
username = 'hello'
password = 1234


2. i get an access denied page, which i expected.
    <img width="1902" height="1033" alt="image" src="https://github.com/user-attachments/assets/5a34120f-1cd0-43eb-96c7-99dbad929d97" />
    of course there are no clues to be found within the denied page.
   After some time i choose to use a hint


   
3. The hint goes like this
   "Sometimes, the most important information is hidden in plain sight. Have you checked all parts of the webpage?"
   coupled with the fact that the CTF is named 'cookie' monster, i got the hint immediately.



4. I go to the cookies settings within my browser.
   <img width="1902" height="1033" alt="image" src="https://github.com/user-attachments/assets/2ba62e6e-424d-4a55-90f0-14ac5a93134e" />
   a few minutes of going through each section yielded little confidence in my clue finding.
   if the clues werent apparent immediately, taking a look at the source code definetely couldnt hurt.



   
5. to get access to the source code i typed "Ctrl + SHIFT + c",
   <img width="1902" height="1033" alt="image" src="https://github.com/user-attachments/assets/1e4b4025-f95b-4999-8c4f-d02bb1b29682" />

   As someone who doesnt exactly know what they are looking at, i try to find some relavent pieces of information. so anything that relates to cookies.
   After a few minutes of going through the source code i clicked on 'Application'
   and there is that relavent piece of information i am searching for
   <img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/62338c32-a839-4048-970a-187b5d58aef1" />

6. under storage and the cookie drop down is a single item. Within that item is the best clue i came across thus far. 'cookie value'. 
   <img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/97843b96-4634-4d75-bbe4-9bfcff7491f6" />

7. i see that it is a binary64 encoded string. a string that can be converted to regular string using bash.
   i turn on my VM, start kali linux and remote in using SSH powershell
   to convert/decrypt the string, the following command was needed. echo {input} | base64 -d
   <img width="1455" height="746" alt="image" src="https://github.com/user-attachments/assets/04a6a40e-9891-4518-97e8-2b5dd7bb3257" />
   After decrypting the base64 string i finally found the flag
   



  





