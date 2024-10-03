#TY BCS

Operating System - I

Solved Practical Slips

2022-23

Slip 1_1 / Slip 11_1:Write the simulation program to implement demand paging and show the

page scheduling and total number of page faults according to the LFU page replacement

algorithm. Assume the memory of n frames.

Reference String : 3,4,5,4,3,4,7,2,4,5,6,7,2,4,6

#include<stdio.h>

#define MAX 20

int frames[MAX],ref[MAX],mem[MAX][MAX],faults,

sp,m,n,count[MAX];

void accept()

{

int i;

printf("Enter no.of frames:");

scanf("%d", &n);

printf("Enter no.of references:");

scanf("%d", &m);

printf("Enter reference string:\n");

for(i=0;i<m;i++)

{

printf("[%d]=",i);

scanf("%d",&ref[i]);

}

}

void disp()

{

int i,j;

for(i=0;i<m;i++)

printf("%3d",ref[i]);

printf("\n\n");

for(i=0;i<n;i++)

 {

for(j=0;j<m;j++)

{

if(mem[i][j])

printf("%3d",mem[i][j]);

else

printf(" ");

}

printf("\n");

}

printf("Total Page Faults: %d\n",faults);

}

int search(int pno)

{

int i;

for(i=0;i<n;i++)

{

if(frames[i]==pno)

return i;

}

return -1;

}

int get_lfu(int sp)

{

int i,min_i,min=9999;
