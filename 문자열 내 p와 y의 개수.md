```java
import java.util.*;

//문자열 내 p와 y의 개수
class Solution {
	public static void main(String args[]) {
		String s = "pPoooyY";
		
		s = s.toLowerCase();
		
		int pCnt = 0;
		int yCnt = 0;
		
		for(int i = 0; i < s.length(); i++) {
			if(s.charAt(i) == 'p') {
				pCnt++;
			}
			else if(s.charAt(i) == 'y') {
				yCnt++;
			}
		}
		
		boolean answer = true;
		
		if(pCnt != yCnt) answer = false;
		System.out.println(s);
		System.out.println(sb);
		
	}
}
```