## Baekjoon Algorithm(부분집합의 합)

1182

```java
/*www.acmicpc.net/problem/1182*/
import java.io.*;
import java.util.*;
class Solution {
	static int answer = 0;
	static void go(int[] arr, int count, int index, int sum, int n) {
		if(n == index) {
			if(count == sum) {
				answer++;
			}
			return ;
		}
		go(arr,count+arr[index],index+1,sum, n);
		go(arr,count,index+1,sum, n);
	}
	public static void main(String[] args) throws Exception {
		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt();
		int sum = sc.nextInt();
		int[] arr = new int[N];
		sc.nextLine();
		for(int i = 0; i < N; i++) {
			arr[i] = sc.nextInt();
		}
		go(arr,0,0,sum,N);
		if(sum == 0)	answer -= 1;
		System.out.println(answer);
	}
}
```

