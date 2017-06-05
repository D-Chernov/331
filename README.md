#include "stdafx.h"
#include "stdio.h"
#include "stdlib.h"

   int size; //  размер массива
   int *arr; // указатель для выделения памяти под массив

void gener()
{
	printf("n = ");			// Ввод количества элементов массива
    scanf("%d", &size);
    if (size <= 0) 
	{
        // Размер масива должен быть положитлеьным
        printf("Invalid size\n");
    }
	arr = (int *)malloc(size * sizeof(int));// выделение памяти под массив
    for (int i = 0; i < size; i++)  // заполнение массива
	{
		printf("arr[%d] = ", i);
    	scanf("%d", &arr[i]);
    	printf("\n");
    }
}
	
void sort()
{
    int temp; // временная переменная для обмена элементов местами
    for (int i = 0; i < size - 1; i++) // Сортировка массива пузырьком
	{
        for (int j = 0; j < size - i - 1; j++) 
		{
            if (arr[j] > arr[j + 1]) 
			{
                // меняем элементы местами
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}
	
	
void output()	// Вывод отсортированного массива на экран
{ 
    for (int i = 0; i < size; i++) 
	{
    	printf("%d ", arr[i]);
    }
    printf("\n");
}
	
int main()
{
    gener();
    sort();
    output();
	system("pause");
	free(arr);
    return 0;
}
