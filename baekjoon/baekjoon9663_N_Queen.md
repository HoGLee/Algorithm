## BaekJoon algorithm(N-Queen)

9663 problem

```java
//https://www.acmicpc.net/problem/9663
import java.util.Arrays;
import java.util.Scanner;

public class Solution {
	static int N;
	static int[][] map = new int[15][15];
	static boolean[] check_col = new boolean[15];
	static boolean[] check_digit_right = new boolean[30];
	static boolean[] check_digit_left = new boolean[30];
	static int calc(int row){
		if(row == N) {
			return 1;
		}
		int cnt = 0;
		for(int col = 0; col < N; col++) {
			if(check_col[col] == false && check_digit_right[row+col] == false && check_digit_left[row-col+N-1] == false) {
				check_col[col] = true;
				check_digit_right[row+col] = true;
				check_digit_left[row-col+N-1] = true;
				cnt += calc(row+1);
				check_col[col] = false;
				check_digit_right[row+col] = false;
				check_digit_left[row-col+N-1] = false;
			}
		}
		return cnt;
	}
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		N = sc.nextInt();
		Arrays.fill(check_col, false);
		Arrays.fill(check_digit_left, false);
		Arrays.fill(check_digit_right, false);
		System.out.println(calc(0));
	}

}

```

