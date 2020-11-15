---

How to be a DaskMaster PART-1
Implementation of Dask.Distributed, Dask.delayed & Dask Task Graph in 6 minutes {how in God's name} :-0
Definition of Dask:

Dask is an open-source library for parallel computing, written in Python. Originally developed by bleh bleh… (You really don't wanna know about it, do you?)
My blog will walk you through what Dask is so that you don't waste your precious time on grasping it and wondering what the definition is.
Let's just assume that you have the world's best computer, with a great processor and ample RAM. Yet, you can't run your model which uses a HUGE dataset (think numerous columns and an infinite number of rows)! You may run your whole notebook on the server, which will cost you a fortune.
This is where Dask comes in. It helps you to provide parallelism and can help you compute your data in hours or even in minutes. This saves you from spending a whole lot of money on the server (which can be put to better use for buying a Netflix subscription)…
Join The Wonderful Journey Of Using Dask On Big Datasets.

First off, we must have a better understanding of the working of Dask on a few lines of code. Boring stuff coming in 3..2..1.



This is a basic python code, with 2 functions. One is an incrementing function and the other is an addition function. But that's not the main point..
The main point is the execution time of this code. It will take around 2.5–3.11 seconds depending on the processing of your "LAPTOPS'.
Now we will see Dask or as I like to call it, parallel code.


---

Remember to install the Dask libraries to see the below code in working! As I am assuming you have all the libraries installed.



You look confused????WHYYYY? WAIT!!!
Never heard of the infamous quote!?

Patience is bitter but it's fruit is sweet. ~ARISTOTLE


---

What is delayed?? What is "Thunk"??Why I am getting that output??
The Dask delayed function decorates your functions so that they operate lazily. Rather than executing your function immediately, it will defer execution.
'Thunk' is a keyword which we use in reference to lazy execution. Basically, Dask does 'lazy' computing.

When you are making a delayed (inc), the output will not be printed but will execute partially. Instead of executing x and y sequentially, both get executed simultaneously, upon calling Compute( ). This evidently saves time. When you execute the code z.Compute(), then the output gets printed.



So Dask basically executes the x and y simultaneously or I say parallelly. and that will save you time. The running time would be less than the previous time of the python code.
BUT the time difference is 0 if you remove the Sleep function.
Keep in your head that the above code is just to explain the working and to show you how dask actually works. The time difference will get significant when dealing with HUGE datasets.
Now time for some visual action you can see in dask and understand correctly that what the deal is!!?.
for that, we first have to create a Client that will redirect us to the Task Graph window. Task Graph is a status bar where you can see the backend of the dask functionalities and you can see other things too.



This code will help you to generate a link to the Task graph. By clicking on this link, you can see how Dask is working.
Now to get into more detail that what is n_worker, thread_per_worker and…bleh bleh, you could visit:
https://docs.dask.org/en/latest/diagnostics-distributed.html
But for now, it is important to understand that it will show us: how the memory is getting loaded, which function is executing first etc…
Let's get into more detail and try to understand the following code.
for loop with the inc function - we are generating a list, and then getting 'total' with the help of sum function integration.
Now is the time for the parallel code! But before running the code below, try to open the Task Window to see both tabs in front of you. Use: 'Window + Left Arrow Key'.



for loop with the delayed inc function. Then, computing the 'total'
After running this code, let's see the Task Graph. Some movement is evident in the Task Graph.
What is happening??
Actually the for loop is not working like a for loop. here the delayed object is not calculating the result for any " i ". when you see the window of task graph you will notice that there are 8 huge GREEN blocks which are our "i" result. They all are computing and executing parallelly. You can also see the small RED line which represents the total.compute( ) execution.



---

TIME FOR THE CLOSURE!!
Dask is implemented worldwide and is widely used when working on a dataset. Well, you can't be a DaskMaster in 6 mins but now you do have a little understanding of Dask.
Please tell me if you'd ever heard of Dask before reading this, and whether you've ever used it in your job or for a project.
" Signing off ,
MANJOT SINGH DHILLON
Github-manjotsingh99
LinkedIn -www.linkedin.com/in/MSeeeeeeeeee
