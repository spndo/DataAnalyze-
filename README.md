# DataAnalyze-
Ask user to enter a group of #s. Then make comparison to find whether max equals min or less than 2 times of min
import java.util.Scanner;

public class DataAnalyze {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);

		System.out.print("Please enter the simple size: ");
		int maxn = input.nextInt();

		int i,j;

		int[]total = new int[4];
		int[]avg = new int[4];

		int[] arr0 = new int[maxn];
		int[] arr1 = new int[maxn];
		int[] arr2 = new int[maxn];
		int[] arr3 = new int[maxn];

		int min = Integer.MAX_VALUE;
		int max = Integer.MIN_VALUE;

		System.out.println("Enter numbers for Trial 0");
		for (i=0;i< maxn;i++){
			System.out.print("Enter sample #" + i + ": ");
			arr0[i] = input.nextInt();
			total[0] += arr0[i];
		}

		System.out.println("Enter numbers for Trial 1");
		for (i=0;i< maxn;i++){
			System.out.print("Enter sample #" + i + ": ");
			arr1[i] = input.nextInt();
			total[1] += arr1[i];
		}

		System.out.println("Enter numbers for Trial 2");
		for (i=0;i< maxn;i++){
			System.out.print("Enter sample #" + i + ": ");
			arr2[i] = input.nextInt();
			total[2] += arr2[i];
		}

		System.out.println("Enter numbers for Trial 3");
		for (i=0;i< maxn;i++){
			System.out.print("Enter sample #" + i + ": ");
			arr3[i] = input.nextInt();
			total[3] += arr3[i];
		}

		for(j=0;j<4;j++){
			avg[j]=total[j]/maxn;
		}


		for(j=0;j<4;j++){
			if(avg[j] < min)
				min = avg[j];
			if(avg[j] > max)
				max = avg[j];
		}


		System.out.println("\tSample#\tTrial 0\tTrial 1\tTrial 2\tTrial 3");
		for(i=0;i<maxn;i++){
			System.out.println("\t"+ i + "\t" + arr0[i] + "\t" + arr1[i] + "\t" + arr2[i] + "\t" + arr3[i]);
		}

		System.out.println("\t--------------------------------------------------------");

		System.out.print("Average:");
		for(j=0;j<4;j++){
			System.out.print("\t"+avg[j]);
		}

		System.out.println("");
		System.out.println("Min Average: " + min);
		System.out.println("Max Average: " + max);

		if(max == min)
			System.out.println("The trials match EXACTLY!");
		else if(max < 2*min)
			System.out.println("The trials concur with each other!");
		else
			System.out.println("The trials do NOT concur!");


		input.close();

	}

}
