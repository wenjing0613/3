package week1;

import java.util.Scanner;
public class Main {
	public static void main(String[] args) {
		@SuppressWarnings("resource")
		Scanner in = new Scanner(System.in);
		int N = in.nextInt();
		
		//确定边界，比如三位数的边界是100~999
		int min = 1;
		int max = 0;
		for(int i = 0; i < N - 1; i++) {
			min *= 10;
		}
		max = min * 10 - 1;
		
		for(int i = min; i <= max; i++) {
			if(i == sum(i,N)) {
				System.out.println(i);
			}
		}		
	}
	
	//该函数返回一个数的各位数幂运算之和
	public static int sum(int data,int N) {
		int res = 0;//各位数幂运算之和
		
		for(int j = 0; j < N; j++) {
			int t = data % 10;
			//幂运算
			for(int k = 0; k < N - 1; k++) {
				t *= (data % 10);
			}
			res += t;
			data /= 10;
		}
		
		return res;
	}
}
