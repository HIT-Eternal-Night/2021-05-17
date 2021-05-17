# 2021-05-17
复习课上PPT内容，力求牢固掌握

1、动态内存分配的用途之一是实现动态数组，把p当作数组名，像使用普通一维数组一样使用一维动态数组。
2、指向函数的指针变量：函数指针。编译器将不带（）的函数名解释为该函数在内存中的入口地址
#include<stdio.h>

void Fun(int x, int y, int (*f)(int, int));
int Max(int x, int y);

int main(int argc,char const *argv[])
{
	int a,b;
	scanf("%d,%d",&a,&b);
	Fun(a,b,Max);
	return 0;
}

void Fun(int x, int y, int (*f)(int, int))
{
	int result;
	result = (*f)(x,y);
	printf("%d\n",result);
}

int Max(int x, int y)
{
	printf("Max = ");
	return x>y ? x : y;
}
传不同的地址调用不同的函数，通过函数指针调用的函数——回调函数
问：什么时候需要指针指向代码？
答：使用函数指针编写一个通用的排序函数
如将
SelectionSort(a,n,Ascending);
SelectionSort(a,n,Dscending);
合并成为一个通用函数
void SelectionSort(int a[], int n, int (*compare)(int,int));

3、指针小结：
·指针是一种特殊的可以保存地址值的数据类型
·指针不是地址，指针变量的值是一个地址
·永远清楚指针指向了哪里
