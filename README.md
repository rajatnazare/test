1.PROGRAM TO FIND AREA & CIRCUMFERENCE OF CIRCLE
#include <stdio.h>
int main()
{
int r;
float area,circum,pi=3.142;
printf("enter a radius of circle\n");
scanf("%d",&r);
area=pi*r*r;
circum=2*pi*r;
printf("area of circle %g\n",area);
printf("circumference of circle %g\n",circum);
return 0;
}


2.PROGRAM TO EXPLAIN ALL DATATYPES INCLUDING SIGNED & UNSIGNED..
#include <stdio.h>
int main()
{
printf("size of integer %d\n",sizeof(int));
printf("size of float %d\n",sizeof(float));
printf("size of character %d\n",sizeof(char));
printf("size of double %d\n",sizeof(double));
printf("size of long double %d\n",sizeof(long double));
printf("size of short int %d\n",sizeof(short int));
printf("size of long int %d\n",sizeof(long int));
printf("size of unsigned int %d\n",sizeof(unsigned int));
printf("size of signed int %d\n",sizeof(signed int));
return 0;
}

4.PROGRAM TO EXPLIAN ALL STORAGE CLASSES SCOPE
Auto: It is default storage class for all the variable declared inside a function or block.
     Scope of auto storage class is with in block
#include <stdio.h>
int main()
{
 int a=10; //auto storage 
 printf("%d",a);
 return 0;
}
STATIC:  It can be used Globally or locally. Static variables are initialized once , it will be existing till the end of program. Scope static is within a block.

#include <stdio.h>
void fun();
void main()
{
    fun();
    fun();
    fun();
}
void fun()
{
    int a=1;// auto
    static int b=1; //static
    printf("%d %d\n",a,b);
    a++;
    b++;
}
REGISTER:  Register variable has same functionality as that of auto variables only difference is that compiler tries to store register variable in register of micro processor.
#include<stdio.h>
int main()
{
register int a=10;
printf(“%d”,a);
return 0;
}
EXTERN: extern is short name for a external. Used when a particular file needs to access variable from another file.
#include <stdio.h>  
int main()  
{  
extern int a;    
printf("%d",a);  
}  
int a = 20;




3.PROGRAM TO EXPLAIN ALL OPEARTORS USING DIFFERENT DATATYPES..
#include <stdio.h>  
int main()  
{ 
    int a=10,b=5,c=0,d=1;;
    // Arithmatic opeartor
    printf("addition=%d\n",a+b);
    printf("subtraction=%d\n",a-b);
    printf("multiplication=%d\n",a*b);
    printf("division=%d\n",a/b);
    printf("modulus=%d\n",a%b);
    //Relational opeartor
    printf("%d\n",a<b);
    printf("%d\n",a>b);
    printf("%d\n",a==b);
    printf("%d\n",a!=b);
    //increment and decrement operator
    printf("post increment %d\n",a++);
    printf("post decrement %d\n",a--);
    printf("pre increment %d\n",++a);
    printf("pre decrement %d\n",--a);
    // bitwise operator
    printf("and operator=%d\n",c&d);
    printf("or opeartor=%d\n",c|d);
    printf("xor opeartor=%d\n",c^d);
    
    return 0;
}

5.CREATE A LIST WITH 3 NODES HAVING INT DATA IN SINGLE LINKED LIST DATA: 100,200,300

#include<stdio.h>
#include<stdlib.h>
typedef struct sll
{
    int data;
    struct sll *link;
}node;
 node *first=NULL;
 node *last=NULL;
 
 void create(int ele)
 {
     node *ptr=(node*)malloc(sizeof(node));
     ptr->data=ele;
     ptr->link=NULL;
     if (first==NULL)
     {
         first=ptr;
         last=ptr;
     }
     else
     {
         last->link=ptr;
         last=ptr;
         
     }
 }
void dispaly()
{
    node *temp=first;
    while(temp!=NULL)
    {
        printf("%d\n",temp->data);
        temp=temp->link;
    }
}

int main()
{
    create(100);
    create(200);
    create(300);
    dispaly();
    
}

6.CREATE A CIRCULAR LL WITH 5 NODES HAVING CHAR DATA-VOWELS-a,e,i,o,u

#include <stdio.h>
#include<stdlib.h>
struct cll              //circular linked list
{
    char ch;
    struct cll *next;
};
typedef struct cll node;
node *first = NULL, *last = NULL;
void create_node(char vowels)
{
    node *new = (node *)malloc(sizeof(node));
    if(first == NULL)
    {
        new -> ch = vowels;
        new -> next = first;
        first = last = new;
    }
    else
    {
        new -> ch = vowels;
        new -> next = first;
        last -> next = new;
        last = new;
    }
}
void display()
{
    node *temp= first;
    do
    {
     printf("%d\n",temp -> ch);
     temp = temp -> next;
    }
    while(temp!=first);
}
int main()
{
    
    create_node('a');//97
    create_node('e');//101
    create_node('i');//105
    create_node('o');//111
    create_node('u');//117
    create_node('A');//65
    create_node('E');//69
    create_node('I');//73
    create_node('O');//79
    create_node('U');//85
    display();
    return 0;
}
