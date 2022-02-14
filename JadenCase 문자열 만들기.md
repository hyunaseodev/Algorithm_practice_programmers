```java
//JadenCase 문자열 만들기
class Solution {
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		String s = "3people unFollowed me";
		
		System.out.println(sol.solution(s));
	}
	
	public String solution(String s) {
		String answer = "";
		
		String[] str_arr = s.split("");
		
		for(int i = 0; i < str_arr.length; i++) {
			if(i == 0) {
				str_arr[i] = str_arr[i].toUpperCase();
			}
			else {
				if(str_arr[i-1].equals(" ")) str_arr[i] = str_arr[i].toUpperCase();
				else str_arr[i] = str_arr[i].toLowerCase();
			}
			
			answer += str_arr[i];
		}
		
        return answer;
    }
}
```