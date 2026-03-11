### Circular Linked List using Singly Linked List (SLL)

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct dll {
    int data;
    struct dll *link;
} node;

node *head = NULL;

node *memalloc(int d) {
    node *new = (node *)malloc(sizeof(node));
    if (new == NULL) {
        printf("Memory not allocated\n");
        exit(1);
    }
    new->data = d;
    new->link = head;
    return new;
}

void insertfront(int d) {
    node *new = memalloc(d);
    if (head == NULL) {
        head = new;
        return;
    }
    new->link = head;
    head = new;
}

void createacll() {
    node *temp = head;
    while (temp->link != NULL) {
        temp = temp->link;
    }
    temp->link = head;
}

void display() {
    node *temp = head;
    printf("The list Elements are: ");
    do {
        printf("%d ", temp->data);
        temp = temp->link;
    } while (temp != head);
    printf("\n");
}

int main() {
    int d, n;
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter the element: ");
        scanf("%d", &d);
        insertfront(d);
    }
    createacll();
    display();
}
```

### Circular Linked List using Doubly Linked List (DLL)

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct dll {
    int data;
    struct dll *plink;
    struct dll *nlink;
} node;

node *head = NULL;

node *memalloc(int d) {
    node *new = (node *)malloc(sizeof(node));
    if (new == NULL) {
        printf("Memory not allocated\n");
        exit(1);
    }
    new->data = d;
    new->plink = head;
    new->nlink = head;
    return new;
}

void insertfront(int d) {
    node *new = memalloc(d);
    if (head == NULL) {
        head = new;
        return;
    }
    new->nlink = head;
    head->plink = new;
    head = new;
}

void createacll() {
    node *temp = head;
    while (temp->nlink != NULL) {
        temp = temp->nlink;
    }
    temp->nlink = head;
    head->plink = temp;
}

void display() {
    node *temp = head;
    printf("The list Elements are: ");
    do {
        printf("%d ", temp->data);
        temp = temp->nlink;
    } while (temp != head);
    printf("\n");
}

int main() {
    int d, n;
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter the element: ");
        scanf("%d", &d);
        insertfront(d);
    }
    createacll();
    display();
}
```
