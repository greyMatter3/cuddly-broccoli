#include<stdio.h>
void rotate_arr(int n, int arr[n]){
  int temp;
  temp=arr[0];
  for(int i=0; i<n; i++){
    arr[i]=arr[i+1];
  }
  arr[n-1]=temp;
}

void rot_by_d(int n, int arr[n], int d){
  for(int i=0; i<d; i++){
    rotate_arr(n, arr[n]);
  }
}

void ascending_arr(int n, int arr[n]){
  int temp;
  for(int i=0; i<n; i++){
    for(int j=0; j<n; j++){
      if(arr[i]<arr[j]){
        temp=arr[i];
        arr[i]=arr[j];
        arr[j]=temp;
      }
    }
  }
}

void even_odd_rearrange(int n, int arr[n]){
  int j;
  int evenpos=n/2;
  int oddpos= n-evenpos;
  int temp_arr[n];
  for(int i=0; i<n; i++){
    temp_arr[i]=arr[i];
  }
  ascending_arr(n, temp_arr);
  j=oddpos-1;
  for(int i=0; i<n; i=i+2){
    arr[i]=temp_arr[j];
    j--;
  }
  j=oddpos;
  for(int i=1; i<n; i=i+2){
    arr[i]=temp_arr[j];
    j++;
  }
}

void pushback_zeroes(int n, int arr[n]){
  int count=0;
  for(int i=0; i<n; i++){
    if(arr[i]!=0){
      arr[count++]=arr[i];
    }
  }
  while(count<n){
    arr[count++]=0;
  }
}

int main(){
  int n=10;
  int arr[n];
  int sum_arr[n];
  for(int i=0; i<n; i++){
    sum_arr[i]=0;
  }
  for(int i=0; i<n; i++){
    scanf("%d", &arr[i]);
  }
  //ascending_arr(n, arr);
  //even_odd_rearrange(n, arr);
  pushback_zeroes(n, arr);
  for(int i=0; i<n; i++){
    printf("%d ", arr[i]);
  }
}
