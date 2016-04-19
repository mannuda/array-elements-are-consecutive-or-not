#include <stdio.h>
#define MAX 30


int segregate(int a[], int l)
{
	int c=0;
	for(int i=0;i<l;i++)
	{
		if(a[i]==0) c++;
	}
	for(int i=0;i<c;i++)
	{
		a[i]=0;
	}
	for(int i=c;i<l;i++)
	{
		a[i]=1;
	}
	return 0;
}
display(int a[],int l){
	for(int i=0;i<l;i++)
	{
		printf("%d ",a[i]);
	}
}


int segregate2(int a[], int l)
{
	int left,right;
	for(left=0,right=l;left<right;left++,right--)
	{
		while(a[left]==0 && left<right)
		{
			left++;
		}
		while(a[right]==1 && left <right)
		{
			right--;
		}
		if(left<right)
		{
			int temp=a[left];
			a[left]=a[right];
			a[right]=temp;
		}
	}
}
int main(void) {

	int a[]={1,0,1,0,1,0,0,0,0,1,1,1,1,0,1,0,1};
	int l=sizeof(a)/sizeof(int);

    	segregate(a,l);
  
	display(a,l);
	return 0;
}
