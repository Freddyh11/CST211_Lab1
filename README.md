# CST211_Lab1

CST 211 Lab 

Lab 1 

Single Dimensional Array 

Description 

Write an Array ADT that is based on a dynamic array. Use the following class definition to build your class. Work off of the associated Shell. Use the included tests (30 tests) to test your classes. 

 

private: 

T* m_array; 

int m_start_index; 

int m_length; 

int m_newArray; 

  

public: 

Array() : m_array(nullptr), m_start_index(0), m_length(0) {}; //default constructor 

Array(int length, int start_index = 0); //constructor 

Array(const Array<T>& copy); //copy constructor 

Array(Array<T>&& move) noexcept; //move constructor 

  

~Array(); //destructor 

  

Array<T>& operator = (const Array<T>& move); //overloaded copy assignment operator  

Array<T>& operator = (Array<T>&& copy) noexcept; //move assignment operator 

T& operator [] (const int); //overloaded subscript operator 

  

const int getStartIndex(); //gets start index 

void setStartIndex(const int start_index); //sets start index 

const int getLength(); //gets length of array 

void setLength(int length); //sets length of array 

 

Stipulations 

Make sure that the length values are valid. 
Make sure the user never goes out of bounds. If they do, throw an exception (see below). 
The user should be able to set the length of the array at any time to any valid length, including lengths that are smaller than the current length. This may result in the loss of data but should still be allowed. 
The user should have the capability of specifying a negative starting index. 
There should be NO memory leaks. 
Your name should be in the final project name AND in each file in the project (Array.h, Exception.h and the testing file.cpp). 
Each method should have at least 1 comment. 
You must create and use the following Exception class. This class will be used to handle the following exceptions: 
Specifying an index smaller than the lower bounds. 
Specifying an index larger than the upper bounds. 
 

Exception class: 

 

private: 

string m_msg; 

  

public: 

Exception() : m_msg("Unknown Error") {}; //default constructor 

Exception(const string& msg) : m_msg(msg) {}; //constructor with parameters 

Exception(const Exception& move) : m_msg(move.m_msg) {}; //copy constructor 

Exception(Exception&& copy) noexcept; //move constructor 

  

Exception& operator = (const Exception& move); //copy assignment operator 

Exception& operator = (Exception&& copy) noexcept; //move assignment operator 

  

const string getMessage() { return m_msg; } //gets exception message 

void setMessage(const string& message) { m_msg = message; }    //sets exception message 

  

friend std::ostream& operator << (std::ostream&, const Exception&); //output operator 

 

 

Grading: 

Correct Array Members 15 pts 
Correct Exception Members 10 pts 

No Memory Leaks 10 pts 

Documentation 10 pts 

Naming 5 pts 

Tests passed 50 pts 
