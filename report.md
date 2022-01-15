# Remote Access

This blog post will be a tutorial for incoming CSE-15L students regarding remote access through Visual Studio Code. 

1. Step #1: **Installing VScode**

Go on the visual studio code website and download it for your appropriate operating system. Once downloaded, it should look something like this:

<img width="356" alt="Screen Shot 2022-01-14 at 7 15 07 PM" src="https://user-images.githubusercontent.com/97698918/149607977-8c6ff7c8-3740-4ee9-b8f9-fef48f6e9aeb.png">

2. Step #2: **Remotely Connecting**

In order to remotely connect, you will first have to go to https://sdacs.ucsd.edu/~icc/index.php in order to look up your username for the respective
and change your password. Once that is done, you will go on VS code, open a new terminal and paste "$ ssh cs15lwi22zz@ieng6.ucsd.edu" where
the "cs15lwi22zz" will be your specific username. After that you will have to type in your password in order to connect to the remote server.
Once that is done, it should look something like this:

<img width="398" alt="Screen Shot 2022-01-14 at 7 24 16 PM" src="https://user-images.githubusercontent.com/97698918/149607982-7a757df7-eaa8-4fd1-9727-f0fa228a5617.png">

3. Step #3: **Trying Some Commands**

Next step is to try some commands such as "ls -a", "-a", "ls", "ls -i" and see what these commands do. The following is what the two commands ("ls -i" and "ls") that I used give:

<img width="623" alt="Screen Shot 2022-01-14 at 7 30 45 PM" src="https://user-images.githubusercontent.com/97698918/149607992-357c88e1-1b17-4301-99b0-a162e39f5f7f.png">

4. Step #4: **Moving Files with scp**

For this step you will have to create a file on your computer called "WhereAmI.java" with some contents. After that, open your terminal and run the following:
"scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/" This will prompt you for your password which you should input. After that, log into ieng6 with ssh again, and use ls and you will see the files in the home directory. In this step I personally had an issue since my password was being denied which is why this is what it looked like for me:

<img width="625" alt="Screen Shot 2022-01-14 at 7 38 46 PM" src="https://user-images.githubusercontent.com/97698918/149608002-07b62211-2d6b-44a4-ba20-cd6211cdcfe3.png">

5. Step #5: **Setting an SSH Key**

The point of this key is to give us the ability to login without the tedious requirement of typing our password each time. You should input "ssh-keygen" in the terminal and receive a series of questions which you will type answers too. Once that is done you will have 2 unique keys: a public and private key. Copy the public key in the ssh directory by using scp. Once that is finished, we are able to login without our password. 

<img width="626" alt="Screen Shot 2022-01-14 at 7 44 06 PM" src="https://user-images.githubusercontent.com/97698918/149608003-97c3e74b-4e12-4743-9083-0edc1e6d05dc.png">

6. Step #6: **Optimizing Remote Running**

Now we will optimize this process for our personal convenience. I personally did this by the command scp WhereAmI.java cs15lwi22aqi@ieng6.ucsd.edu; ssh cs15lwi22aqi@ieng6.ucsd.edu "javac WhereAmI.java; java WhereAmI". For this step my password was being denied again which is why there is no screenshot. 
