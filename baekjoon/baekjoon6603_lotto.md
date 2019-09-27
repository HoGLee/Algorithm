## Baekjoon algorithm(lotto)

problem 6603

```java
//https://www.acmicpc.net/problem/6603
import java.util.*;

class Solution {
	static int[] arr = new int[12];
	static ArrayList<Integer> list = new ArrayList<>();
	static int N;
	static int cnt = 0;
	static void lotto(int index, int count) {
		if(count == 6) {	
			for(int i = 0; i < 6; i++) {
				if(i == 5) {
					System.out.print(list.get(i));
				}else
					System.out.print(list.get(i)+" ");
			}
			System.out.println("");
			return;
		}
		if(N == index)	return;
		list.add(arr[index]);
		lotto(index+1,count+1);
		list.remove(list.size()-1);
		lotto(index+1,count);
	}
    public static void main(String[] args) {
    	Scanner sc = new Scanner(System.in);
    	while(true) {
    		int n = sc.nextInt();
    		if(n == 0)	break;
    		else {
    			N = n;
    			Arrays.fill(arr, 0);
    			for(int i = 0; i < n; i++) {
    				arr[i] = sc.nextInt();
    			}
    			lotto(0,0);
    		}
    		sc.nextLine();
    		System.out.println("");
    	}
    }
}

```

