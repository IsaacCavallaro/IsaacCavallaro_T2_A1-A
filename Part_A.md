# Isaac Cavallaro T1_A2-A


# The ACME project


- *ACME Corporation is looking for devs with an understanding of Rails. The following set of questions relate to this RfQ-requirement.*

- *ACME Corporation is very big on project management, documentation and process. This will be a key metric in their decision to award the project. The following set of questions relate to this RfQ-requirement.*

- *Having suffered several cyber attacks in the past and resultant remedial audits ACME Corporation takes compliance, security and privacy very seriously. The following set of questions relate to this RfQ-requirement.*

- *ACME Corporation has specifically requested the app to be based on a relational database. The next set of questions relate to this RfQ-requirement.*

- *Companies (including ACME Corporation) value previous project experience and case studies. The following set of questions relate to this RfQ-requirement.*



# Q1: Describe the architecture of a typical Rails application

- Rails uses MVC as its architecture which stands for:
    - Model

    - View

    - Controller


![Alt](MVC1.png)



The MVC design pattern divides the responsibilities of an application which Rails follows by convention.

- The *Model* is the representation of the **data**.

- The *View* **displays** the content that is stored **in the model**.

- This is all done through the *Controller*.

## Overview

- First, the user **interacts** with the *View*.

- Some action initiated by the user will **prompt** the *Controller* to either:

    - **Get information** from the *Model* OR

    - **Update** the *Model*: If our user is interacting with our application in a way that **adds data** or **changes data** in our application.

- As the *Model* gets updated (as we update the data that is managed by our application) then the *Controller* will update the *View* to reflect those **changes in the data.**


## Minimum

 At a minimum, in order to get Rails to output "Hello", you need to create a:

- Route

- Controller
    - With an **action** and a *View*.

## Action

An **action** is a *Controller* **method** that respond to http **requests**.
 

## Requests

- When we type a URL into the browser or click on a link, a HTTP request is sent to the server. These requests are:

- GET -> Retrieve a resource (Read)

- POST -> Create a resource

- PUT/PATCH -> Update a resource

- DELETE -> Delete a resource

## Route

A **route** maps a **request** to a **controller action**/controller method. The controller action will handle the request and prepare the data to be displayed by the view. The view will then display this data in the desired format. 


- Routing is a **key part of all websites** with the content of a website being organised within serveral URLs.

- Different URLs and different HTTP methods require different routes. 

- Routing is needed whenever a **URL** is used in an application.

- Rails routes direct **particular requests** to the **particular controller** that can handle the **particular requests**.




## Params

- **Params** is a special object in which you can access everything in it using the hash notation.

        params[:id]


- Everytime there is a collon in the URL it means that this is a parameter or a param.

For example:

        get 'pets/:id to:'pets#show'

- Parameters are used when there is a list of items and we want to just access **one item.**


- The **id** represents a **key in our params.**

- The name of this key depends on what we have named it in our routes.rb folder.

- Therefore the id in our routes folder is very important because:
	
	- Whatever we have in our params depends on whatever name we use in our route.

- A URL parameter captures part of the request path and makes it available within the controller in the params object.


# MVC Breakdown



##  Model

- "A *Model* is a Ruby class that is used to represent data" (Ruby guides, 2021).

- The *Model* represents and manages the content of our application (the data in our application).

- The *Model* is the part of our design pattern that **connects** to the *database* and **retrieves information**, updates wherever we are storing that data for our application.

- The *Model* also is used to **define the data structure** for our data and the **relationships** between the different types of data in our application.

- Lastly, it’s the *Model* in this design pattern that’s **responsible for validating data**. So since the *Model* is the one that is aware of the data structure and what is expected for the data in our application, it’s the *Model* that we make responsible for **validating any use of that data**.

- All rails *Model* objects have an ID attribute. This ID attribute is used to look the *Model* objects up in the database. 

- Rails convention states the name of the ID is used for *Model* record IDs.

- Interestingly, most methods are not defined directly on an application's *Model* classes. Rather, they're inherited from a superclass. For example, the "all" class method is a common method that can be called on a *Model* class inherrited from ApplicationRecordClass.

- Rails will send the database a command in SQL when a *Model* method is called. For example, when the "all" method is called on a *Model* class, each record is converted into an instance of the *Model* class.

## To run the model generator from your terminal:

        bin/rails generate model ModelName attr1:type attr2:type


## For example:

        bin/rails generate model Pet name:string


## View

- The *View* is our user interface and it is responsible for what is actually appearing in the browser.

- The *View* is what the user is interacting with.

- This contains the **display of our application data** and also it exposes the way that the user can interact with our application.

- The *View* is responsible for displaying the content or the data of our application, which of course is received from the model.
So it displays the information to the user and also gives the user ways to interact with that data through our application logic.

### *The View usually though not always take the form of HTML templates with Ruby expressions embedded in them. Those expressions refer to data loaded from the model to populate an HTML page with data* - (Teamtreehouse, 2021).


ADD EXAMPLE


## Partials


- Partials refers to *Partial View*. 

- Partials allow you to take the HTML code that's identical between the templates and move it to a partial view. 

- This allows you to have less code to update when making any changes as any changes made to the partial will be visiable in all the views which use that partial. 

- Therefore partials are a good way to keep Rails projects DRY. 

## Controller

- You can think of the the *Controller* as the brain of this MVC trio or the orchestrator.

- The *View* is interacting with the *Controller* to get information from the *Model* and to update information that is managed by the *Model*.

- In this way, the user goes through the *Controller* to interact with our application.

- The *Controller* also manages the requests that are sent to our application.

- It controls the *Model* and the *View* to generate a response.

- For example: 

    - The *Controller* will recieve a request.

    - Then the *Controller* will load the request data via the *Model*

    - Then the *Controller* will insert that data into the *View.* 


## Generating a controller from the terminal:

        rails g controller (name of controller)

- All of the *Controllers* that we create will inherit from ApplicationController.

- ApplicationController inherites from the ActionContoller module and the Base class in that particular module.

## Render

- The **render** keyword is one way in which we can **send back** a response to our client.

- The **render** keyword is a **method** that can take a number of different arguments with a number of different notations. 


![Alt](MVC2.png)


# Q2: Identify a database management system (DBMS) commonly used in web applications (including Rails) and discuss the pros and cons of this database 

## PostgreSQL - Overview

- PostgreSQL is a database management system commonly used in web applications; including Rails. It is an open source object-relational database system which extends the SQL language. PostgreSQL has a positive reputation with regards to its:

    - reliability
    - data integrity
    - extensibility 
    - ability to support multiple languages (Python, Java, Perl. PHP, Ruby, C, C++ etc). 

- PostgreSQL is run by a community of developers who continually contribute to its source code; making it a very reliable DBMS system.

## PostgreSQL - Origins

- PostgreSQL dates back to 1986 where it originated as a part of the POSTGRES project at the University of California. In fact, the *Ingres* project came before POSTGRES, which is where the team leader of the *Ingres* project *Michael Stonebraker* left the university to create POSTGRES. 

## Pros of PostgreSQL

- **Data Types** 

    - "PostgreSQL has a rich set of native data types available to users. Users can add new types to PostgreSQL using the CREATE TYPE command." (postgresqldocs 2021)

- **Open Source**

    - This means that the code is available and may be redistributed and modified.

- **Free**

    - PostgreSQL is released under the OSI-approved PostgreSQL Licence which allows developers to use it for free. 

- **Supports JSON**

    - JSON is a lightweight format for storing and transporting data. 

- **Language Support**

    - Ability to support multiple languages (Python, Java, Perl. PHP, Ruby, C, C++ etc). 

- **Scalable** 

    - PostgreSQL is scalable both in the  quantity of data it can manage and the number of users it can accommodate. 


## Cons of PostgreSQL

- **Not available on all hosts by default**

    - PostgreSQL installation needs to be uniform across all supported operating systems.


- **Not owned by one organization**

    
- **Slower than MySQL** 

    - When comparing performance metrics, PostgreSQL is slower than MySQL. 

## SQL stands for Structured Query Language.

- There are many databases that support reading (querying) data from a database with SQL. 

    - MySQL
    - MS SQL
    - Oracle
    - SQLite
    - PostgreSQL




# Q3: Discuss the implementation of Agile project management methodology 


- The Agile Manifesto was written in 2001 by a group of 17 software developers who were looking to reduce time and resources when developing software. The Agile Manifesto encourages teams to consider how to break down silos that seperate people when working on a project. In this manner, the Agile Manifesto provides expectations for collaboration in addition to setting formal roles and responsibilities.
It emphasizes responding to change over strickly following a plan. Therefore, as priorities change, a team who implements the Agile Manifesto can continue to develop and deliver value. 


- The Agile project management methodology is a strategic approach to managing a project. Specifically, the Agile project management methodology breaks a project up into different phases and originally worked within four main values:

    1. Individuals and interactions over processes and tools

    2. Working software over comprehensive documentation

    3. Customer collaboration over contract negotiation

    4. Responding to change over following a plan

- Today (according to scrumalliance.org) these values or key principles are:

## 12 Agile principles.

1. Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.

2. Welcome changing requirements, even late in development. Agile processes harness change for the customer's competitive advantage.

3. Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.

4. Business people and developers must work together daily throughout the project.

5. Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.

6. The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.

7. Working software is the primary measure of progress.

8. Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.

9. Continuous attention to technical excellence and good design enhances agility.

10. Simplicity--the art of maximizing the amount of work not done--is essential.

11. The best architectures, requirements, and designs emerge from self-organizing teams.

12. At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly.

![Alt](agile1.png)


- With these key principles in mind, we can see that Agile uses an iterative and incremental approach to product development; allowing projects to be more flexible and adaptive to changes.
Furthermore, we can see that Agile focuses on critical documentation (such as product requirements) and considers lengthy reports as unnecessary. This however, does not suggests that Agile project management methodology allows developers an excuse to produce low quality products. Rather, Agile aims to provide a workable product after each iteration. 

## Implementating Agile

- Successfully incorporating Agile will require everyone (project team, customer, key stakeholders) to be on board before you begin your project. 

- Given the iterative and incremental nature of Agile, it is best to start with one small project when implementing Agile across a whole organization. 

- After gaining feedback, you can then use Agile on other projects.

- It is also important to keep your team engaged and motivated to have a successful Agile approach to your project. This requires open communication, collaboration and problem solving between all members of the team. 

- Sticking to a selected Agile framework (Daily scrums for example) is important for the success of your project. Although everyone is busy, committing to these are essential to the success of implementing Agile.

- When you are first implementing an Agile methodology, it is critical to follow a proven Agile project management process. In other words, it is important to stick to the rules and not to experiment with hybrid frameworks mid-sprint. Particularly while your team is learning the ropes. 


## Swarming 

- One process used in Agile project management is called “swarming” which is an approach used to optimize flow efficiency. In short, “swarming” requires a team member to pause and help other colleagues before working on the next task. This creates a collaborative environment focusing on optimising the overall process instead of focusing on individual improvements.  

## Scrum

- The term Scrum refers to a frameword used in agile project management that uses fixed-length iterations of work; referred to as sprints. Although scrums are generally used by software development teams, the scrum framework can be beneficial to any team working towards a common goal.


## Scrum roles: 

- There are two sets of roles in Agile scrum methodology.

    1. Core roles - referred to as "pigs"

    2. Ancillary roles - referred to as "chickens".


- The core roles can be broken down into three core roles:

    1. **Scrum master:**

        - Facilitaes the scrum development process.

        - Supervises and manages that the scrum rules are being enforced and applied as intended.

        - Responsibile for motivating and coaching the team.

        - Responsibile for helping the team meet their target.


    2. **Product owner:**

        - Represents stakeholders (typically customers).

        - Determins product expectations.

        - Records any changes to the product. 

        - Responsibile for administering a scrum backlog. 

        - Responsible for keeping a detailed and updated to-do list for the scrum project.

    3. **Scrum team:**

        - Members of a scrum team are collectively responsible for meeting each sprint's goals.

        - A scrum team has the skills required to produce deliverable products.




## The scrum board

- Used to visualize all the work in a given sprint.

- They are a key component for illustrating transparency within agile project management.


## Aigle tools:

### Trello board

- Trello is a simple tool to begin implementing Agile methodologies.

- Trello works like a traditional whiteboard but inclues the freedom and luxuries associated with digital and web technologies; it is free, simple to use and share with others. 

- Trello givess users and guests full visibility into project stages, roles, and deadlines.

- Trello can be used as a Scrum board or an Agile-based sprint board.

- In order to create an Agile-based sprint board, you will need:

    - Sprint backlog: 
    
        - Contains all the tasks that need to be completed within the current project.

    - Current sprint

        - Dedicated to the tasks you aim to accomplish.

    - To do

        - Contains actionable steps that are required in the current sprint.

    - In progress

        - Contains the tasks that are in progress and not finished.

    - Q & A

        - This is where tasks are place after a team member completes it. Then it can be reviewed by other team members before being adding to the done area. 

    - Done

        - Contains tasks that are completed.


- There are other ways of incorporating Agile based methodologies with trello but the above is just one example. 

- The image below illustrates an example/template of using a trello board as a *Scrum Project Management Board.*


![Alt](trello.png)

- Link to this template can be found [here:](https://trello.com/b/0xzkRjTH/scrum-project-management-board)


## Tips for excelling at Agile with Trello

1. Move the **Done list** to the far left side of the board


2. Minimise the amount of tasks in the **todo list**

3. Include an extra list for tasks in **pending status**









# Q4: Provide an overview and description of a standard source control workflow 

- Source control is the process of tracking and managing changes to code; allowing developers to work on the correct version of source code. Although source control and version control are often used interchangeably, they do slightly differ. 

- Specifically source control relates to source code while version control also includes large binary files and digital assets. In addition to source control and version control, there is also source control management (SCM). SCM relates to the tools that help developes track the changes of the source code with a complete history of these changes (Git for example).

## Workflow:

## Start a new project:

		git init

- Executing this command in the root folder of a project will create a new and empty repository.

## Work on files 

- Work on your files within IDE or editor. 

## Overview Status

		git status

- Running the git status command will display what has happened since your last commit (were any new files created or deleted etc).

## Add files to the staging area

		git add <filename>

- It's important to note that while you may have changed a file, it does not mean it is ready to be commited. This is why we have to execute the git add command. This explicitly adds whatever files you want to the "staging area".


## Commit all staged changes

		
        git commit -m “message”

- Executing a git commit command will wrap all the changes made from the previously staged files and record these changes in the Git database (Github for example).

## Check status

		git status


- By running the git status command after a commit, you can see which changes have been recorded to the Git database and which are only changed on your local machine.

## Inspect git history

		git log


- Running git log will list all the commits made in chronological order; allowing for an easy illustration of what changes where made over the course of the project. 

## Push changes to remote repository

        git push



![Alt](git1.png)





## Branching

- Branching refers to an independent line of development. 

- They server as an abstraction for the edit/stage/commit process. 

- In other words, branching can be viewd as a way to request a brand new:
    -  working directory

    - staging area

    - project history

- In this way, new commits are recorded in the histroy of the current branch. 

- This will result in a fork in the history of the project.




        git branch


- The git branch command lets you create, list, rename, and delete branches. 

- "It doesn’t let you switch between branches or put a forked history back together again. For this reason, git branch is tightly integrated with the git checkout and git merge commands." (https://www.atlassian.com/git/tutorials/using-branches)


"Branches are just pointers to commits. When you create a branch, all Git needs to do is create a new pointer, it doesn’t change the repository in any other way." (https://www.atlassian.com/git/tutorials/using-branches)


## Checkout 

"Git checkout works hand-in-hand with git branch. The git branch command can be used to create a new branch. When you want to start a new feature, you create a new branch off main using git branch new_branch. Once created you can then use git checkout new_branch to switch to that branch. Additionally, The git checkout command accepts a -b argument that acts as a convenience method which will create the new branch and immediately switch to it. You can work on multiple features in a single repository by switching between them with git checkout." (https://www.atlassian.com/git/tutorials/using-branches)

        git checkout -b ＜new-branch＞


"When collaborating with a team it is common to utilize remote repositories. These repositories may be hosted and shared or they may be another colleague's local copy. Each remote repository will contain its own set of branches. In order to checkout a remote branch you have to first fetch the contents of the branch." (https://www.atlassian.com/git/tutorials/using-branches)


        git fetch --all



In modern versions of Git, you can then checkout the remote branch like a local branch. (https://www.atlassian.com/git/tutorials/using-branches)


        git checkout ＜remotebranch＞



# Q5: Provide an overview and description of a standard software testing process

The primary goal of testing is to make sure our program is functional.

- Functional

    - Does it meet the requirements that have been set out by this application?


- Usability

    - How easy is it for our user to use the application?
Are they able to use all the functions that they need to use and is it intuitive?

- Reliable

    - What happens if we are given unexpected input or invalid input? 

- Scalable

    - As we put more load on the application, more users or more objects in the data base, does our application still perform they want hat we expect to?

- Secure

    - We want to make sure that if we are storing any data about our users that we are protecting that data.


## Unit testing

- Unit testing is perhaps one of the most important types of testing.
It is done from the very start of the development process and often accompanies Test driven development (TDD). A lot of times the majority of tests in a particular project are unit tests.
Unit tests are referred to as automated tests; meaning developers write tests that automatically test the code without having to manually test that things are working. Specifically, unit tests are used to test things at the level of a unit or a single functional (The smallest parts of our program that do something). In other words, unit tests help developers make sure that given particular input will always get the expected output.

- Some example of testing frameworks that we can use for unit testing are:

  - Rspec, MiniTest or TestUnit (Ruby)
  - Mocha or Jest (JavaScript)

- In addition to unit testing there are also:
 
  - End to end testing
  - Acceptance testing
  - Non functional testing
  - Usability testing
  - Manual testing
  - Automated testing


ADD RSPEC CODE!



# Q6: Discuss and analyse requirements related to information system security and how they relate to the project

- *Having suffered several cyber attacks in the past and resultant remedial audits ACME Corporation takes compliance, security and privacy very seriously. The following set of questions relate to this RfQ-requirement.*


- In the modern digital world, companies are recieving security threats on a constant basis. Therefore, it is critical for organizations to understand security requirements. Understanding the information security requirments is considered "the all-important first step to developing a robust information security strategy" (ProServeIT, 2020). 

https://www.proserveit.com/blog/information-security-requirements


There are 3 types of security obligations organizations need to consider when dealing with information security requirements.

## 1. Business Obligations

"Business Obligations: These are the security commitments you have. For example, you have a responsibility to ensure that information in the business – customer data, employee files, etc. – is kept secure and is available when needed."

## 2. Regulatory Obligations: 

"These are legal, compliance, or contractual obligations that your security team must fulfil. For example, organizations in the healthcare industry must be HIPAA compliant."

## 3. Customer Obligations: 

"These are the security commitments that the customer expects your organization to keep. For example, if you were a manufacturing company that provided custom parts, those customers may require all of their proprietary blueprint files to be encrypted."




## Types of attacks:

### Phishing

- "This attack collects sensitive information like login credentials and credit card information by sending an email supposedly from a legitimate business that has a link to a legitimate-looking (but totally fraudulent) website. This is one of the most prevalent types of attack that a small business will face. (Source: Ponemon Institute)."

https://www.proserveit.com/blog/information-security-best-practices


### Ransomware

- "One of the fastest growing types of security breaches, ransomware is a type of malware that will infect the target’s machine and either lock the victim out of their machine, encrypt the victim’s files, or threaten to publish the victim’s confidential information if a ransom is not paid. Remember WannaCry? That was a ransomware attack."

https://www.proserveit.com/blog/information-security-best-practices

### Inside attacks

- "These attacks happen when someone with administrative privileges purposely misuses his or her credentials and hacks into your confidential company information."

https://www.proserveit.com/blog/information-security-best-practices


### Malware

- "Short for “malicious software”, this attack covers any program that is introduced into the target’s computer with the intent to either gain unauthorized access or cause damage."

https://www.proserveit.com/blog/information-security-best-practices

### Password attacks

- "Brute-force attacks (keep guessing at a password until they get in), dictionary attacks (use a program to try combinations of dictionary words), or keylogging attacks (track the target’s keystrokes) are three types of password attacks".

https://www.proserveit.com/blog/information-security-best-practices


# Q7: Discuss common methods of protecting information and data and how you would apply the to the project

https://looker.com/definitions/data-security

## Authentication 

"Authentication, along with authorization, is one of the recommended ways to boost data security and protect against data breaches. Authentication technology verifies if a user’s credentials match those stored in your database. Today’s standard authentication processes include using a combination of ways to identify an authorized user, such as passwords, PINS, security tokens, a swipe card, or biometrics."

"Authentication is made easier through single sign-on technology, which, with one security token, allows an authenticated user access to multiple systems, platforms, and applications. Authorization technology determines what an authenticated user are allowed to do or see on your website or server."

https://looker.com/definitions/data-security

## Access control

"Authentication and authorization happen through the process called access control. Access control systems can include:"

"Discretionary access control (the least restrictive), which allows access to resources based on the identity of users or groups,
Role-based access control, which assigns access based on organizational role and allows users access only to specific information,
And mandatory access control, which allows a system administrator to strictly control access to all information."

https://looker.com/definitions/data-security

## Backups & recovery

"Prioritizing data security also requires a plan for how to access your company’s and client’s data in the event of system failure, disaster, data corruption, or breach. Doing regular data backups is an important activity to help with that access."

"A data backup entails making a copy of your data and storing it on a separate system or medium such as a tape, disk, or in the cloud. You can then recover lost data by using your backup."

## Encryption

"Data encryption software effectively enhances data security by using an algorithm (called a cipher) and an encryption key to turn normal text into encrypted ciphertext. To an unauthorized person, the cipher data will be unreadable."

"That data can then be decrypted only by a user with an authorized key. Encryption is used to protect the data that you store (called data at rest) and data exchanged between databases, mobile devices, and the cloud (called data in transit). Your encryption keys must be securely managed, including protecting your critical management systems, managing a secure, off-site encryption backup, and restricting access."

## Data masking

"Data masking software hides data by obscuring letters and numbers with proxy characters. The data is still there, behind the masking. The software changes the data back to its original form only when an authorized user receives that data.

## Tokenization

"Tokenization substitutes sensitive data with random characters that are not algorithmically reversible. The relationship between the data and its token values is stored in a protected database lookup table, rather than being generated by and decrypted by a mathematical algorithm (as in the case of encryption). The token representing the real data is used across different systems as a replacement, while the actual data is stored on a separate, secure platform."

## Deletions & erasure

"When electronic data is no longer needed and must be permanently cleared from the system, erasure can overwrite that data so that it is irretrievable. Erasure is different from deletion, which is a process that simply hides data in such a way that makes it easy to retrieve."



# Q8: Research what your legal obligations are in relation to handling user data and how they can be met for the project 

In order to outline the legal obligations of handling user data and there relationship to ACME Corporation, I have sourced an Australian Government document titled *Rights, responsibilities and roles of data users*. The document clearly outlines appropriate definitions and as suggested by the title, the legal obligations and responsibilities of data users. I consider the overview of the document below to be of practical use for ACME Corporation. 


- Link to the full document can be viewed [here](https://toolkit.data.gov.au/files/Rights,_responsibilities_and_roles_of_data_users_Dec2013.pdf).

- Additionally, I have sourced *The Privacy Act 1988* 
which can be viewed [here]()

### Data Users:

- The term data user refers to a person involved in accessing and investigating integrated datasets. Specifically for statistical and research purposes. This includes academics who work in research institutions and employees undertaking research in Commonwealth and state/territory agencies. The term data user in plural may also refer to multiple data users working as part of a consortium, alliance or collaborative network. 

- Given ACME Corporation aims to be competitive and relevant, it is encouraged ACME Corporation should embrace the benefits of big data. In this manner, it is fair to suggest ACME Corporation will be involved in accessing and possibly investigating integrated datasets.

- Therefore, it is recommended ACME Corporation seriously consider the following outline. 


### Rights and Responsibilities 

- There are a number of rights and responsibilities associated with accessing and using integrated datasets which ACME Corporation should familiarise themselves with. These rights and responsibilities relate to integrated datasets that involve the use of at least one Commonwealth dataset. Additionally, these rights and responsibilities 
exist within the governance and institutional framework which is designed to help minimise risks associated with managing data.


- ACME will be required to consult with data custodians and the integrating authority if they are to make any material changes or updates to a data integration project. This will be required 
regardless of whether any such changes originate from data custodians or integrating authorities. Additionally, the consultative process will be led by a data custodian(s) who are required to approve theACME project before proceeding to an integrating authority. 


- According to the sourced document - *Rights, responsibilities and roles of data users*, this consultation is to be done before data users start examining integrated datasets; aiming to raise issues of integrating authorities (technical feasibility of ACME Corporation) or any limitations of the data use. 



 


- "are entitled to receive appropriate training covering high level statistical integration principles, governance and institutional arrangements, data protocols (e.g., ethical approval processes in the case of human-based health research), legislative frameworks and security requirements. This training will be facilitated by integrating authorities. Course material will also be determined by integrating authorities, with possible input, advice and assistance provided by data custodians. Data users can also expect to access a range of self-help tools to enhance their understanding of the Commonwealth arrangements."

- "must be aware of, and understand, sanctions which apply for attempts to identify (or re-identify) individuals or organisations; disseminating outputs that enable the identification of individuals or organisations; or the misuse of data."

- "has the right to be informed by data custodians of the project status (i.e. approval or disapproval). Data custodians have the right to approve or disapprove a project proposal, in whole or in part. This decision could take into consideration the technical feasibility assessment made by integrating authorities. Data custodians may also need to prioritise and schedule data extraction work associated with project proposals, taking into account the range of data extraction requests that may be outstanding at the time."

- "have a responsibility to pay cost recovery payments to data custodians, where applicable."

- "are responsible for ensuring that datasets are used for the approved purposes only. This is facilitated by practices which help avoid the misinterpretation of data. Examples include the testing of assumptions made in respect of the data by researchers and the supply of appropriate metadata by data custodians."




![Alt](dataintegration.png)




# Q9: Describe the structural aspects of the relational database model. Your description should include information about the structure in which data is stored and how relations are represented in that structure.

The structure of a relational database is considered to be explicit and requires careful alteration once the database is being used. In this manner, using a relational database is not recommended when the structure of the data is changing or may be different within certain instances of the data.

## Set 

- A set refers to the grouping of **similar things.**

- Sets are foundational in performing useful queries with relational databases. 

- Sets can be illustrated using a *Venn Diagram*.

- Example set: **Things you wear.**

  - Shirts
  - Shoes
  - Socks 
  - Coats

- Additionally, you can have a specific set for Shirts:

  - T-shirt
  - Dress-shirt
  - Sweaters 

- Therefore, items like shoes and socks will appear in the first set but are not in the second set given socks and shoes are approprite for things you wear but not for specific shirts. 

## Dataset 

- Collection of rows with the same column definitions.


## Keys 


### Primary Keys

A primary key is an **attribute** or field that uniquely identifies **every record** in a certain table. Given this can be accomplished with a **single attribute**, you will only have ONE primary key per entity.

### Primary Key Rules:

1. Has to be unique

    - A primary key will indentify only ONE record in a table. 

2. Never Changing

3. Never-Null 

    - Simply put, the value can NOT be left **blank.** 

### Foreign keys

- Unlike a primary key, foreign keys do NOT have to be unique and CAN be **repeated in a table**. Another differnce between primary and foreign keys is that there can be **multiple** foreign keys in a **single entity.** 

- Foreign keys are attributes from one table referenced in a related table. 

- In short, foreign keys create relationships between tables. 

### Composit Primary keys

1. Uses the **fewest number** of **attributes** possible to generate a **composite primary key.**

2. **Does not** use attributes that will **change.** 

### Unique keys

- A specifically configured column so that no value can be repeated within it.

- Multiple unique keys can exist per table.

- "For example, a unique email address column could also be in the same table as a unique Social Security number column."


"Also, values in unique columns can be changed to new values as long as they don't conflict with any existing values in that column."

## Relational Database

 "In the real world, databases are very large, having millions of rows in a single table.These commonly used databases are called relational databases."  (Teamtreehouse)

"This term came about from structuring databases in a way that tables are linked to each other by shared attributes. These links are the relationships between tables. Remember that relational databases are called relational because the tables are connected by common attributes."  (Teamtreehouse)


"Relational databases allow schema designers to enforce good data principles which lead to better data quality and better reports. This is what relational databases do, they organize data into related tables that give context and meaning to the words and numbers contained within." (Teamtreehouse)


"There are many reasons why relational databases became the standard for application data storage. A few of which are eliminating redundant data reduces storage requirements on disk."

 (Teamtreehouse)

- Relational databases organise data in tables with **rows** and **columns.**

- The **table** represents a **relation** because it **defines** the ways that the **data relates as information.**

- The **columns** indicate **attributes** (also known as domains or types) for the data.

- The **rows** (also called tuples) represent individual **records** in the table.

- One example of a **Relational Database** is a **spreadsheet.**

- Each **entity** (or object type) would be defined in its own **table.**


## Entity

- An **entity** represents a person, place or thing that you want to **track in your database.** 

- Each **occurance of an entity** is referred to as an **entity instance** which will become a **record/row in the table.** 


## Store example: Entities & Attributes

    - Items 

        - Name
        - Description
        - Price
    
    - Customers

        - Name
        - Email 
        - Address

    - Orders

        - Date
        - Customer
        - Items with quantities
        - Total price 


In the above example the entities are:

- Item, Customers and Orders.

- Underneath each Item follows their respective attributes (Name, Description etc).

## Store example: Relationships

The **first step** to defining the relationships that we have to include in the structure of our table is: *We think about our entities and we create sentences that describe the way each entity relates to the other.*

- How is a customer associated with an order?

    - A customer places an order.

- How is an item associated with an order?

    - An order contains at least one item.


- When talking about relationships, we need to define the **cardinality** and **ordinality** of the relationship. 

## Cardinality

- Cardinality expresses the **maximum** number of one entity with which an entity relates.

    - An order is made by **one customer** (one).

        - For example: If we have an order that has been placed, it will be placed by a single customer. NOT multiple customers, NOT no customers but one single customer. 

    - An order can contain many items (many).

        - For example: An order can contain many items. It will contain one item, but it could potentially contain many items. 

## Ordinality

- Ordinality expresses the **minimum** number of one entity with which an entity relates. 

    - A customer can have 0 orders (optional relation).

        - For example: It's possible a customer may not place an order. 

    - An order contains at least one item (mandatory relation).

        - For example: An order must contain at least one item. Otherwise it is not considered a valid order. 

- These expressions of the numbers that relate to each other are realy important as it effects the way that we define our database model. 


## One to one relationship (Store example)

- If we separate addresses from custromers into a seperate addresses table, the relationship between custromer and address would be: 
    - One to One relationship.

- A **customer** has **one address.**

- An **address** belongs to **one customer.**

## One to many relationship (Store example)

- The relationship between customer and order is a one to many relationship. It is mandatory that an order has at least 1 customer and it is optional for a customer to make an order. 

- An order has exactly 1 customer.

- A customer can have 0 or more orders.

## Many to many relationship (Store example)

- The relationship between order and items is a many to many relationship. 

- An order can have many items (at least one item).

- An item can belong to many orders (or no orders at all).

- A many to many relationship is often modelled with a joining tables (in relational databases).

## Relationship symbols

![Alt](relationshipsymbols1.png)

## One

One relationship (Customers & Addresses): 

- Where a customer has one address and an address has one customer.

- We use a little vertial line (at the end of the line connecting the two entities). 

![Alt](one.png)

- If we want to indicate that this relationship is a required relationship: 

    - Meaning an addresss MUST have one customer.

    - And a customer MUST have one address. 

- We use a double vertical line.

![Alt](one1.png)

- In other words, the second vertical line indicates that the relaionship is required. 

## Many

Many relationship (Customers & Orders):

- Where a customer can have many orders. 

- We use the crows foot to indicate a many relationship. 

![Alt](many.png)

- If look at the image below:

![Alt](many1.png)

- It reads (right to left):

    - A Customer can have 0 or more orders. 

- It reads (left to right):

    - An order has exactly one customer. 

## Optional

- The image below shows how we illustrate an optional relationship: 

![Alt](optional.png)

- The first symbols reads as optinal 0 to 1 and the second reads optional 0 to many.

## Normalisation

Nornalisation is the process of identifying and eliminating elements in a database design that if left in place, would make the database perform poorly or have inconsistent data.



## 1NF

The first normal form (1FN) says the table MUST meet the constraints of a Relational Database:

- The column names need to be unique.

- Order of records does not matter.

- Records in one column must be of the same type.

- Must have atomic values in columns (single values).

## 2NF

The second normal form (1FN) says the table MUST meet the constraints of a Relational Database:

- It should be in the First Normal form.

- It should not have Partial Dependency.

## 3NF

The third normal form (1FN) says the table MUST meet the constraints of a Relational Database:

- It is in the Second Normal form.

- And, it doesn't have Transitive Dependency.

## Designing a relational database model

- Before implementation, it is important to design your relational database using a physical ERD. 

- A physical ERD (entity relaionship diagram) represents the way data is physically modelled in the database. 

- A physical ERD represents the schemas (defined structure) for the database tables. 

- We can then use our ERD to inform how we should create our database tables.

![Alt](ERDexample.png)

# Q10: Describe the integrity aspects of the relational database model. Your description should include information about the types of data integrity and how they can be enforced in a relational database.


## Entity integrity

- Entity integrity means **no two rows** can be the **same** in a **table.** This can be achieved by defining a **primary key** in which the primary key field contains a **unique id**. Therefore, **no two rows** can have the same **unique id.**  With this in mind, if you define a primary key for each entity, then they follow the **entity integrity rule.** The uniqueness property of entity integrity ensures that the **primary key of each row is uniquely identified**. In other words, there are NO duplicates. Additionally, the second property ensures that the primary key has a meaning/value. The entity integrity system does not allow the operations to produce an invalid primary key. If an operation creates a duplicate primary key or one which contains null it is rejected. 

## Referential integrity

- Referential integrity refers to **relationships.** For example, when two or more tables are related, it is important to **match the values** of the **foreign key** with the **primary key at all times.** If a situation arises where a foreign key has no matching primary key value in a primary table, we will get an **orphaned record.**
Referential integrity **prevents** users from adding records to a table when there is **no associated record** in the primary table. It also prevents users from **changing values** in a primary table and prevents users from **deleting records** from a primary table (when there are matching related records). 

There are three common techniques to **handle** and **enforce** referential integrity violation.

- **Reject Technique**

    -  Rolls back the statement that fired the rule with a raise error statement. This error informs the application that the some rule was violated with regards to some specified condition or constraint. 

- **Nullify Technique**

    - Another course of action to respond to a violation in a referential integrity constraint when a foreign key does not have a matching primary key is to use the Nullify technique. Nullifying refers to a situation where the columns in the records in violation of the constrainare made null. 


- **Cascade Technique**

    - Cascading is when the original update applies to other records in violation of the constraint. Specifically, when the statement that violates the constraint is an insert or update. In this case, cascading will insert the offending forein key into the primary key column. Also when the violation is a delete (deleting the primary key and all forein keys that match the primary key).


## Domain integrity

 - Domain integrity refers to the validity of the entries for any given column of a table. Therefore, selecting the appropriate data type for a given column is paramount to maintaining domain integrity. Other ways to maintaining domain integrity are:

    - Allocating appropriate constraints and rules.

These constraints and rules are used to define the data format and/or restrict the range of possible values. 



# Q11: Describe the manipulative aspects of the relational database model. Your description should include information about the ways in which data is manipulated (added, removed, changed, and retrieved) in a relational database.


*The manipulative features of relational databases provide the ways we access and modify the data*

## Manipulating Data

- Insert Data into tables.

- Query data with SELECT.

- DELETE data from tables.

## Inserting Data

- Specify column names in any order and match order of values.

- Error if required (not null, primary key) column values are missing.

        INSERT INTO <table_name> (COLUMNS) VALUES

- We give the list of columns for which we will insert data in the order of which we will specify the values.


## Retrieving Data: Select

Returns a relation containing all tuples (records) that meet some condition. In PostgreSQL, we use the SELECT statement for this, with optional clauses to limit the results.

- Retrieving data from a specific table can be done by using the SELECT statement. 


        SELECT <list_of_columns> FROM <list_of_table_names> WHERE <conditions> ;



- We can divide the SELECT statement into three main sections:


1. List of columns:

        <list_of_columns>


     - This specifies the column names that need to be retrieved from a particular table/tables. 

2. List of table names:


        <list_of_table_names>

    - the tables from which to retrieve the data.

3. Conditions:

        <conditions>

    - Parameters used for including any further restrictions on the data.

## Examples:

    SELECT * from items WHERE name = ‘beef’;

    SELECT * from items WHERE price < 10.00 LIMIT 10;

    SELECT name from items;

    SELECT quantity, item from orders;

# Q12: Conduct research into a marketplace website (app) and answer the following parts: 

## Airbnb

## A: List and describe the software used by the app.

- 

## B: Describe the hardware used to host the app.



## C: Describe the interaction of technologies within the app



## D: Describe the way data is structured within the app



## E: Identify entities which must be tracked by the app



## F: Identify the relationships and associations between the entities you have identified in part (e)




## ERD 


# References:

https://www.proserveit.com/blog/information-security-requirements#eleven
https://www.atlassian.com/git/tutorials/using-branches
https://blog.hubstaff.com/agile-trello/

https://www.businessnewsdaily.com/4987-what-is-agile-scrum-methodology.html


https://www.atlassian.com/agile/project-management

https://stackshare.io/airbnb/airbnb

https://medium.com/@poojaseenu1999/the-technology-stack-behind-airbnb-6b23fe425612








