# coding_practice -> facebook interview problem of coins
package javaapplication1;

import java.io.*; 
import java.lang.Math;
class facebook_question 
{ 
  
    static int func(int []arr, int i, int j, int sum)  
    {  
        if (j == i + 1)  
            return Math.max(arr[i], arr[j]);  
      
        
        return Math.max((sum - func(arr, i + 1, j, sum - arr[i])),  
                (sum - func(arr, i, j - 1, sum - arr[j])));  
    }  
      
    static int solution(int[] arr, int n)  
    {  
        int sum = 0;  
        for(int i = 0; i < n; i++) 
        { 
            sum += arr[i]; 
        } 
  
        return func(arr, 0, n - 1, sum);  
    }  
      
      
    static public void main (String[] args) 
    {  
        int []arr1 = { 10, 35, 23, 17 };  
        int n = arr1.length;  
        System.out.println(solution(arr1, n));  
      
        int []arr2 = { 8,5,12,13,5,9};  
        n = arr2.length;  
        System.out.println(solution(arr2, n));  
      
        int []arr3 = { 10, 20, 2, 21, 10 };  
        n = arr3.length ;  
        System.out.println(solution(arr3, n));  
    
        int []arr4 = { 18,5,12,23,15,19};  
        n = arr4.length ;  
        System.out.println(solution(arr4, n));  
    
    
    }
} 
