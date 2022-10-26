# code100
package practice;

import java.util.Arrays;
import java.util.Scanner;

public class isAnagram {
	
	static boolean isAnagram(String a, String b) {
		boolean flag = true;
		int arr[] = new int[256];
		for(char c: a.toCharArray()) {
			int index = (int) c;
			arr[index]++;
		}
		
		for(char c: b.toCharArray()) {
			int index = (int)c;
			arr[index]--;
		}
		
		for(int i=0; i<256; i++) {
			if(arr[i] != 0) {
				flag = false;
				break;
			}
		}
		
		return flag;
	}

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		String a = sc.next();
		String b = sc.next();
		a = a.toLowerCase();
		b = b.toLowerCase();
		boolean ans = isAnagram(a,b);
		System.out.println((ans)? "Angram" : "Not Anagram");

	}

}
