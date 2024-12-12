# Online-Quiz-Assessment-
Online Quiz Assessment 
create DATABASE questiondb for this project

CREATE TABLE Question (
    id SERIAL PRIMARY KEY,
    question_title TEXT NOT NULL,
    option1 TEXT NOT NULL,
    option2 TEXT NOT NULL,
    option3 TEXT NOT NULL,
    option4 TEXT NOT NULL,
    right_answer TEXT NOT NULL,
    difficulty_level TEXT NOT NULL,
    category TEXT NOT NULL
);


INSERT INTO Question (question_title, option1, option2, option3, option4, right_answer, difficulty_level, category)
VALUES
    ('What is a class in Java?', 'A function', 'An object', 'A data structure', 'A loop', 'An object', 'Easy', 'java'),
    ('What does OOP stand for?', 'Object-Oriented Programming', 'Object Ordering Process', 'Operating Overloaded Pointers', 'Order of Operations', 'Object-Oriented Programming', 'Easy', 'java'),
    ('What is a list in Python?', 'A type of loop', 'A built-in function', 'A data structure', 'An object', 'A data structure', 'Easy', 'python'),
    ('Which data structure uses First-In-First-Out (FIFO) order?', 'Stack', 'Queue', 'Array', 'LinkedList', 'Queue', 'Medium', 'python'),
    ('What is a constructor?', 'A member of a class', 'A loop in Python', 'A data type', 'A special method', 'A special method', 'Medium', 'java'),
    ('Which sorting algorithm has the worst-case time complexity of O(n^2)?', 'Merge Sort', 'Quick Sort', 'Insertion Sort', 'Bubble Sort', 'Bubble Sort', 'Hard', 'python'),
    ('In Java, what is used to create an instance of a class?', 'Class', 'Method', 'Object', 'Constructor', 'Constructor', 'Easy', 'java'),
    ('Which keyword is used to define a variable that won’t be reassigned?', 'static', 'final', 'constant', 'immutable', 'final', 'Easy', 'java'),
    ('What is the output of 4 ^ 3 in Python?', '7', '64', '81', '12', '64', 'Easy', 'python');




PostMan

--- to create the quiz according to category --- POST ---  http://localhost:8080/quiz/create?category=java&numQ=3&title=JQuiz
--- to get the quiz which we have created --- GET ----  http://localhost:8080/quiz/get/2
--- to submit the answers of the above quiz
(to get the corrct answers ---open pgadmin and then fire query in the tool box ---- select id, right_answer from question where id=2 or id=10 or id=17 (here take id according to the quiz) then we'll get the correct answers.
 type --   to submit the quiz--- POST --- http://localhost:8080/quiz/submit/1    then in body then raw format is JSON type---

[
    {
        "id": 2,
        "response": "Object-Oriented Programming"
    },
    {
        "id": 10,
        "response": "Ability to take multiple forms"
    },
    {
        "id": 17,
        "response": "public"
    }

]

----- ( here answers should be according to the quiz's questions) 
  then send....it will show only the score of correct quiz in numbers. end...




