## BaekJoon  algorithm(리모컨)

```java
//https://www.acmicpc.net/problem/1107
package ex01;

import java.util.Scanner;

public class Remote {
	static boolean[] broken = new boolean[10];
	static int possible(int c) {	// c의 각 자리수 검사 
		int len = 0;
		if(c == 0) {
			return broken[0]? 0 : 1;
		}
		while(c > 0) {
			if(broken[c%10])	return 0;
			len++;
			c /= 10;
		}
		return len;
	}
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt();
		int M = sc.nextInt();
		int tmp;
		for(int i = 0; i < 10; i++) {broken[i] = false;}
		if(M > 0) {
			for(int i = 0; i < M; i++) {
				broken[sc.nextInt()] = true;	// 망가진 버튼 true
			}
		}
		int ans =  Math.abs(100-N);	// only plus or minus count
		for(int i = 0; i < 1000001; i++) {
			int c = i;	// 이동할 채널 c
			int len = possible(c);
			if(len > 0) {
				tmp = len + Math.abs(N-c);
				if(ans > tmp) {
					ans = tmp;
				}
			}
		}
		System.out.println(ans);
	}
}
```

