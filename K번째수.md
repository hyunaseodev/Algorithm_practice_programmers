```java
//K번째수
import java.util.*;

class Solution {
	public static void main(String args[]) {
		int[] array = {1, 5, 2, 6, 3, 7, 4};
		int[][] commands = 	{{2, 5, 3}, {4, 4, 1}, {1, 7, 3}};
		int commandsLen = commands.length;
		int[] answer = new int[commandsLen];

		int idx = 0;
		for(int[] command: commands) {
			//배열 자르기
			int[] newArray = Arrays.copyOfRange(array, command[0]-1, command[1]);
			//배열 오름차순으로 정렬
			Arrays.sort(newArray);
			//배열 값 넣기
			answer[idx] = newArray[command[2]-1];
			idx++;
		}
		
		System.out.println(Arrays.toString(answer));
	}
}
```