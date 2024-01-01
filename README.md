# My_Fall_Semester_23
Here is my some of c code. I will upload all of my fall 23 c code soon.
---------------------------------------------------------------------------------------------

Task_1  -->>



#include<stdio.h>    //Formula for return & base condition for if logic;

int factorial(int n)              // formula n!=(n-1)!*n

{                        // base condition 1!=1;

  if(n==1)                  // 4!=3!*4

  {                      // 3!=2!*3

    return 1;                // 2!=1!*2

  }                      // 1!=1

  return factorial(n-1)*n;

}



int main()

{

  printf("%d\n\n",factorial(4));

  return 0;

}

------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------

Task_2  -->>



#include<stdio.h>

int fibonacci(int n)

{

  if(n <= 1)

  {

    return n;

  }

  else

  {

    return fibonacci(n-1)+fibonacci(n-2);

  }

}



int main()

{

  int result;

  result= fibonacci(10);

  printf("%d", result);



  return 0;

}

-----------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------------------------------------------

Task_3  -->>



#include<stdio.h>

int print_array(int size, int arr[], int start)

{

  if(start >= size)

  {

    return;

  }

  else

  {

    printf("%d\t", arr[start]);

  }

  print_array(size, arr, start+1);

}

int main()

{

  int array[5]={10, 15, 5, 6, 3};



  print_array(5, array, 0);



  return 0;

}

-------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------

Task_5  -->>



#include<stdio.h>

int power(int n, int p)           // formula x^p=x^(p-1)*x

{                      // base condition 2^0=1

  if(p==0)                // 2^3=2^2*2

  {                    // 2^2=2^1*2

    return 1;              // 2^1=2^0*2

  }                    // 2^0=1

  return power(n, p-1)*n;

}



int main()

{

  printf("%d\n",power(5,4));



  return 0;

}

-----------------------------------------------------------------------------------------

						Searching And Sorting

-----------------------------------------------------------------------------------------

1. Selection sort -->

#include<stdio.h>

int main()

{

  int n = 5;

  int arr[5] = {7, 10, 6, 5, 15};

  int i, j, min;



  printf("Our original array is: \n");

  for(i=0; i<n; i++)

  {

    printf("%d\t",arr[i]);

  }



  for (i = 0; i < n - 1; i++)

  {

    min = i;

    for (j=i+1; j<n; j++)

    {

      if (arr[j] < arr[min])

      {

        min = j;

      }

    }

    int temp = arr[min];

    arr[min] = arr[i];

    arr[i] = temp;

  }



  printf("\nOur sorted array is: \n");

  for (i = 0; i < n; i++)

  {

    printf("%d\t", arr[i]);

  }



  printf("\n\n");

  return 0;

}

-----------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------

2. Insertion sort  -->>

#include<stdio.h>

void i_sort(int array[], int size)   //void type function create

{

  if(size<=0)             //base condition

  {

    return;             //return for if there is no or 1 element in array

  }

  i_sort(array, size-1);       //recursion called

  int last=array[size-1];       //declare last index of array

  int j=size-2;            //declare one index lower than last

  while(j>=0 && array[j]>last)    //comparing last index with its lower index

  {

    array[j+1]=array[j];      //if last index value lower than its lower index, last index value will change

    j--;              //decreasing j value so all the elements we can check.

  }

  array[j+1]=last;          //define array[j+1] as last index

}



int main()

{

  int array[5]={5, 3, 1, 6, 4};    //declare an array

  i_sort(array, 5);          //call the function

  printf("Our sorted array is: \n");

  for(int i=0; i<5; i++)       // for loop for printing the array

  {

    printf("%d\t", array[i]);

  }



  printf("\n\n");



  return 0;

}

-------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------

3. Binary Search -->>

#include<stdio.h>

int b_Search (int arr [], int target, int left, int right)

{

  if (left > right)                        // Check if the left index is greater than the right index

  {

    return -1;                         // Return -1 if the target is not found

  }



  int mid = (left + right) / 2;                  // Calculate the middle index



  if (target == arr [mid])                    // Compare the target value with the element at the middle index

  {

    return mid;                         // Return the middle index as the position of the target

  }

  else if (target < arr [mid])

  {

    return b_Search (arr, target, left, mid - 1);        // Call the function recursively with the left half of the array

  }

  else

  {

    return b_Search (arr, target, mid + 1, right);       // Call the function recursively with the right half of the array

  }

}



int main()

{

  int array[6]= {5, 10, 2, 6, 8, 4};               //declare an array

  int size=6;                           //initialize the size

  int right=size-1;                        //initialize right index

  int left=size-size;                       //initialize left index

  int target=2;                          //define target value

  int result=b_Search(array, target, left, right);        //call function in result so that we can print it easily



  printf("%d\n\n", result);                    //printing





  return 0;

}

-------------------------------------------------------------------------------------------------

