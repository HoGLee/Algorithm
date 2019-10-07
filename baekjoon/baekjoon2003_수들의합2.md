## Baekjoon Algorithm(수들의 합2)

2003 problem

```java
//https://www.acmicpc.net/problem/2003
import java.util.*;
public class Solution{
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt();
		int M = sc.nextInt();
		int[] list = new int[N+1];
		sc.nextLine();
		for(int i = 0; i < N; i++) {
			list[i] = sc.nextInt();
		}
		list[N] = 0;
		int left = 0, right = 0, answer = 0, sum = list[0];
		while(left <= right && right < N) {
			if(sum < M) {
				right++;
				sum += list[right];
			}else if(sum == M) {
				right++;
				sum += list[right];
				answer++;
			}else if(sum > M) {
				sum -= list[left];
				left++;
				if(left > right && left < N) {
					right = left;
					sum = list[left];
				}
			}
		}
		System.out.println(answer);
	}
}
```

