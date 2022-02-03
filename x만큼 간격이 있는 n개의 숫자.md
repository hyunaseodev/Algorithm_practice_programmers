```java
import java.util.Arrays;

//x만큼 간격이 있는 n개의 숫자
class Solution {
	public static void main(String args[]) {
		int x = -4;
		int n = 2;
		
		long[] answer = new long[n];
		
		for(int i = 1; i <= n; i++) {
			answer[i-1] = (long) x * i;
		}
	        
		System.out.println(Arrays.toString(answer));
	}
}
```