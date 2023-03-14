# Lab Report 5

Benefits of bashscript in Lab Report 4:

In the specific instance of the tasks provided, writing a Bash script would have allowed for a faster and more efficient completion of the tasks. The tasks involved multiple steps, including deleting existing forks, forking a repository, logging into ieng6, cloning a forked repository, running tests, editing code, and committing and pushing changes to Github. Writing a Bash script that automated these steps would have saved time and minimized errors. For instance, the script could have included commands to delete existing forks, fork the repository, clone the forked repository, and run the tests. Additionally, the script could have used conditionals to check whether the tests passed or failed and to perform the appropriate action, such as editing code and committing and pushing changes if the tests failed. By using a Bash script, the entire process could have been completed quickly and without the need for manual intervention.






### 2. Setup Fork the repository

  - Done


## Bash-script for step 2
`curl -X DELETE https://api.github.com/repos/your-username/repository-name/forks`

 Fork the repository
 
 replace "upstream-repo" with the name of the repository you want to fork
 
replace "your-username" with your actual Github username

`curl -u "your-username" -X POST https://api.github.com/repos/upstream-repo/forks`

### 3. The real deal Start the timer!

### 4. Log into ieng6

### 5. Clone your fork of the repository from your Github account

## Bash-script for step 5

Clone your fork of the repository from your Github account

replace "your-username" with your actual Github username

`git clone https://github.com/your-username/repository-name.git`

Change directory to the cloned repository

`cd repository-name`

## 6. Run the tests, demonstrating that they fail

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


 # Here is the bashscript (pseudo-code) that you can use: 
 ```
#!/bin/bash

# Delete any existing forks of the repository you have on your account
# replace "your-username" with your actual Github username

curl -X DELETE https://api.github.com/repos/your-username/repository-name/forks

# Fork the repository
# replace "upstream-repo" with the name of the repository you want to fork
# replace "your-username" with your actual Github username

curl -u "your-username" -X POST https://api.github.com/repos/upstream-repo/forks

# Clone your fork of the repository from your Github account
# replace "your-username" with your actual Github username

git clone https://github.com/your-username/repository-name.git

# Change directory to the cloned repository

cd repository-name

# Compile the code and run the JUnit tests

javac -cp ../libs/junit-4.13.2.jar:../libs/hamcrest-2.2.jar:. TestListExamples.java
java -cp ../libs/junit-4.13.2.jar:../libs/hamcrest-2.2.jar:. org.junit.runner.JUnitCore TestListExamples

# If the tests passed, commit and push the changes to Github

if [ $? -eq 0 ]
then
    git add .
    git commit -m "Fixed failing tests"
    git push origin master
else
    echo "Tests failed, please fix the code and try again."
fi


# Commit and push the resulting change to your Github account
# replace "commit-message" with your commit message

git add .
git commit -m "commit-message"
git push origin master
```


