# string
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {
	public static String output1;
	public static void JumbleWords(String input1, int input2) {
        String arr[]=input1.split(" ");
        int i,j;
        String even="",odd="",res="";
        for(i=0;i<arr.length;i++){
            String str=arr[i];even="";odd="";
            for(j=0;j<str.length();j++)
            {
                if(j%2==0)
                    even+=str.charAt(j);
                else
                    odd+=str.charAt(j);
            }
            if(input2==1){
                StringBuffer sb=new StringBuffer(even);
                String r=sb.reverse().toString();
                res=res+odd+r;
            }
            else if(input2==2)
            {
                res=res+odd+even;
            }
            else
            {
                String a=even+odd;
                for(j=0;j<a.length();j++)
                {
                    if(a.charAt(j)=='A'||a.charAt(j)=='E'||a.charAt(j)=='I'||a.charAt(j)=='O'||a.charAt(j)=='U')
                        res+=a.charAt(j);
                    else
                        res=res+(char)(a.charAt(j)+32);
                }
            }
            res+=" ";
        }
          output1=res;  
    }    

 public static void main(String[] args) {
      Scanner in = new Scanner(System.in);
      String input1 = in.nextLine();
      int input2=in.nextInt();
      JumbleWords(input1,input2);
      System.out.println(output1);
    }
}
