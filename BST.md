```c
#include <stdio.h>
#include <stdlib.h>
typedef struct BST {
    int data;
    struct BST *left;
    struct BST *right;
} node;

node *root = NULL;

node *memalloc(int d){
    node *new = (node*) malloc(sizeof(node));
    if(new == NULL){
        printf("Memory not allocated \n");
        exit(1);
    }
    new->data = d;
    new->left = NULL;
    new->right = NULL;
    return new;
}

void insert(int d){
    node *new = memalloc(d);
    if(root == NULL){
        root = new;
        return;
    }
    node *temp = root, *parent = NULL;
    while(temp != NULL){
        if(d > temp->data) {
            parent = temp;
            temp = temp->right;
        }
        else if(d < temp->data){
            parent = temp;
            temp = temp->left;
        }
        else {
            printf("Duplicates are not allowed\n");
            return;
        }
    }
    if (d > parent->data){
        parent->right = new;
    } else {
        parent->left = new;
    }
}
void inorder(node *temp) {
    if (temp == NULL) return;
    inorder(temp->left);
    printf("%d ", temp->data);
    inorder(temp->right);
}
void preorder(node *temp) {
    if (temp == NULL) return;
    printf("%d ", temp->data);
    preorder(temp->left);
    preorder(temp->right);
}

void postorder(node *temp) {
    if (temp == NULL) return;
    postorder(temp->left);
    postorder(temp->right);
    printf("%d ", temp->data);
}

int main(){
    insert(17);
    insert(5);
    insert(32);
    insert(15);
    insert(8);
    insert(11);
    insert(20);
    insert(60);
    insert(22);
    insert(12);

    printf("Inorder: ");
    inorder(root);
    printf("\nPreorder: ");
    preorder(root);
    printf("\nPostorder: ");
    postorder(root);

    return 0;
}
```
