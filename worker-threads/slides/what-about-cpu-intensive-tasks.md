## But what about CPU intensive tasks?

Note: What happens if we need to do synchronous intense stuff - complex calculations in memory on a large dataset?
We might have a synchronous block of code that takes a lot of time
and will block the rest of the code from executing.


What do we mean by blocking?
Note: A function is considered blocking if the main event loop must wait until it has finished executing the next command.
A "non-blocking" function will allow the main event loop to continue as soon as it begins
and typically alerts the main loop once it has finished via a "callback"


Don't block the event loop!
Note: Good rule of thumb when we write code...
we try to keep the event loop running and avoid things like synchronous network calls or infinite loops that would block it.


JavaScript and Node.js were not meant to be used for CPU bound tasks
