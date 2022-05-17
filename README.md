#define _CRT_SECURE_NO_WARNINGS
#include <stdlib.h>
#include <stdio.h>

void switching(int array1[], int array2[], int temp[])
{
	int a;
	for (a = 0; a <= 10; a++)
	{
		temp[a] = array1[a];
		array1[a] = array2[a];
		array2[a] = temp[a];
	}
}


void main()
{
	int a, b;
	int array1[10] = { 1, 6, 3, 4, 1, 0, 1, 8, 0, 0 };
	int array2[10] = { 2, 6, 4, 5, 1, 3, 8, 6, 10, 2 };
	int temp[10] = { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 };

	printf("before...\n");
	for (a = 0; a < 10; a++)
	{
		printf("%d ", array1[a]);
	}

	printf("\n");
	for (a = 0; a < 10; a++)
	{
		printf("%d ", array2[a]);
	}

	printf("\nafter...\n");
	//והדפסנו אותם לפני השינוי
	switching(array1, array2, temp);
	//עד לפה החלפנו בין המערכים

	for (a = 0; a < 10; a++)
	{
		printf("%d ", array1[a]);
	}

	printf("\n");
	for (a = 0; a < 10; a++)
	{
		printf("%d ", array2[a]);
	}
	printf("\n");
	//והדפסנו אותם אחרי השינוי
	for (a = 0; a < 10; a++)
	{
		for (b = 0; b < 10; b++)
		{ 
		if (array2[a] == array1[b])
			printf(" this number is the same in both arrays ---> %d and %d\n", array2[a], array1[b]);
		else
			printf(" this numbers are diffrent in both arrays ---> %d and %d\n", array1[b], array2[a]);
		}
	}
	system("pause");
}
