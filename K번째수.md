```java
//K번째수
import java.util.*;

class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		int[] array = {1, 5, 2, 6, 3, 7, 4};
		int[][] commands = {{2, 5, 3}, {4, 4, 1}, {1, 7, 3}};
		
		System.out.println(sol.solution(array, commands));
	}
	
	public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];
        
        //임시 배열 선언
        int[] tmp;
        
//        command[] 2번째 원소 값 추출해서 answer 배열에 넣기
        for(int i=0; i<commands.length; i++) {
//        	array 배열을 command[] 0번째 원소값부터 1번째 원소의 값까지
//        	임시 배열이 참조
        	tmp = Arrays.copyOfRange(array, commands[i][0]-1, commands[i][1]);
//        	임시 배열 정렬
        	Arrays.sort(tmp);
        	answer[i] = tmp[commands[i][2]-1];
        }
        return answer;
    }
}
```