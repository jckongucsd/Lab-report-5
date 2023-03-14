# Lab Report 4

## 1. Setup Delete any existing forks of the repository you have on your account

  - Done

## 2. Setup Fork the repository

  - Done
<img width="1018" alt="Screen Shot 2023-02-26 at 10 47 19 PM" src="https://user-images.githubusercontent.com/122569310/221493494-d3ba2099-d2c0-4a1b-bfd6-af8e1702b1fd.png">

### Bash-script for step 2
`curl -X DELETE https://api.github.com/repos/your-username/repository-name/forks`

 Fork the repository
 
 replace "upstream-repo" with the name of the repository you want to fork
 
replace "your-username" with your actual Github username

`curl -u "your-username" -X POST https://api.github.com/repos/upstream-repo/forks`

## 3. The real deal Start the timer!

<img width="655" alt="Screen Shot 2023-02-26 at 10 42 13 PM" src="https://user-images.githubusercontent.com/122569310/221492712-572d82c3-b201-4daa-aa2b-2a4fa5f37016.png">

## 4. Log into ieng6
<img width="717" alt="Screen Shot 2023-02-26 at 10 46 14 PM" src="https://user-images.githubusercontent.com/122569310/221493316-1bef899c-8056-401a-8afc-279e532c338b.png">


## 5. Clone your fork of the repository from your Github account
<img width="652" alt="Screen Shot 2023-02-26 at 10 50 42 PM" src="https://user-images.githubusercontent.com/122569310/221494086-85d80ee0-ebb9-4fcf-a6d5-1c51e4bc6833.png">

### Bash-script for step 5

Clone your fork of the repository from your Github account

replace "your-username" with your actual Github username

`git clone https://github.com/your-username/repository-name.git`

Change directory to the cloned repository

`cd repository-name`

## 6. Run the tests, demonstrating that they fail

<img width="726" alt="Screen Shot 2023-02-26 at 11 05 33 PM" src="https://user-images.githubusercontent.com/122569310/221496592-0747ddea-7378-4cfb-b7ad-8c0d98ac24ef.png">

#!/bin/bash

Compile the code and run the JUnit tests

`javac -cp ../libs/junit-4.13.2.jar:../libs/hamcrest-2.2.jar:. TestListExamples.java
java -cp ../libs/junit-4.13.2.jar:../libs/hamcrest-2.2.jar:. org.junit.runner.JUnitCore TestListExamples`

If the tests passed, commit and push the changes to Github

`if [ $? -eq 0 ]
then
    git add .
    git commit -m "Fixed failing tests"
    git push origin master
else
    echo "Tests failed, please fix the code and try again."
fi`


## 7. Edit the code file to fix the failing test


Use Nano to edit the file:


<img width="431" alt="Screen Shot 2023-02-26 at 11 13 44 PM" src="https://user-images.githubusercontent.com/122569310/221498054-082e4115-6107-4ba9-8b35-7127d4cdb2ec.png">


 Here is the bashscript (pseudo-code) that you can use: 
 `

#!/bin/bash

#Delete any existing forks of the repository you have on your account
#replace "your-username" with your actual Github username
curl -X DELETE https://api.github.com/repos/your-username/repository-name/forks

#Fork the repository
#replace "upstream-repo" with the name of the repository you want to fork
#replace "your-username" with your actual Github username
curl -u "your-username" -X POST https://api.github.com/repos/upstream-repo/forks

#Clone your fork of the repository from your Github account
#replace "your-username" with your actual Github username
git clone https://github.com/your-username/repository-name.git

#Change directory to the cloned repository
cd repository-name

#Run the tests, demonstrating that they fail
#replace "test-command" with the actual command to run the tests
test-command

#Edit the code file to fix the failing test
#replace "file-to-edit" with the name of the file you want to edit
nano file-to-edit

#Run the tests, demonstrating that they now succeed
#!/bin/bash

#Compile the code and run the JUnit tests
javac -cp ../libs/junit-4.13.2.jar:../libs/hamcrest-2.2.jar:. TestListExamples.java
java -cp ../libs/junit-4.13.2.jar:../libs/hamcrest-2.2.jar:. org.junit.runner.JUnitCore TestListExamples

#If the tests passed, commit and push the changes to Github


if [ $? -eq 0 ]
then
    git add .
    git commit -m "Fixed failing tests"
    git push origin master
else
    echo "Tests failed, please fix the code and try again."
fi
`
