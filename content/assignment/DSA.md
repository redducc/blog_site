---
title: "DSA Assignments"
dateString: Apr 2024
draft: false
tags: ["DSA", "assignment",]
weight: 999999
---

# DOUBLE ENDED QUEUE AT RARE
 #include <stdio.h>
 #include <stdlib.h>

 #define MAX_SIZE 100

 typedef struct {
     int data[MAX_SIZE];
     int front;
} Deque;

Deque* createDeque() {
    Deque* deque = (Deque*)malloc(sizeof(Deque));
    deque->front = -1;
    return deque;
}

int isEmpty(Deque* deque) {
    return deque->front == -1;
}

int isFull(Deque* deque) {
    return deque->front == MAX_SIZE - 1;
}

void insertFront(Deque* deque, int value) {
    if (isFull(deque)) {
        printf("Deque is full, cannot insert at front.\n");
        return;
    }

    if (isEmpty(deque)) {
        deque->front = 0;
    } else {
        for (int i = deque->front; i >= 0; i--) {
            deque->data[i + 1] = deque->data[i];
        }
        deque->front++;
    }

    deque->data[0] = value;
    printf("Inserted %d at front.\n", value);
}

int deleteFront(Deque* deque) {
    if (isEmpty(deque)) {
        printf("Deque is empty, cannot delete from front.\n");
        return -1;
    }

    int value = deque->data[deque->front];
    for (int i = 0; i < deque->front; i++) {
        deque->data[i] = deque->data[i + 1];
    }
    deque->front--;

    printf("Deleted %d from front.\n", value);
    return value;
}

void display(Deque* deque) {
    if (isEmpty(deque)) {
        printf("Deque is empty.\n");
        return;
    }

    printf("Deque elements: ");
    for (int i = 0; i <= deque->front; i++) {
        printf("%d ", deque->data[i]);
    }
    printf("\n");
}

int main() {
    Deque* deque = createDeque();

    insertFront(deque, 1);
    insertFront(deque, 2);
    insertFront(deque, 3);
    display(deque);

    deleteFront(deque);
    display(deque);

    return 0;
}

# DOUBLE ENDED QUEUE AT FRONT
 #include <stdio.h>
 #include <stdlib.h>

 #define MAX_SIZE 100

typedef struct {
    int data[MAX_SIZE];
    int front;
} Deque;

Deque* createDeque() {
    Deque* deque = (Deque*)malloc(sizeof(Deque));
    deque->front = -1;
    return deque;
}

int isEmpty(Deque* deque) {
    return deque->front == -1;
}

int isFull(Deque* deque) {
    return deque->front == MAX_SIZE - 1;
}

void insertFront(Deque* deque, int value) {
    if (isFull(deque)) {
        printf("Deque is full, cannot insert at front.\n");
        return;
    }

    if (isEmpty(deque)) {
        deque->front = 0;
    } else {
        for (int i = deque->front; i >= 0; i--) {
            deque->data[i + 1] = deque->data[i];
        }
        deque->front++;
    }

    deque->data[0] = value;
    printf("Inserted %d at front.\n", value);
}

int deleteFront(Deque* deque) {
    if (isEmpty(deque)) {
        printf("Deque is empty, cannot delete from front.\n");
        return -1;
    }

    int value = deque->data[deque->front];
    for (int i = 0; i < deque->front; i++) {
        deque->data[i] = deque->data[i + 1];
    }
    deque->front--;

    printf("Deleted %d from front.\n", value);
    return value;
}

void display(Deque* deque) {
    if (isEmpty(deque)) {
        printf("Deque is empty.\n");
        return;
    }

    printf("Deque elements: ");
    for (int i = 0; i <= deque->front; i++) {
        printf("%d ", deque->data[i]);
    }
    printf("\n");
}

int main() {
    Deque* deque = createDeque();

    insertFront(deque, 1);
    insertFront(deque, 2);
    insertFront(deque, 3);
    display(deque);

    deleteFront(deque);
    display(deque);

    return 0;
}
 
# Enqueue at rare
 #include <stdio.h>
 #include <stdlib.h>

 #define MAX_SIZE 100

// Define Queue structure
struct Queue {
    int items[MAX_SIZE];
    int front;
    int rear;
};

// Initialize queue
void initQueue(struct Queue *q) {
    q->front = -1;
    q->rear = -1;
}

// Check if queue is full
int isFull(struct Queue *q) {
    return q->rear == MAX_SIZE - 1;
}

// Check if queue is empty
int isEmpty(struct Queue *q) {
    return q->front == -1 && q->rear == -1;
}

// Enqueue function
void enqueue(struct Queue *q, int value) {
    if (isFull(q)) {
        printf("Queue is full. Cannot enqueue.\n");
        return;
    }
    if (isEmpty(q)) {
        q->front = q->rear = 0;
    } else {
        q->rear++;
    }
    q->items[q->rear] = value;
    printf("%d enqueued to the queue.\n", value);
}

int main() {
    struct Queue q;
    initQueue(&q);

    // Enqueue elements
    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);

    return 0;
}

# ENQUEUE AT FRONT
 #include <stdio.h>
 #include <stdlib.h>

 #define MAX_SIZE 100

// Structure to represent a queue
struct Queue {
    int items[MAX_SIZE];
    int front;
    int rear;
};

// Function to create a new queue
struct Queue* createQueue() {
    struct Queue* queue = (struct Queue*)malloc(sizeof(struct Queue));
    queue->front = -1;
    queue->rear = -1;
    return queue;
}

// Function to check if the queue is full
int isFull(struct Queue* queue) {
    if ((queue->front == 0 && queue->rear == MAX_SIZE - 1) || (queue->rear == (queue->front - 1) % (MAX_SIZE - 1))) {
        return 1;
    }
    return 0;
}

// Function to check if the queue is empty
int isEmpty(struct Queue* queue) {
    if (queue->front == -1) {
        return 1;
    }
    return 0;
}

// Function to add an element to the front of the queue
void enqueueFront(struct Queue* queue, int value) {
    if (isFull(queue)) {
        printf("Queue is full, cannot enqueue.\n");
    } else {
        if (queue->front == -1) {
            queue->front = 0;
            queue->rear = 0;
        } else if (queue->front == 0) {
            queue->front = MAX_SIZE - 1;
        } else {
            queue->front = (queue->front - 1) % (MAX_SIZE - 1);
        }
        queue->items[queue->front] = value;
        printf("%d enqueued to the front of the queue.\n", value);
    }
}

// Function to display the queue
void display(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty.\n");
    } else {
        int i;
        printf("Elements of the queue are: ");
        for (i = queue->front; i != queue->rear; i = (i + 1) % MAX_SIZE) {
            printf("%d ", queue->items[i]);
        }
        printf("%d\n", queue->items[i]);
    }
}

int main() {
    struct Queue* queue = createQueue();

    enqueueFront(queue, 10);
    enqueueFront(queue, 20);
    enqueueFront(queue, 30);

    display(queue);

    return 0;
}

