# linkedlistinsert

// Online C++ compiler to run C++ program online
#include<iostream>

using namespace std;
class node{
   public:
   int data;
   node* next;
   node(int data){
    this->data=data;
    this->next=NULL;
   }
};
 
void insertAthead(node* &head , int d){
    node*temp = new node(d);
    temp->next=head;
    head=temp;
} 

void insertAttail(node* &tail , int d){
    node*temp = new node(d);
    tail->next=temp;
    tail=temp;
}

void insertatpos( node* &head , int pos , int d){
    node *temp = head;
    int count =1;
    while(count<pos-1){
        temp=temp->next;
        count++;
    }
    
    node* newnode= new node(d);
    newnode->next = temp ->next;
    temp->next=newnode;
}

void print(node * &head){
    node*temp=head;
    while(temp!=NULL){
        cout<<temp->data<<"->";
        temp = temp->next;
    }
    cout<<endl;
    
}
 
int main(){
    node* n1= new node(10);
    node* head=n1;
    
     print(head);
    //cout<<n1->next<<endl;
    insertAthead(head, 9);
    print(head);
    
    insertAthead(head, 5);
    print(head);
    
    node*tail=n1;
    insertAttail(tail , 15);
    print(head);
    
    insertatpos(head, 4 , 11);
    print(head);
    
} 
