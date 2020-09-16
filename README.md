
Please download the artifact zip file [here](https://github.com/chelsb/gtutr/archive/artifact.zip)

gtutr is an interactive feedback system designed to assist students with writing grammars. The tool uses gamification to prevent students from being overloaded with too many failing test cases, and encourages independent problem solving by giving away as little information as possible. gtutr has access to test suites that can be used to evaluate student submissions, after which the tool attempts to identify and reduce the redundancy in the feedback that is given to the student. This helps direct students to possible error locations in their grammars. Students can prompt the system for more information if needed, and the tool can also highlight rules that are the most likely to contain faults. gtutr has been implemented for ANTLR, although the principles used can be generalised.

## Artifact Contents ##

After extracting the artifact zip **gtutr-artifact.zip**, the extracted folder contains the following files:

1. **gtutr.zip** : The file containing the artifact sources. This file contains the following subfolders:
    * **grammarProject** directory which contains the gtutr project sources
    *  **grammars** directory which contains example grammars for student submissions
    *   **testcases** directory which contains examples test suites for admin submissions
2. **gtutr.pdf** : The accepted version of the paper
4. **README.md** instructions for the artifact usage

## How To Run ##

There are two options for running gtutr.

1. To access the already hosted version, go to the URL:

    https://grammar-prod.zettel.co.za/

2. To run the project on your local machine, extract the project from the zip file
    ```
    gtutr.zip
    ```
    
    Inside the 'grammarProject' directory, run the following commands:
    ```
    chmod +x run.sh
    ./run.sh
    ```

    Then go to the following URL:
     ```
    http://localhost:8080
    ```
    
    Please note that you will need Maven and at least JDK 11 installed on your machine to run this version of the application.
    
## Admin Usage ##

To log into gtutr as an Admin, use any of the following preloaded credentials:

  ```
Username: AlanSLE       Password: AlanSLE
Username: CarolSLE      Password: CarolSLE
Username: BobSLE        Password: BobSLE
```

Upon logging in, you will see that there is already a grammar available called **testGrammar**

#### Viewing Grammar Submission Information ####

After logging in, you will see a list of available grammars. Clicking on a grammar with the Admin role will take you to the Admin dashboard, where you can view student submissions and test case information for that grammar. 

#### Adding A Grammar ####

After logging in, you will see a list of available grammars. Under that list, there is a button that says 'Add A Grammar'. Clicking on this button will take you to a new page where you can fill in the properties of the new grammar and provide test suites. Examples test suites can be found in the folder **testcases** that is included in the artifact submission. All the test suites are positive except for the test suite **neg**. 

#### Editing A Grammar  ####

After logging in, you will see a list of available grammars. Next to each grammar is two buttons. The left button containing a pen icon is used for editing an existing grammar. When clicked, a new page will open containing an existing grammar's information. The following can be edited:

1. The starting rule of the grammar
2. The penalty values of the grammar
3. Single test cases can be deleted
4. Whole test suites can be deleted or edited
5. New test suites can be added
6. Students can be remarked

#### Deleting A Grammar  ####

After logging in, you will see a list of available grammars. Next to each grammar is two buttons. The right button containing a red cross icon is used for deleting an existing grammar. This will delete the grammar and its associated test cases, as well as any user submissions to this grammar.

## Student Usage  ##
To log into gtutr as a Student, use any of the following preloaded credentials:

```
Username: MarvinSLE       Password: MarvinSLE
Username: JamesSLE        Password: JamesSLE
Username: JohnSLE         Password: JohnSLE
```

Upon logging in, you will see that there is already a grammar available called **testGrammar**. Clicking on this grammar with the Student role will take you to the student dashboard where you can submit. 

#### Submitting A Grammar ####

In the artifact submission is the folder **grammars**. Inside this folder are 3 grammar files that can be uploaded to gtutr to test the student submissions system.

1. **test_faulty_1.g4** is a grammar containing multiple faults
2. **test_faulty_2.g4** is a grammar containing fewer faults than **test_faulty_1**
3. **test_faulty_3.g4** is a grammar that contains no faults

After logging in as a student, you will be redirected to the student dashboard. you can click on the 'Add a new submission' button which will bring up a new dialog from where you can select one of the previously mentioned grammar files. Once submitted, gtutr will start marking.

#### Viewing Results #### 

In the student dashboard there are tabs in the upper right corner that say 'Submissions', 'Results' and 'Grammars'. Clicking on the 'Results' tab will display the results for your grammar submissions. These results are given in the form of a table that has the following format:

| testcases | submission1 | submission2 | submission3 |
|-----------|-------------|-------------|-------------|
| testcase1 | pass        | fail        | pass        |
| testcase2 | pass        | pass        | fail        |
| testcase3 | fail        | fail        | pass        |

Test cases will be displayed in their classes, and there are options to view more test cases of each class or a new class altogether. Most of the interactions have tooltips to explain what they mean in case of confusion.

#### Viewing Faulty Rules #### 

In the student dashboard there are tabs in the upper right corner that say 'Submissions', 'Results' and 'Grammars'. Clicking on the 'Grammars' tab will display your grammar's contents in the form of rules and their productions. If you want to view the most suspicious rules in your grammar, you can click on the 'Find faulty rule' button. Clicked once, this button will display the top 5 suspicious rules in your grammar. With every successive click it will start revealing the order of their suspiciousness, starting with the least suspicious shown first.
