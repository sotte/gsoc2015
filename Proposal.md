# gsoc2015

Project Name-Vector Math Library Integration in Numpy
Project Mentor-Julian Taylor
Synopsis:-

This project is about improving the performance of
elementary/transcendental functions in numpy. These functions are for
example exp (base-e exponential e^x), pow (power x^y), sin, cos, tan, etc.

Present Situation:-

Currently numpy uses the system standard C math library to implement
most of these functions.
These are the timeit calls for the present trigonometic numpy calls
>>> x= range(1000)
>>> def numpy_sin():
...     return np.sin(x)
...
>>> n=10000
>>> timeit.timeit(numpy_sin,number=n)
1.83381986618042

>>> def numpy_cos():
...     return np.cos(x)
...
>>> timeit.timeit(numpy_cos,number=n)
1.7894339561462402

After studying the numpy code base, i have found out that this huge time being
consumed is due to the fact that the c functions take scalars as input and
small calculations also take a lot of function calls and hence need to be
changed.

Goals of the Project:-

->Integrating faster math library classes to NumPy of sleef and yeppp.
->Setting up representative benchmarks for the new functions compared to the
  previous functions.
->Investigating possible accuracy and correctness differences in the
implementations


Project:-

My efforts would actually be in three different tasks.

Firstly, I will study the way how a function is called
in Numpy and what exactly is the problem which is making the calls slower. And
then, find in the new Sleef and Yeppp library classes, the things that is
making it faster.

Secondly,
I will create a new header file in c , which includes the faster codes taken
and improved from both sleef and Yeppp.

Thirdly,
I would implement the new header file in the numpy code base and change the
function calls wherever necessary to run the new header file from numpy code
base in generate_umath.py


Work Done-
I have spent the past month in studying the numpy-master code base and located
the function calls.
I have downloaded sleef and yeppp lbraries and built them in my computer.
I have then created a c file constituting funcions from both yeppp and sleef.
The file consists of some trigonometric as well as some different mathematical
functions. You can find the link to that file below.[1]
But, the file still needs improvement.
I have also spent some time solving issues in the numpy github page but was
partially successful in doing so but made significant progress in issue #3595.

RoadMap-

April 27-May 10 -> Complete my header file consisting of all the different
mathematical functions from Sleef and Yeppp.

May 10-May 31 -> Adding the header file to the code base and changing the
function calls in the existing code.

June 1-June 25 -> Calcuating the benchmarks and check whether the functions
are working for all numpy objects.

June 26-Submit the mid term analysis.

June 27- August 17- Clean the code and write new docstrings if necessary and
submit my project.


Biography-

My name is Shubhankar Mohapatra . I am a 18 year old first year undergraduate
in IIIT Bhubaneswar,India.I love participating in competitive programming
contests.The recent contest was the March Cook off in Codechef.
I believe that i am a good programmer and have previous experience in C and
Java.I have won some programming contets in my college and high school.I also
have some knowledge in Matlab and hence i am used to some array based numerical
software. I also have knack for mathematics and hence, i have chosen this
project.I am always up for new challenges and i consider this project as a
challenge that i will be able to complete.I also want to continue contributing
to NumPy open source foundation in future and the open source community as a
whole.

I know that i couldn't provide a patch in numpy but I have tried my level best
in solving bugs and i am also ready to solve any bug that is given to me to
test my knowledge.

IRC Nickname-mshubhankar
E-mail- shubhankarmohapatra@gmail.com
Phone No- +91 7064675485

Other Objectives-

I have seen that numpy manuals are provided in many languages but not in indian
languages. I was wondering if I can help in converting the manual into Hindi.

Links
[1]- https://www.dropbox.com/s/k2f80hxp2006g0j/functions.c?dl=0
