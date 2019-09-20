## BaekJoon algorithm (비밀번호 만들기)

1759번 문제

```java
//https://www.acmicpc.net/problem/1759
import java.util.*;
public class CreatePassword {
	public static boolean check(String password) {
		int ja = 0;
		int mo = 0;
		for(char x : password.toCharArray()) {
            if (x == 'a' || x == 'e' || x == 'i' || x == 'o' || x == 'u') {
                mo += 1;
            } else {
                ja += 1;
            }
		}
		return ja >= 2 && mo >= 1;
	}
	public static void go(int n, String[] alpha, String password, int i) {
		if(n == password.length()) {
			if(check(password)) {System.out.println(password);}
			return ;
		}
		if(i >= alpha.length) return;
		go(n, alpha, password+alpha[i], i+1);
		go(n, alpha, password, i+1);
	}
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int m = sc.nextInt();
		sc.nextLine();
		String[] alpha = sc.nextLine().split(" ");
		Arrays.sort(alpha);
		go(n,alpha,"",0);
	}

}

```

