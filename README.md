Our second data structure is a “Queue”.

\*Image from dbader.org

A queue data structure is used to store data in a style which is “First In, First Out” (FIFO). Queues are similar to stacks but are different in that they allow for inserting and removing from both ends of the data structure. If you think about how a line at a store works, this may start to make more sense. Imagine there are 3 people standing in the line. You walk up and take your place in line but now you have to wait until the people who arrived first take their turns. Not a minute into waiting, 10 other people come and take their place in line behind you. Luckily, because you arrived first, you won’t have to wait for all of them. You will get taken care of first. This is “First In, First Out” in action and is exactly what a queue allows for.

Below are some operations of a queue along with their time complexity when implemented with a python list:

|**Function**  |**Description**  |**Big O Notation**|
| :- | :- | :- |
|queue.Enqueu()  |Adds an element to the back of the queue  |O(1)|
|queue.Dequeu()  |Removes an element from the front of the queue  |O(n)|


Below is an image diagram that illustrates what a queue might look like.

\*Image from 101computing.net

As you can see, dequeue takes elements from the front just like a person standing in line would be dequeued when their turn is up. Enqueue adds an element to the back just like someone getting in the back of the line.

Now that we fundamentally understand what a queue is, let’s look at some examples.

Imagine you are building an app for a DJ that will allow users to send song requests to that DJ which will be played in the order they are received. You are given 3 lists of songs that are in order. If there are no songs in the list, you should display that there are no requested songs. How will you display the next song to be played to the DJ?

Here are the lists of songs:



```
songList = ["Welcome to Paradise", "Smells Like Teen Spirit", "Come as You Are" "Blackbird", "On the Wing", "Nothing Else Matters"]

songList2 = ["Super Bon Bon", "For Once In My Life", "Start the Machine"]

songList3 = []
```


There are various ways to implement a queue in python but for the sake of simplicity, we will use the python list implementation. This method provides us with O(1) time complexity for append operations and O(n) time complexity for pop opperations. First we will include the Queue class.

```
class Queue:
    """
    A basic implementation of a Queue
    """

    def __init__(self):
        """
        Start with an empty queue.
        """
        self.queue = []

    def enqueue(self, value):
        """
        Add an item to the queue
        """
        self.queue.append(value)

    def dequeue(self):
        """
        Remove the next item from the queue. 
        """
        value = self.queue[0]
        del self.queue[0]
        return value

    def is_empty(self):
        """
        Check to see if the queue is empty.
        """
        return len(self.queue) == 0
    
    def __len__(self):
        """
        Support the len() function
        """
        return len(self.queue)

    def __str__(self):
        """
        Provide a string representation for this object.
        """
        result = "["
        for item in self.queue:
            result += str(item)
            result += ", "
        result += "]"
        return result
```

Next we will include our queue function (notice how we are using the enqueue and dequeue methods specified in the Queue class):

```
def queueDemo(songList):

    # Create an instance of Queue.

    songQueue = Queue()

    # If there are songs in the list, add them to the queue.

    if len(songList) == 0:

        print("There are no requested songs.")

    else:

        for song in songList:

            songQueue.enqueue(song)


    # Loop through the queue and dequeu the elements.

    while len(songQueue) != 0:

        print(songQueue.dequeue())
```

Now let's make calls to our methods with the data:

```
songList = ["Welcome to Paradise", "Smells Like Teen Spirit", "Come as You Are", "Blackbird", "On the Wing", "Nothing Else Matters"]

songList2 = ["Super Bon Bon", "For Once In My Life", "Start the Machine"]

songList3 = []

queueDemo(songList)

queueDemo(songList2)

queueDemo(songList3)

```

Now that you have had some practice, here is a problem to solve on your own.

You are given two lists of current customer names for two adjacent fast-food restaurants. One list per restaurant. You are tasked with making sure that orders get delivered to the most recent customers first for each restaurant. Display each name in the correct order. When the queue is finished, send a message to the user that all the customers of that restaurant have been served. How would you solve this using a queue?

Here are the lists of names:



```
nameList1 = ["John", "Jeremy", "Melinda", "Greg", "Bethony", "Mark"]

nameList2 = ["Jim", "Jared", "Logan", "Mike", "Melvin"]
```


Here is a link to the solution.

[Queue Example Solution](Queue%20Code%20Example%20Solution.docx)
