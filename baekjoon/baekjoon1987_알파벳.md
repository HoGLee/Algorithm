## Baekjoon algorithm 1987 (알파벳)

1987 problem

```java
//https://www.acmicpc.net/problem/1987
import java.util.*;

class Solution {
	static char[][] board = new char[20][20];
	static boolean[] check = new boolean[30];
	static int answer = 0;
	static int cnt = 0;
	static int R;
	static int C;
	static void search(int row, int col) {
		if(row >= R || col >= C || row < 0 || col < 0 || check[board[row][col]-'A'] == true) {return;}
		check[board[row][col]-'A'] = true;
		cnt++;
		search(row+1,col);
		search(row,col+1);
		search(row-1,col);
		search(row,col-1);
		answer = Math.max(answer, cnt);
		cnt--;
		check[board[row][col]-'A'] = false;
	}
    public static void main(String[] args) {
    	Scanner sc = new Scanner(System.in);
    	R = sc.nextInt();
    	C = sc.nextInt();
    	sc.nextLine();
    	for(int i = 0; i < R; i++ ) {
    		String str = sc.nextLine();
    		for(int j = 0; j < C; j++) {
    			board[i][j] = str.charAt(j);
    		}
    	}
    	sc.close();
    	Arrays.fill(check, false);
    	search(0,0);
    	System.out.println(answer);
    }
}

```

