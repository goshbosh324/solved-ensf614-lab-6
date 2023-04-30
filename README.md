Download Link: https://assignmentchef.com/product/solved-ensf614-lab-6
<br>
<strong>Objectives: </strong>

The purpose of this lab is:

<ol>

 <li>More practice to understand concepts data structures in C++</li>

 <li>Understand the concepts of overloading operators in C++.</li>

 <li>Understanding and developing a simple program in Java that uses one of the important design pattern models called “Strategy Pattern”, and “Observer Pattern”.</li>

</ol>

<strong> </strong>

<strong>Marking scheme:  </strong>

The total mark for the exercises in this lab is: <strong>59 marks  </strong>

<ul>

 <li>Exercise A (14 marks)</li>

 <li>Exercise B (16 marks)</li>

 <li>Exercise C (12 marks)</li>

 <li>Exercise D (2 marks) Exercise E (15 mark)</li>

</ul>

<strong> </strong>

<strong>Exercise A (: </strong>

<strong> </strong>

<strong>Part I – Drawing an AR Diagram for a Dictionary Data Structure (5 marks):</strong> <strong> </strong>

<em>Dictionary</em> is a data structure, which is generally an association of unique keys with some values. (Other common names for this type of data structures are Map and Lookup Table). <em>Dictionaries</em> are very useful abstract data types (ADT) that contain a collection of items called <em>keys</em>, which are typically strings or numbers. Associated with each key is another item that will be called a <em>datum</em> in this exercise. (“Datum” is singular form of the plural noun “data”.)

Typical set of operations for a Dictionary include: inserting a key with an associated datum, removing a key/datum pair by specifying a key, and searching for a pair by specifying a key. Dictionaries can be implemented using different data structure such as arrays, vectors, or linked lists. In this exercise a linked list implementation, called DictionaryList class is introduced.  Class DictionaryList, in addition to a node-pointer that usually points to the first node in the linked list has another node-pointer called cursor that is used for accesses to the individual key/datum pairs.

<strong> </strong>

<strong> </strong>

<strong>What to do: </strong>

<strong> </strong>

Download files dictionaryList.h, dictionaryList.cpp, mystring.h, mystring.cpp, and exAmain from D2L.  Read them carefully and try to understand what the functionalities of these classes are doing. Note also the definition of class Node that contains three private data members:  keyM, datumM, and nextM, a pointer of type Node. Also, class Node declares class DictionaryList as a friend. For details about friend keyword in C++, please refer to your lecture notes. <strong> </strong>




The idea of implementing a dictionary as a linked list is simple: each node contains a key, a datum, a pointer to the next node, and another node pointer called cursor that can either point to any node or can be set to NULL.  For better understanding of the details of DictionaryList, try to understand how the function insert works. Further details about the operation of inserting a node into the list, can be learned from following AR diagram, which represents <strong>point one</strong> in this function, when reaches this point for the second time:







Now that you know how class DictionaryList and its member function insert work, draw an AR diagram for <strong>point TWO</strong> in function remove, when the program reaches this point for the first time.

<strong>Important Note:</strong> If you read this exercise carefully, you will find that this exercise is an excellent example for learning more about concept of destroying and copying C++ objects. It tells you more about how de-allocate memory of nodes in a linked list, and how to make copies of a linked list object. I recommend you pay attention to these details and if you have any questions please do not hesitate to contact me.

<strong>What to Submit: </strong>

<em>Submit you AR diagram.  </em>

<strong> </strong>

<strong> </strong>

<strong>Exercise B – Overloading Operators in C++ (16 marks) </strong>

<strong> </strong>

In this exercise you are going to use the same files that you have used in exercise B, and you will overload several operators, for classes Mystring, and DictionaryList.




<strong>What to Do:  </strong>




Open the file exAmain.cpp and uncomment the line that calls function test_overloading, and its prototype at the top of the file.  Then, change the conditional compilation right above the implementation of test_overloading from #if 0 to #if 1 and try to compile or run the program. Now you will see a few errors. These errors are due to the fact that this function is trying to make some operations on Mystring or DictionaryList objects using common C++ relational operators such as, &gt;, &lt;, &lt;=, !=, or other type of operators such as &lt;&lt; or [] that are not by default defined by C++ compiler for objects of Mystring or DictionaryList. Your job in this assignment is to find out which operator is required to be overloaded and write the necessary code in mystring_B.h, mystring_B.cpp, dictionalyList.h and dictionaryList.cpp. For example, one of the lines in exBmain.cpp is:




<strong>if</strong><strong>(dl.</strong><strong>cursor_datum</strong><strong>() &gt;= (dl2.</strong><strong>cursor_datum</strong><strong>())) </strong>

<strong>    </strong><strong>cout</strong><strong> &lt;&lt; </strong><strong>endl</strong><strong> &lt;&lt; dl.</strong><strong>cursor_datum</strong><strong>() &lt;&lt; </strong><strong>” is greater than or equal “</strong><strong> &lt;&lt;  dl2.</strong><strong>cursor_datum</strong><strong>();</strong>




In the above if-clause, the binary operator &gt;= is used to compare two Mystring objects and find out which one is greater than the other one (lexicographically).  Then it tries to print the value of string on the screen using C++ insertion operator &lt;&lt;.




Without overloading the operators &gt;= ,  and &lt;&lt; for class Mystring, this line will show errors such as: Invalid operands to binary expression Mystring




Since there are several operators to be overloaded, again the best strategy is to work incrementally. Means first comment out most of the lines in function terst_overloading, except the two lines that uses the operator &gt;= and &lt;&lt; . Then write the necessary code in the given files. If they work fine, then uncomment the next few lines to implement and test the next operator — until all required operators are properly defined and tested.




<strong>What to Submit: </strong>

For exercises B following files electronically on the D2L:

<ul>

 <li>As part of your lab report (PDF file), submit the copy of all .cpp and .h files, and the output of your program.</li>

 <li>Submit a zipped file that contains your actual source code (all .cpp and .h files)</li>

</ul>

<strong><u>Exercise C – Strategy Desing Pattern</u></strong>




The purpose of this exercise is to give you an opportunity to practice using Strategy Design Pattern in you program.




<strong>Read This First – Why and Where to Use Strategy Pattern  </strong>




The subject of applying different strategies at different points of time (for good reasons) is a real demand in many real-world projects or processes. This is also a true requirement for many software applications. One of the most common applications of the Strategy Pattern is where you want to choose and use an algorithm at the runtime. A good example would be saving files in different formats, running various sorting algorithms, or file compression.

In summary, Strategy Pattern provides a method to define a family of algorithms, encapsulate each one as an object, and make them interchangeably used by a client.




<h1>Read This Second – A Quick Note on Strategy Pattern</h1>

The Strategy Pattern is known as a <strong>behavioural </strong>pattern – it’s used to manage algorithms, relationships and responsibilities between objects. The definition of Strategy Pattern provided in the original Gang of Four book states:







The diagram shows that the objects of Context provide means to have access to objects that implement different strategy.

<strong>What to Do: </strong>

<strong> </strong>

Since last Spring the subject of Java Generic was not covered. We have two versions of Exercise C and D.  One exercise which is not using Java Generic, and related files are posted in subdirector EXC_D-V1. The second version is for those of your that seeking for more challenge. The files related to this version is stored under the subdirector EXC_D-V2.  No matter which version you choose the rest of the instructions will be the same:




Assume as part of a team of the software designers you are working on an application that allows its clients to be able to use different sort methods for a class called MyVector.  For the purpose of this exercise you just need to implement two sort methods: bubble-sort, and insertion-sort. And of course, your design must be very flexible for possible future changes, in a way that at anytime the client objects should be able to add a new sort technique without any changes to the class MyVector (for the generic version will be MyVector&lt;E&gt;).




<strong>Please follow these steps: </strong>

<strong> </strong>

<strong>Step 1:</strong> Download file DemoStrategyPattern.java form D2L. This file provides a client class in Java that must be able to use any sort techniques at the runtime.




<strong>Step 2: </strong>Download file called Item.java This is a class that represents data object. It means its private data member item can be used and sorted within the body of MyVector objects.




<strong>Step 3: </strong>Now your program must have the following classes:




<ul>

 <li>Class MyVector (or MyVector &lt;E&gt; which is also Bound to only Java Number type and its decedents). This class should have a private data member called storageM of type ArrayList&lt;Item&gt; (or</li>

</ul>

ArrayList&lt; Item&lt;E&gt; &gt; for the generic version), which provides space for an array of certain size, and more

data member as needed, and a second private data member called sorter that is a reference to an object of the Java interface Sorter (or interface Sorter &lt;E&gt; for the generic version).  Class MyVector should also have at least two constructors as follows:

o A constructor that receives only an integer argument, n, to allocate memory for an array with n elements. o A constructor that receives only an ArrayList object, arr, and makes storageM an exact copy of arr.




Also must have at least the following methods, which are used in the client class

DemoStrategyPattern:




<strong>public</strong> <strong>void</strong> add(Item value): That allows to add a new Item value to storageM




<strong>public</strong> <strong>void</strong> setSortStrategy(Sorter s): That allows its private data member register with a an object that implements Sorter.

<strong>public</strong> <strong>void</strong> performSort():That allows sort method of any sorter object to be called.




<strong>public</strong> <strong>void</strong> display():That displays data values stored in storage on the screen in one line. For example:  1.0  2.0  3.0  4.0  5.0




<ul>

 <li>Two Concrete classes called BubbleSorter and InsertionSorter that one implements a bubble sort algorithm and the other one implements insertion sort algorithm.</li>

</ul>

<strong> </strong>

<strong> </strong>

<strong><u>Exercise D:</u></strong>




This is a smaller size exercise. The purpose of this exercise is to demonstrate how you can add a new algorithm to exercise A called SelectionSorter that uses selection-sort and can be used by the class client without making any changes to the class MyVector.




<strong> </strong>

<strong>What to Submit for Exercises C and D?  </strong>

<strong> </strong>

<ol>

 <li>Copy and paste all your source codes and your program output as part of your lab report and submit it in PDF format into the D2L Dropbox.</li>

 <li>Create and submit a zip file that contains your source code file (.java files) and submit it on the D2L Dropbox.</li>

</ol>




<strong><u>Exercise E (15 marks):</u></strong><strong>  </strong>

The purpose of this exercise is to give you an opportunity to practice using Observer design pattern in a simple Java program.




<h1>Read This First – A Quick Note on Observer Pattern</h1>

The Observer pattern is also one of the <strong>behavioural </strong>patterns – This pattern is also used to form relationships between objects at the runtime.







<h2>Figure 1</h2>







<strong>Figure 1:</strong> shows that the concrete subjects can add any observers, and when any changes happen to the data, all observers will be notified. The following figures may help you to better understand how this pattern works.




<table width="633">

 <tbody>

  <tr>

   <td width="315"> </td>

   <td width="317"> https://www.gofpatterns.com/design-patterns/module6/tradeoffs-implementing-observerPattern.php</td>

  </tr>

 </tbody>

</table>




<h2>Figure 2</h2>




Figure 2 is a simple demonstration of the observers’ notification concept and figure 3 illustrates the most common form of using this pattern. Any changes to the subject (data a, b or c) will be immediately translated in three observer views (tabular format, bar chart, or pie chart).

Using observer pattern is not limited to GUI presentation; it can be used for any notification system. Here is another example:




<strong>What to Do: </strong>




Download file ObserverPatternController.java form D2L. This file provides a client class that demonstrates how your observer pattern works. For the purpose of this exercise you just need to have three observers, and your design must be very flexible for change. In other words at anytime you should be able to add a new observer or remove an observer without any changes to the subject or observer classes. Your program must have the following interfaces and classes:

<ul>

 <li>Interface Observer with the method update that receive a parameter of type ArrayList&lt;Double&gt;</li>

 <li>Interface Subject with the required methods.</li>

 <li>Class DoublArrayListSubject, with a data list of type ArrayList&lt;Double&gt; , called data that is supposed to be visible to the observers. Consider other data members as shown in the Observer Pattern Design Model. This class should also have at least the following methods:

  <ul>

   <li>A default constructor that initializes its data members as needed. For example should create an empty list for its member called data.</li>

   <li>Method addData that allows a new Double data to be added to the list o Method setData that allows changing the data at any element in the list</li>

   <li>Method populate that populates the list with the data supplied by its argument of the function, which is an array of double.</li>

   <li>Other methods as needed</li>

  </ul></li>

</ul>




<ul>

 <li>Three concrete Observer classes as follows: o Class FiveRowsTable_Observer This class should have a function display that shows the date in 5 rows as illustrated in following example (any number of columns, as needed):</li>

</ul>

10     30     11

20     60     23

33     70     34

44     80     55

50     10

This class should also have a constructor to initialize it data member(s) as needed and to register the object as an observer.




<ul>

 <li>Class ThreeColumnTable_Observer that displays the same list of data in tabular format as illustrated in the following example (3 columns and any number of rows as needed):</li>

</ul>

10    20    33

44    50    30

60    70    80

10    11    23

34    55

This class should also have a constructor to initialize it data member(s) as needed and to register the object as an observer.




<ul>

 <li>Class OneRow_Observer that displays the same vector of data in single line as follows: 10 20 33 44 50 30 60 70 80 10 11 23 34 55</li>

</ul>




This class should also have a constructor to initialize its data member(s) as needed and to register the object as an observer.




If you have all the classes and methods defined properly, your program with the given client class ObserverPatternController should produce the following output:




Creating object mydata with an empty list — no data:

Expected to print: Empty List …

Empty List …

mydata object is populated with: 10, 20, 33, 44, 50, 30, 60, 70, 80, 10, 11, 23, 34, 55  Now, creating three observer objects: ht, vt, and hl  which are immediately notified of existing data with different views.




Notification to Three-Column Table Observer: Data Changed:

10.0 20.0 33.0

44.0 50.0 30.0

60.0 70.0 80.0

10.0 11.0 23.0

34.0 55.0




Notification to Five-Rows Table Observer: Data Changed:

10.0 30.0 11.0

20.0 60.0 23.0

33.0 70.0 34.0

44.0 80.0 55.0

50.0 10.0




Notification to One-Row Observer: Data Changed:

10.0 20.0 33.0 44.0 50.0 30.0 60.0 70.0 80.0 10.0 11.0 23.0 34.0 55.0




Changing the third value from 33, to 66 — (All views must show this change):




Notification to Three-Column Table Observer: Data Changed:

10.0 20.0 66.0

44.0 50.0 30.0

60.0 70.0 80.0

10.0 11.0 23.0

34.0 55.0




Notification to Five-Rows Table Observer: Data Changed:

10.0 30.0 11.0

20.0 60.0 23.0

66.0 70.0 34.0

44.0 80.0 55.0

50.0 10.0




Notification to One-Row Observer: Data Changed:

10.0 20.0 66.0 44.0 50.0 30.0 60.0 70.0 80.0 10.0 11.0 23.0 34.0 55.0




Adding a new value to the end of the list — (All views must show this change)

Notification to Three-Column Table Observer: Data Changed:

10.0 20.0 66.0

44.0 50.0 30.0

60.0 70.0 80.0

10.0 11.0 23.0

34.0 55.0 1000.0




Notification to Five-Rows Table Observer: Data Changed:

10.0 30.0 11.0

20.0 60.0 23.0

66.0 70.0 34.0

44.0 80.0 55.0

50.0 10.0 1000.0




Notification to One-Row Observer: Data Changed:

10.0 20.0 66.0 44.0 50.0 30.0 60.0 70.0 80.0 10.0 11.0 23.0 34.0 55.0 1000.0

Now removing two observers from the list:

Only the remained observer (One Row ), is notified.




Notification to One-Row Observer: Data Changed:

10.0 20.0 66.0 44.0 50.0 30.0 60.0 70.0 80.0 10.0 11.0 23.0 34.0 55.0 1000.0 2000.0




Now removing the last observer from the list:




Adding a new value the end of the list:

Since there is no observer — nothing is displayed …




Now, creating a new Three-Column observer that will be notified of existing data: Notification to Three-Column Table Observer: Data Changed:

10.0 20.0 66.0

44.0 50.0 30.0

60.0 70.0 80.0

10.0 11.0 23.0

34.0 55.0 1000.0

2000.0 3000.0

<em> </em>

<strong>What to Submit for Exercise E?  </strong>

<strong> </strong>

<ol start="3">

 <li>Copy and paste all your source codes and your program output as part of your lab report and submit it in PDF format.</li>

 <li>Create and submit a zip file that contains your source code (.java file(s))</li>

</ol>

<strong> </strong>





