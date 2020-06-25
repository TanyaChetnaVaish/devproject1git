# TASK 1
# DEVOPS ASSEMBLY LINES
## TOPIC:Setup a Jenkins Production and testing and production pipeline using Docker
*Assumptions:Git is installed on Windows. The user must have GitHub profile. Docker and Jenkins must be installed ,here it is installed on RHEL8 running on VMWare. Webserver and docker server is configured. There is active internet connection.*

***Setting up GitHub and Git repositories and branches***

•	Create a folder (here on Desktop) -devproject1 and in it create a one.html file with data.
![](images/1.png)

•	Create a GitHub repository. And copy the following command onto your git and run it. It will create README file.
![](images/2.png)

![](images/3.png)

•	Make the dev1 branch

![](images/4.png)
To get into this branch use git branch dev1 command

![](images/5.png)
•	Now make changes to one.html file in this branch and add and commit it
![](images/6.png)

•	Now checkout into master branch and push the updates and file on GitHub. Here, we will notice neither of the branch merges or hampers the other, thereby maintaining isolation.
![](images/7.png)
![](images/8.png)

***Setting up Jenkins with useful Configurations required for automation:***
Login into Jenkins using the IP Address of RHEL8 and 8080 port.
![](images/9.png)
•	Now create job1 (Freestyle project) with following Configurations. Use the GitHub URL of the repository here and enable POLL SCM
![](images/10.png)
![](images/11.png)
Write the above command in Execute Shell of Build. Remember the path or file specified is the already existing folder in our RHEL8.

•	Create job2 with following configurations: Use the GitHub repository URL here, enable POLL SCM
![](images/12.png)
![](images/13.png)
Save the job2 now .

•	Create job3(Freestyle project) and copy the GitHub repository URL.
![](images/14.png)

Remember here the branch specification has to be done that is write the alternate created branch here (in this it’s dev1)
Write the following code on Execute shell. Remember to specify he right folder name from RHEL8 one that exists on the right specified path
![](images/15.png)
•	Now create the last job4 with following configurations:
![](images/16.png)
![](images/17.png)
Now in the post-build actions select Git publisher option and proceed with following configurations:
![](images/18.png)
![](images/19.png)
Now save job4 too with the above-mentioned configurations. That’s it!


Now you’re done with your automation.

You can access your one.html file and see the data merged. But job4 has to be built by us, thus insisting security as well from the users side.
![](images/20.png)


Further we can from RHEL8, both the files from devtest1 and devtest2 contain data from both master and dev1 branch in one
![](images/21.png)
![](images/22.png)
If we make changes in the file from dev branch then
![](images/23.png)

It will get updated after running job4
![](images/24.png)





I hope it helps. Thank-you!




