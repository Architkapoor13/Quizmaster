# QUIZMASTER
**Website Link:** [https://quizmaster.study](https://quizmaster.study/)

### Description
During these COVID days where everything is going online, so are the tests conducted by the schools, universities so quizmaster have all the things you needed to smoothly conduct quizzes and evaluate your students.

### Language used:
1. Python(Django)
2. Javascript
3. CSS(both simple and bootstrap)
4. HTML

### Models made(Database Structure)
1. Custom User Model:
    1. Added the fullname field(Although it is available but made my own single Field for this).
    2. Added two boolean fields to tick if the user is a **teacher** or a **student**.
    
2. Quiz Model:  
    1. owner: the foreign key to the user who made the quiz.
    2. quizid: The **quizregnumber** function will generate the custom quizid and wil assign to this field. These quizid's will be used to find the quiz and get enrolled.
    3. quizname: this field holds the name of the quiz being made.
    4. instructions: This filed is char type field and will hold the instructions for the quiz.
    5. totalquestions: This field will hold the value of total questions the student will get if the students starts the quiz.
    6. totalquestionsadded: This field will hold the number of total questions added for the quiz, as you might think that totalquestions field was enough but this thing helps in prevention of cheating as the teacher can add as many number of questions as desired but the student will get only the **totalquestions** number of questions in the quiz and **note:** each student will be getting random questions from that questionset, that is the questions they may get may be same and may not be same and the order of questions might be different.
    7. type: This refers to what type is the quiz is, as **quizmaster** holds two types of quizzes, the single answer correct and the multiple answer correct.
    8. date: This is the date of the quiz, that on which date the quiz will be conducted.
    9. stime: The start time of the quiz.
    10. etime: The endtime of the quiz.
    11. duration: The total duration of the quiz, there might be a case where the stime and etime might offer a big window of time to students but still the quiz is of less time. And the students can start the quiz at any time between the stime and etime, but here's a catch if the quiz windows is of two hours and the quiz durations is of 10 mins then in those 10 mins the students can take the quiz but if the student tries to take the quiz at any time betweent the last 10 minutes then the difference of the time and **etime** will the total time given to the student, this means that no student can have the quiz running after the etime of the quiz.
    12. enrolled: This is the field which keeps the tracks of the students that are enrolled in this quiz.
    
3. Question Model:
    1. quizname: This field holds the quiz object of the Quiz modal to which the question belongs.
    2. image: This is an optional field, if there's an image then it will be stored here.
    3. option[i]image: Here **i** varies from 1 to 4, it stores the option images if they are availbale, again it is optional.
    4. questiondec: Here is the actual question asked will be stored.
    5. option[i]: Here **i** varies from 1 to 4, it stores the options of the current question.
    6. answers: Here the answer/answers will be stored.
    
4. AttemptedQuizdetails: 
    This modal will contain the information about the student that when the student started the quiz and when ended the quiz, total time taken by the student, the questions numbers that the student got while attempting the quiz.
   
5. Studentresults: 
    1. student: This is the student who's result is this.
    2. quiz: This is the quiz that the student gave and the result has been generated.
    3. totalcorrect: This is the field which stores the number of correct questions.
    4. partialcorrect: This stores the partial correct questions(in the quiz type multiple answer correct).
    
6. Studentresponses:
    1. result: This holds the reference to the object of the **Studentresults** class.
    2. ques: This is the Question object of which the responses has to be stored.
    3. correctans: This is the correct answer/answers of the question.
    4. answermarked: This is the answer/answers marked by the user.
    5. match: This is the booleanfield and keeps track that the answer marked is equal to the correct ans or not, if yes then it will be true and if not then it will be false.
    
### Features of Quizmaster
1. Register: You have to register yourself to use all the features of this website and to do so by going on the register tab. You can register as a student or a teacher depending on what purpose you want to use the website for.

2. Login: Once you have registered, you will be able to login into the website.

3. #### Features when registred as a teacher
    1. Make Quiz: You can make a new quiz by going on to the **Make Quiz** tab and then by clicking on the button **New Quiz**.
        1. You can create two types of quizzes on Quizmaster, **single answer correct** and the **multiple answer correct**.
        2. You can add a question bank from which the students will get random questions, you give the total questions that specifies the total questions in the quiz and then the total questions to be added(here's there a role of the question bank).
        3. You can also add images int the questions if you want.
        4. You can add the images to options as well, if your question has this requirement then you can go for it.
        5. You will have to add the answers along with the questions, mark the **radio buttons** for the single answer correct questions and mark the **chekboxes** for the multiple answer correct questions.
    2. View Quiz: You can view the quiz made by you on going to the **My quizzes** tab and expanding the quiz you want to see and click on the **view** button.
    3. You can see the results of the quiz once the quiz is completely over, and you can even see the individual detailed quiz results of all the students who took the quiz and in the detailed quiz you can see the responses marked by that student.
    4. delete a quiz: You can delete the quizzes that are redundant or those that have been wrongly built.
    
4. #### Features when registered as a student
    1. Search the quiz: When your teacher will open a quiz and share the quizid with you and when you enter that quizid in the search box then you will be able to find the quiz and when expanding that quiz you can enrol yourself in that quiz.
    2. My Quizzes: You can see your enrolled quizzes on this tab:
        1. The quizzes that appear in red color are the quizzes that are over, the quizzes in yellow are the quizzes that are to be conducted in future and the quizzes in green are the currently started quizzes.
    3. When you exapnd a green quiz there will be a **start quiz** button shown, which clicked the quiz will begin and timer starts with duration as the value.  
    4. When you start the quiz then you will be seeing the questions that are to be answered.
    5. while answering the question to clear the selection of a question click on the button provided at the end of that queston.
    6. You can submit the quiz before the time if you have already answered the questions or when the timer hits 0 the quiz will be submitted automatically.
    7. Results will be shown to you after the complete quiz is over then you can go to the results tab and see the results of you attempted quizzes, but **note:** The results will be only then available when the complete quiz is over.
    
5. Results: The result of the students will be in the format that they will be able to see the **total correct** questions, **questions attempted** and their **responses**, and in front of each question there will be written if the that question is correct, wrong or not attempted.
So the students can have a better understanding of their attempt and they can further improve that. Teachers can see the results of all the students who has attempted the quiz. In both the short result and detailed results.

### Full Mobile Responsive Website
Quizmaster has been built by keeping this view that not every student or not evry teacher has pc/laptop to access the websites, but the phones are common so this website has been built mobile responsive and can be accessed via mobile in the complete ease.

