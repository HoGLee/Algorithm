## BaekJoon algorithm(1,2,3더하기 재귀)

9095 problem

```java
//https://www.acmicpc.net/problem/9095
import java.util.*;
public class OneTwoThreePlus {
	public static int go(int count, int sum, int goal) {
		System.out.println("count : "+count+",sum : "+sum);
		if(sum > goal)	return 0;
		if(sum == goal)	return 1;
		int now = 0;
		for(int i = 1; i <= 3; i++) {
			now += go(count+1,sum+i,goal);
		}
		return now;
	}
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int tc = sc.nextInt();
		for(int i = 0; i < tc; i++) {
			int goal = sc.nextInt();
			System.out.println(go(0,0,goal));
		}
	}

}
```

