# Data_structure_QuickSort

#include<stdio.h>
//int a[100];
void printArray(int* a , int n){
    for(int i=0; i<n ; i++){
        printf("%d " , a[i]);
    }
    printf("\n");
}
int partition(int a[] ,int low ,int high){
    printArray(a,9);
    int pivot=a[low];
    int i=low+1;
    int j=high;
    int temp;
    do{
    while(a[i]<=pivot){
        i++;
    }
    while(a[j]>pivot){
        j--;
    }
    if(i<j){
        // swap A[i] and A[j]
        temp = a[i];
        a[i] = a[j];
        a[j] = temp;

    }
    }while(i<j);
    // swap A[low] and A[j]
    temp = a[low];// swap pivot with A[j]
    a[low] = a[j];
    a[j] = temp;
    return j;
}
void quickSort(int a[] , int low , int high){
    int partitionIndex; // index of pivot after partition 
    if (low<high){
    partitionIndex = partition(a , low , high);
    quickSort(a , low , partitionIndex-1);// sort left subarray
    quickSort(a , partitionIndex+1, high);// sort right subarray
    }
}
int main(){
    /*int num;
     printf("Enter the total number of num : ");
     scanf(" %d " , &num);
     printf("Enter the numbers: \n");
     for(int i=1 ; i<= num ; i++){
        scanf("%d",&a[i]);
     }*/
    int a[] = {23,45,56,43,12,32,89,87,5};
    int num =9;
    printArray(a,num);
    quickSort(a, 0, num-1);
    printArray(a , num);
    return 0 ;
}
