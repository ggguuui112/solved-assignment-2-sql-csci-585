Download Link: https://assignmentchef.com/product/solved-assignment-2-sql-csci-585
<br>
In this assignment, we will use Google Cloud SQL to work with SQL queries. This will help us learn how to use cloud services as well as run code on SQL. The document is divided into several parts. Parts 1 through 3 go through the basics of setting up the platform. Part 4 is the assignment. Good luck.




Contents

<a href="#_Toc11635">Part I: Setting up Google Cloud Platform……………………………………………………………………………. 2  </a>

<a href="#_Toc11636">Part 2: Setting up Cloud SQL……………………………………………………………………………………………. 3  </a>

<a href="#_Toc11637">Create a Cloud SQL Instance………………………………………………………………………………………….. 4  </a>

<a href="#_Toc11638">Part 3: Working with SQL (Optional)…………………………………………………………………………………. 7  </a>

<a href="#_Toc11639">Part 4: Programming Assignment…………………………………………………………………………………….. 8  </a>

<a href="#_Toc11640">Submission Guidelines……………………………………………………………………………………………….. 11  </a>










<h1><a name="_Toc11635"></a>Part I: Setting up Google Cloud Platform</h1>




Google Cloud Platform helps you to run your work on Google Compute Engine (GCE) and to use its core infrastructure, data analytics and machine learning.

To set up GCP, follow the steps below.

<ol>

 <li>Go to <a href="https://console.cloud.google.com/freetrial">https://console.cloud.google.com/freetria</a><a href="https://console.cloud.google.com/freetrial">l</a> <a href="https://console.cloud.google.com/freetrial">u</a>sing your personal Google account. (Do not use the USC account.)</li>

</ol>

This gives you a $300 credit to spend on the GCP for the next 12 months. Agree to the

acceptances and click on ‘Agree and Continue’, as in Figure 1.1.

<ol start="2">

 <li>In the Customer info screen, select Account Type: Individual and fill in all the details. (You will be required to enter credit/debit card details, but you will not be charged as long as you <sub>don’t </sub>exceed the $300, which is sufficient for all the database assignments.)</li>

 <li>Click on ‘Start my Free Trial’ and wait for Google Cloud Platform to set up. Congratulations! You just finished the first part of the assignment.</li>

</ol>










Figure 1.1: Google Cloud Platform Sign-up page







Notes on Google Cloud Pricing If you go to https://cloud.google.com/free/docs/always-free-usage-limits you will see that there are certain usage items that are always free. For example, under the Google App Engine 28 instance hours/day and 5GB Cloud Storage are just two of several items. The Google Cloud Datastore offers 1GB storage and 50,000 reads, 20,000 writes and 20,000 deletes for free. There are many other aspects of the Google Cloud that include free elements.

Unfortunately, the MySQL and PostgreSQL are not one of them. As a result, the $300 free credit will kick in immediately.

<h1><a name="_Toc11636"></a>Part 2: Setting up Cloud SQL</h1>




Cloud SQL is a part of the GCE to run PostgreSQL and MySQL scripts.

Go to <a href="https://cloud.google.com/sql/">https://cloud.google.com/sql</a><a href="https://cloud.google.com/sql/">/</a><a href="https://cloud.google.com/sql/">.</a>

If you prefer to use MySQL for this assignment, you can find the Quick Start guide at: <a href="https://cloud.google.com/sql/docs/mysql/quickstart">https://cloud.google.com/sql/docs/mysql/quickstar</a><a href="https://cloud.google.com/sql/docs/mysql/quickstart">t</a><a href="https://cloud.google.com/sql/docs/mysql/quickstart">.</a>

If you prefer to use PostgreSQL instead, visit <a href="https://cloud.google.com/sql/docs/postgres/quickstart">https://cloud.google.com/sql/docs/postgres/quickstar</a><a href="https://cloud.google.com/sql/docs/postgres/quickstart">t</a><a href="https://cloud.google.com/sql/docs/postgres/quickstart">.</a>

The pages are self-explanatory, and in case you do not face a problem, setting It up, feel free to skip the rest of Part 2. Below are detailed steps from the same page.  Before you begin

<ol>

 <li>Select or create a Cloud platform project.</li>

</ol>

Go to: <a href="https://console.cloud.google.com/start">https://console.cloud.google.com/star</a><a href="https://console.cloud.google.com/start">t</a><a href="https://console.cloud.google.com/start">.</a> At the top, click on ‘Select a project’, and click  on the     sign.

<ol start="2">

 <li>In the next screen, (as in Figure 2.1), enter a project name.</li>

 <li>Enable billing for your project.</li>

</ol>

In the navigation drawer on the left, click on Billing and add a billing account. Follow the steps and make a billing profile. The details would already be pre-filled as you had entered card details

before. Click on ‘Submit and enable billing’.

<ol start="4">

 <li>Enable the Cloud SQL Administration API. (Select the project that you made earlier in the screen</li>

</ol>

like Figure 2.2.) Wait for API to be enabled and then click ‘Continue’. You will be redirected to the dashboard










Figure 2.1: New Project Screen                             Figure 2.2: Enable the Cloud API.







<h2><a name="_Toc11637"></a>Create a Cloud SQL Instance</h2>

<ol>

 <li>Click on the ‘Go to the Cloud SQL instances page’ button on the Quick-start page. You will get a screen like Fig. 2.3 (a). Click on ‘Select’, select the project and then click ‘Open’. (Fig. 2.3 (b)).</li>

 <li>Click on ‘Create Instance’ in the cloud Instances page. (Fig. 2.4).</li>

</ol>




<ol start="3">

 <li>Select one of MySQL or PostgreSQL and click ‘Next’. Note that PostgreSQL is in beta and might undergo changes which will not be backward compatible.</li>

</ol>







Figure 2.3 (a):  SQL Overview Page.




Figure 2.3 (b): Select the project




Fig 2.4: Create Instance




Figure 2.5: MySQL Second Generation page




The next steps are explained with MySQL.




<ol start="4">

 <li>Click on ‘Choose second generation’ in case you get the next screen as Figure 2.5.</li>

 <li>In the Instance details page, provide an Instance ID name and a root password. Leave the rest as they are. Update this:</li>

</ol>




Click on ‘Create’. You will see ‘Instance is being created’. Wait until the left most wheel turns into a green tick.










Note: On the right-hand side, the three-dot menu has a “Delete” option. Be sure to delete this instance once you are done with the homework to avoid extra charges on the instance.




<ol start="6">

 <li>Click on the instance ID name to open the ‘Instance details’ page, and then click on “Connect using Cloud Shell.<sub>”</sub></li>

</ol>

At the Cloud Shell prompt, connect to your Cloud SQL instance. When the Cloud shell finishes initializing you should see:










db-hw-sql would be replaced with the name of your project.




<ol start="7">

 <li>At the Cloud Shell prompt, connect to your cloud SQL instance.</li>

</ol>

gcloud beta sql connect myinstance –user=root

Replace myinstance with the name of your instance, (in this example, sql-db-1.)







Enter your password (it is a linux terminal so you won’t see it being typed). You should now be able to see the mysql prompt.










Congratulations! You just finished the second part of the assignment.







<h1><a name="_Toc11638"></a>Part 3: Working with SQL (Optional)</h1>




In this part of the assignment, we will build a database with one table and run queries to see if MySQL works as expected.

<ol>

 <li>Create a SQL database on your Cloud SQL instance.</li>

</ol>

CREATE DATABASE test;

<ol start="2">

 <li>Insert sample data into the guestbook database:</li>

</ol>

USE test;

CREATE TABLE entries (guestName VARCHAR(255), content VARCHAR(255),     entryID int not null AUTO_INCREMENT, PRIMARY KEY(entryID));

INSERT intO entries (guestName, content) values (“first guest”, “I got here!”);

INSERT intO entries (guestName, content) values (“second guest”, “Me too!”);

<ol start="3">

 <li>Retrieve the data.</li>

</ol>

SELECT * FROM entries;

You should see:




Congratulations! You are now ready to solve the assignment.




<h1><a name="_Toc11639"></a>Part 4: Programming Assignment</h1>




A database for a social networking application consists of the following tables: x USERS (<strong>USER_ID</strong>, NAME, GENDER, DATE_OF_BIRTH). x FRIENDSHIPS (<strong>USER_ID</strong>, <strong>FRIEND_ID</strong>). x POSTS (<strong>POST_ID</strong>, USER_ID, TEXT).

x COMMENTS (<strong>COMMENT_ID</strong>, POST_ID, COMMENTER _USER_ID, TEXT).




The primary key for each table is bolded. The USER_ID and FRIEND_ID of the Friendships table are foreign keys referencing the Users table. The same applies for the USER_ID of the Posts table. The POST_ID and COMMENTER _USER_ID columns of the COMMENTS table are foreign keys referencing the POSTS and USERS tables, respectively. Everyone can make a comment on any post.

Friendship relationships are symmetric. If user 1 is a friend of user 2, user 2 is a friend of user 1 as well. Consequently, a friendship relationship is represented as two records in the FRIENDSHIPS table. For example, if user 1 is a friend of user 2, the FRIENDSHIPS table must contain two records as follows:

<table width="188">

 <tbody>

  <tr>

   <td width="91">USER_ID</td>

   <td width="97">FRIEND_ID</td>

  </tr>

  <tr>

   <td width="91">21</td>

   <td width="97">12</td>

  </tr>

 </tbody>

</table>




<strong>Notes: </strong>

x The GENDER column of the USERS is represented as ‘F’ for female users and ‘M’ for male users. x The format for the DATE_OF_BIRTH column is ‘YYYY-MM-DD’.

x We haven’t provided any tables of data. You are responsible to make your own with the schema given above and do the query tests on them. We will have our own tables to test your queries.

x Assume the corresponding data for every query exists and that it must return some records. x Don’t use views. They are <strong>not</strong> allowed in this assignment.

x <strong>Temporary</strong> tables, <strong>dummy</strong> tables, … are <strong>not</strong> allowed. All the questions should be answered in one query (with as many subqueries as you need) for that question.

x <strong>For loops</strong> are <strong>not</strong> allowed either.

<strong> </strong>

<strong>Instructions: </strong>

x For each query provide the SQL query and an explanation of why the query works the way it does. Make any assumptions that are not conflicting. Only <strong>use</strong> the <strong>mentioned</strong> attributes (we will make queries only with the <strong>exact </strong>given names of tables and attributes. Also they should be all <strong>CAPITAL</strong> letters).

<strong> </strong>

<strong>Questions: </strong>

<ul>

 <li>List the ids and names of users who have no posts and have one or more comments on POST_ID=5.</li>

</ul>




<ul>

 <li>List the USER_ID of female mutual friends between users 1 and 2.</li>

</ul>




<ul>

 <li>List the USER_ID of users who have more than 2 friends whom have at least one post.</li>

</ul>




<ul>

 <li>List unique USER_ID of female users who were born after ‘1990-12-20’ and commented on posts of USER_ID=10. Show their friends count in a separate column.</li>

</ul>




<ul>

 <li>List the USER_ID of users who commented on POST_ID=7 and are friends with the post creator.</li>

</ul>




<ul>

 <li>List the USER_ID and NAME of the 3 most female commenters, who are friends with USER_ID=20, with at least 3 comments on all the posts combined, excluding the comments under ones posted by USER_ID=10 and themselves. Show their augmented count of comments in a separate column. Also, show their total number of comments in another separate column. [ <em><u>Note 1</u></em>: USER_ID=20 should not be among the 3 answers. <em><u>Note 2</u></em>: <strong>Augmented count of comments (ACC)</strong> is the count of the set of all comments not under “posts by USER_ID=10 and their closed (3 person) group posts” (so exclude all the comments under these 4 people’s posts when counting the number of comments for each female commenter-refer to the example provided in the same folder of Homework 2). <em><u>Note 3</u></em>: the ranking between the 3 top female commenters’ <strong>should be</strong> based on their ACCs. <em><u>Note 4</u></em>: The sum of the count of the augmented comments of these 3 female commenters (ACC1+ACC2+ACC3) should be maximum (refer to case 2 on the next page). <em><u>Note 5</u></em>: For each female commenter, the ACC should be at least 3 as the problem states (refer to case 3 on the next page).  <em><u>Note 6</u></em>: after you maximize the sum, if there were tie cases, make a simple choice for the output and write it down (your own personal choice for ties, if the sums are the same). <em><u>Note 7</u></em>: the result should be a triplet of female commenters. If you couldn’t find any <strong><u>3</u></strong> top female commenters with the appropriate conditions, output should be NULL or nothing. <em><u>Note 8</u></em>: If all the triplets have a member with ACC less than 3, output nothing. But if the ACC of all members of some triplets are at least 3, and the triplet members are all friends with</li>

</ul>

USER_ID=20, you should find the maximum sum of the ACCs among those triplets.]




Cases to clarify Q6 even more:

<ul>

 <li>General case: Suppose the triplet of f1, f2, f3. <strong>For f1</strong>, the augmented count of comments (ACC) is the count of all the <em>f1</em>‘s comments under all the posts without counting the comments under the posts written by f1, f2, f3, and u10.<strong> For f2</strong>, the ACC is the count of all the <em>f2</em>‘s comments under all the posts without counting the comments under the posts written by f1, f2, f3, and u10. <strong>For f3</strong>, the ACC is the count of all the <em>f3</em>‘s comments under all the posts without counting the comments under the posts written by f1, f2, f3, and u10.</li>

 <li>If Linda, Alice, and Lisa have ACC in the order of 10,7,3 <em>versus</em> <strong>Sophia, Eva, and Alice</strong> who have augmented count of comments in the order of <strong>8,7,6,</strong> pick <strong>Sophia, Eva, and Alice </strong>as having more augmented count of comments (because it sums to 8+7+6=<strong>21</strong> in the latter as opposed to 10+7+3=20 in the former), continue the comparisons between any 2 triplets to find the final triplet. Output that final triplet, in descending order of augmented count of comments: Like in <strong>Sophia=8, Eva=7, and Alice=6. </strong></li>

 <li>If Tina, Lucy, and Eva have ACCs in the order of 20,15,2 <em>versus</em> <strong>Tara, Eva, and Alice</strong> who have ACCs in the order of <strong>5,4,3,</strong> pick <strong>Tara, Eva, and Alice </strong>as having ACCs each at least 3 (because <strong>5,4,</strong> <strong>3</strong>&gt;=3 in the latter as opposed to the former, even though, their sum is 20+15+2 &gt; 5+4+3), continue to disregard all the triplets that their ACC (for even one of its members) is less than 3.</li>

</ul>

<strong> </strong>







<strong>           </strong>

Page |

<h2><a name="_Toc11640"></a><strong>Submission Guidelines: </strong></h2>

Some notes for your reference:

<ul>

 <li>The submission MUST be a pdf file named [Student First Name]_[Student Last Name]_HW2.pdf.</li>

 <li>If you have any general questions about the homework, please post your questions on HW2 discussion on USC DEN course forum only.</li>

 <li>Please don’t email the TAs directly with questions. Let other students in the class also benefit from answers and questions. This will also ensure, all the TAs can contribute to class.</li>

 <li>Before asking, please check the forum to see whether similar questions were asked and answered.</li>

 <li>Note that your programs will be automatically checked against other codes. This will be in the amount of percentage similarities. Any percentage can risk your code credibility. So don’t show/share your code with anyone.</li>

 <li>Write your codes in any script (MySQl, PostgreSQL) you feel more comfortable with.</li>

</ul>

However, MySQL is preferred.

<em> </em>

<em>Students can submit the assignment to USC DEN. Just go to the course MY TOOLS Assignments Homework 2. The deadline is firm, only submissions that make it to the system will be graded. Submit your assignment at the latest by 11:59 PM according to the clock on DEN (Dropbox) server. <strong>You will NOT be able to submit your homework after the deadline. </strong>Also, please expect the network traffic around the deadline and network delay won</em><em>’</em><em>t be treated as a valid reason for late submission. The system accepts multiple submissions and only the most recent submission will be graded. Therefore, we advise you to make the initial submission at least a day before the deadline, and overwrite it with a better version or more complete submission after you have it. Good Luck!</em>

Page |