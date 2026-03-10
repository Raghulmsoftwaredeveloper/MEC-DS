```c
#include<stdio.h>
#include<stdlib.h>
typedef struct ls
{
    int data;
    struct ls *link; //self referential pntr
}node;
node *head =NULL;
node* memalloc(int d){
    node *new =(node*) malloc(sizeof(node));
    if(new==NULL)
    {
        printf("memory not allocate\n");
        exit(1);
    }
    new->data=d;
    new->link=NULL;
    return new;
}
void insertfront(int d)
{
    node *new=memalloc(d);
    if(head==NULL)
    {
        head=new;
        return;
    }
    new->link=head;
    head=new;
}
void deleteFront()
{
    if(head==NULL)
    {
        printf("list is Empty\n");
        return;
    }
    node *temp=head;
    head=head->link;
    free(temp);

}
void deleteend()
{
    if(head==NULL)
    {
        printf("list is Empty\n");
        return;
    }
    node* temp=head;
    node* prev=NULL;
    while(temp->link!=NULL)
    {
        prev=temp;
        temp=temp->link;
    }
    prev->link=NULL;
    free(temp);
}

int countlist(){
    int count = 0;
    node *temp = head;
    while(temp !=NULL){
        temp = temp->link;
        count++;
    }
    printf("The Count of List is %d\n",count);
    return count;
}
void insertAtPosition(int d){
    int pos;
    int count = countlist();

    if(count == 0){
        printf("List is empty\n");
        printf("Adding new node\n");
        insertfront(d);
        return;
    }
    printf("Enter the position between 0 - %d: ", count);
    scanf("%d", &pos);
    if(pos < 0 || pos > count){
        printf("Invalid position. Position out of bounds.\n");
        return;
    }
    if(pos == 0){
        insertfront(d);
        return;
    }
    if(pos == count){
        insertend(d);
        return;
    }

    node *new = memalloc(d);
    node *temp = head;

    for(int i = 1; i < pos; i++){
        temp = temp->link;
    }
    new->link = temp->link;
    temp->link = new;
}
void insertend(int d)
{
    node* new=memalloc(d);
    if(head==NULL)
    {
        head=new;
        return;
    }
    node *temp=head;
    while(temp->link!=NULL)
    {
        temp=temp->link;
    }
    temp->link=new;
}
void display()
{
    printf("The List of Elements are : ");
    if(head==NULL)
    {
        printf("No elements in List\n");
        return;
    }
    node *temp=head;
    while(temp!=NULL)
    {
        printf("%d => ",temp->data);
        temp=temp->link;
    }
    printf("\n");
}
int main()
{
   insertfront(30);
   insertfront(20);
   insertfront(10);
    insertend(40);
    display();
    deleteend();
    display();
    insertAtPosition(15);

    display();

    return 0;
}
```
