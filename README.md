# Roundrobin code

#include<stdio.h>
#include<conio.h>
int main()
{
	int burst[100],arrival[100],s[100];
	int n,n1,time=6;
	int t=0;
	printf("Enter number of processor :");
	scanf("%d",&n);
	for(int i=0;i<n;i++)
	{
		printf("Enter the burst time of processor %d :",i+1);
		scanf("%d",&burst[i]);
		printf("Enter the arrival time of processor %d :",i+1);
		scanf("%d",&arrival[i]);
	}
	printf("process    Arrival_time  burst_time\n");
	for(int i=0;i<n;i++)
	{
		printf("%d          %d            %d\n",i+1,arrival[i],burst[i]);
		if(arrival[i]==0)
		{
			s[i]=i+1;
			n1=n1+1;
		}
		
	}
	for(int i=0;i<n1;i++)
	{
		printf("%d-p%d-",t,s[i]);
		for(int j=1;j<=time;j++)
		{
			if(burst[s[i]-1]>0)
			{
				t=t+1;
				burst[s[i]-1]-=1;
			}
			for(int k=0;k<n;k++)
			{
				if(arrival[k]==t)
				{
					s[n1]=k+1;
					n1=n1+1;
				}
			}
		}
		printf("%d ",t);
		if(burst[s[i]-1]!=0)
		{
			s[n1]=s[i];
			n1=n1+1;
		}
		
	}
}
