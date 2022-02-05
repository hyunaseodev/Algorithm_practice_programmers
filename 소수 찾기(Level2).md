import java.util.*;

//소수 찾기(Level2)
class Solution {
	HashSet<Integer> numberSet = new HashSet<>();
	
	public static void main(String args[]) {
		Solution sol = new Solution();
		
		String numbers = "110";
		
		System.out.println(sol.solution(numbers));
	}
	
	public int solution(String numbers) {
		int cnt = 0;
		
		//1. 모든 조합의 숫자를 만든다.
		//permutation("", numbers, set);
		recursive("", numbers);
		
		//2. 소수의 개수만 센다.
		while(numberSet.iterator().hasNext()) {
			int a = numberSet.iterator().next();
			numberSet.remove(a);
			if(a == 2) cnt++;
			if(a%2!=0 && isPrime(a)) {
				cnt++;
			}
		}
		
		//3. 소수의 개수를 반환한다.
		return cnt;
	}

	public boolean isPrime(int n) {
		if(n==0 || n==1) return false;
		
		for(int i=3; i <= (int)Math.sqrt(n); i+=2) {
			if(n%i == 0) return false;
		}
		return true;
	}
	/*
	// 방법 1 - 순열로 숫자 만들기
	public void permutation(String prefix, String str, HashSet<Integer> numberSet) {
		int str_len = str.length();
		if(!prefix.equals("")) {
			numberSet.add(Integer.valueOf(prefix));
		}
		
		for(int i = 0; i < str_len; i++) {
			permutation(prefix + str.charAt(i), str.substring(0, i) + str.substring(i+1, str_len), numberSet);
		}
	}
	*/
	//방법 2
	public void recursive(String comb, String others) {
		// 1. 현재 조합을 set에 추가한다.
		if(!comb.equals(""))
			numberSet.add(Integer.valueOf(comb));
		
		for(int i = 0; i<others.length(); i++) {
			recursive(comb + others.charAt(i), others.substring(0, i) + others.substring(i+1));
		}
	}
}