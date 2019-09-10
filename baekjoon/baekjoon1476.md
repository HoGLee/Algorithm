## BaekJoon  algorithm

1476 problem

```java
//https://www.acmicpc.net/problem/1476
package ex01;

import java.util.Scanner;

public class ExhaustiveSearch {

	public static void main(String[] args) {
		// 1 ≤ E ≤ 15, 1 ≤ S ≤ 28, 1 ≤ M ≤ 19
		Scanner sc = new Scanner(System.in);
		String str = sc.nextLine();
		String[] strArr = str.split(" ");
		int E = Integer.parseInt(strArr[0]);
		int S = Integer.parseInt(strArr[1]);
		int M = Integer.parseInt(strArr[2]);
		int e = 1;
		int s = 1;
		int m = 1;
		// i는 우리가 알고 있는 년도
		for(int i = 1;;i++) {
			if(E == e && S == s && M == m) {
				System.out.println(i);
				break;
			}else {
				e++;
				s++;
				m++;
				if(e == 16) {e = 1;}
				if(s == 29) {s = 1;}
				if(m == 20) {m = 1;}
			}
		}
	}
}
```

