# Hackerrank-daigonal-difference-
//this is solution of of hackerrank problem of daigonal differnce 

import java.util.*;
public class main {
    public static int diagonals( int matrix[][]) {
        int diagonal2=0;
        for(int i=0;i<matrix.length;i++) {
        for(int j =0;j<matrix.length;j++) {
            if(i + j==matrix.length-1) {
                diagonal2+=matrix[i][j];
                
            }
        }
        }
         int diagonal1=0;
    
    for(int i=0;i<matrix.length;i++) {
        
            diagonal1 += matrix[i][i];
        
    }
    if(diagonal1>=diagonal2) {
        int x = diagonal1 - diagonal2;
        return x;
    }else {
        int x = diagonal2 - diagonal1;
        return x;
    }
    
    }
public static void  main(String args[]){
    Scanner sc = new Scanner(System.in) ;
    int n =sc.nextInt();
    int[][] matrix = new int[n][n];
    int diagonal2=0;
    //input
    for(int i=0;i<n;i++) {
        for(int j =0;j<n;j++) {
            matrix[i][j] =sc.nextInt();
            
        }
    }
    int difference = diagonals(matrix);
        System.out.println(difference);
}
}
