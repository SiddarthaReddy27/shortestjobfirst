# shortestjobfirst
#include <stdio.h>
int main()
{
    int i,j,ct[3],wt[3],tat[3],bt[3],temp,sum=0,avg;
    printf("enter burst times\n");
    for(i=0;i<4;i++)
    {
        scanf("\n%d\n",&bt[i]);
    }
    for(i=0;i<4;i++)
    {
        for(j=i+1;j<4;j++)
        {
            if(bt[i]>bt[j])
            {
                temp=bt[i];
                bt[i]=bt[j];
                bt[j]=temp;
            }
        }
    }
    printf("\nafter sorting the burst times\n");
    for(i=0;i<4;i++)
    {
        printf("%d\n",bt[i]);
    }
    for(i=0;i<4;i++)
    {
        if(i==0)
            ct[0]=bt[0];
        else
            ct[i]=ct[i-1]+bt[i];
        printf("\nthe completion time of %d is %d\n",i+1,ct[i]);
    }
    for(i=0;i<4;i++)
    {
        wt[i]=ct[i]-bt[i];
        printf("\nthe waiting time of %d is %d\n",i+1,wt[i]);
    }
    for(i=0;i<4;i++)
    {
        tat[i]=wt[i]+bt[i];
        printf("\nthe waiting time of %d is %d\n",i+1,tat[i]);
    }
    for(i=0;i<4;i++)
    {
        sum=sum+tat[i];
    }
    avg=sum/4;
    printf("\navg turn around time is %d\n",tat[i]);
}
