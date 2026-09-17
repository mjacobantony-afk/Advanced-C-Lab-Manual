EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

```c
#include <stdio.h>

#define SIZE 10

int stack[SIZE];
int top = -1;

void push(int x)
{
    if (top == SIZE - 1)
    {
        printf("Stack overflow\n");
        return;
    }
    stack[++top] = x;
}

void display()
{
    int i;
    if (top == -1)
    {
        printf("Stack is empty\n");
        return;
    }
    printf("Stack elements: ");
    for (i = top; i >= 0; i--)
        printf("%d ", stack[i]);
    printf("\n");
}

int main()
{
    push(10);
    push(20);
    push(30);
    push(40);

    display();

    return 0;
}
```

Output:

```
Stack elements: 40 30 20 10
```



Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

```c
#include <stdio.h>

#define SIZE 10

int size = SIZE;
int top = -1;
float stack[SIZE];

void push(float x)
{
    if (top == size - 1)
    {
        printf("Stack overflow\n");
        return;
    }
    stack[++top] = x;
    printf("%.2f pushed into stack\n", x);
}

void display()
{
    int i;
    printf("Stack elements: ");
    for (i = top; i >= 0; i--)
        printf("%.2f ", stack[i]);
    printf("\n");
}

int main()
{
    float val;

    printf("Enter element to push: ");
    scanf("%f", &val);
    push(val);

    printf("Enter element to push: ");
    scanf("%f", &val);
    push(val);

    display();

    return 0;
}
```

Output:

```
Enter element to push: 15.5
15.50 pushed into stack
Enter element to push: 22.3
22.30 pushed into stack
Stack elements: 22.30 15.50
```




Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

```c
#include <stdio.h>

#define SIZE 10

int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int x)
{
    if (rear == SIZE - 1)
    {
        printf("Queue overflow\n");
        return;
    }
    if (front == -1)
        front = 0;
    queue[++rear] = x;
}

void display()
{
    int i;
    if (front == -1 || front > rear)
    {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    for (i = front; i <= rear; i++)
        printf("%d ", queue[i]);
    printf("\n");
}

int main()
{
    enqueue(5);
    enqueue(15);
    enqueue(25);
    enqueue(35);

    display();

    return 0;
}
```

Output:

```
Queue elements: 5 15 25 35
```


Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

```c
#include <stdio.h>

#define SIZE 10

float queue[SIZE];
int front = -1, rear = -1, size = SIZE;

void enqueue(float x)
{
    if (rear == size - 1)
    {
        printf("Queue overflow\n");
        return;
    }
    if (front == -1)
        front = 0;
    queue[++rear] = x;
    printf("%.2f inserted into queue\n", x);
}

void display()
{
    int i;
    printf("Queue elements: ");
    for (i = front; i <= rear; i++)
        printf("%.2f ", queue[i]);
    printf("\n");
}

int main()
{
    float val;

    printf("Enter element to insert: ");
    scanf("%f", &val);
    enqueue(val);

    printf("Enter element to insert: ");
    scanf("%f", &val);
    enqueue(val);

    display();

    return 0;
}
```

Output:

```
Enter element to insert: 10.5
10.50 inserted into queue
Enter element to insert: 20.75
20.75 inserted into queue
Queue elements: 10.50 20.75
```

Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

```c
#include <stdio.h>

#define SIZE 10

int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int x)
{
    if (rear == SIZE - 1)
    {
        printf("Queue overflow\n");
        return;
    }
    if (front == -1)
        front = 0;
    queue[++rear] = x;
}

void dequeue()
{
    if (front == -1)
    {
        printf("Queue is empty\n");
        return;
    }

    printf("Deleted element: %d\n", queue[front]);
    front++;

    if (front > rear)
        front = rear = -1;
}

void display()
{
    int i;
    if (front == -1)
    {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    for (i = front; i <= rear; i++)
        printf("%d ", queue[i]);
    printf("\n");
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();
    dequeue();
    display();

    return 0;
}
```

Output:

```
Queue elements: 10 20 30
Deleted element: 10
Queue elements: 20 30
```


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
