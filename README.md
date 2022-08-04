# Conversion-from-Roman-NUmbers-to-Natural-Numbers-
import java.util.Scanner;

class Solute {
    public void romanToInt(String s) {
        int i = 0;
        int sum = 0;
        while (i < s.length()) {
            if (s.charAt(i) == 'I' && i != s.length() - 1) {
                if (s.charAt(i + 1) == 'V') {
                    sum = sum + 4;
                    i = i + 2;
                    continue;
                }
                if (s.charAt(i + 1) == 'X') {
                    sum = sum + 9;
                    i = i + 2;
                    continue;
                }

            }
            if (s.charAt(i) == 'X' && i != s.length() - 1) {
                if (s.charAt(i + 1) == 'L') {
                    sum = sum + 40;
                    i = i + 2;
                    continue;
                }
                if (s.charAt(i + 1) == 'C') {
                    sum = sum + 90;
                    i = i + 2;
                    continue;
                }
            }
            if (s.charAt(i) == 'C' && i != s.length() - 1) {
                if (s.charAt(i + 1) == 'D') {
                    sum = sum + 400;
                    i = i + 2;
                    continue;
                }
                if (s.charAt(i + 1) == 'M') {
                    sum = sum + 900;
                    i = i + 2;
                    continue;
                }
            }
            switch (s.charAt(i)) {
                case 'I':
                    sum = sum + 1;
                    i++;
                    break;
                case 'V':
                    sum = sum + 5;
                    i++;
                    break;
                case 'X':
                    sum = sum + 10;
                    i++;
                    break;
                case 'L':
                    sum = sum + 50;
                    i++;
                    break;
                case 'C':
                    sum = sum + 100;
                    i++;
                    break;
                case 'D':
                    sum = sum + 500;
                    i++;
                    break;
                case 'M':
                    sum = sum + 1000;
                    i++;
                    break;
            }
        }
        System.out.println(sum);

    }
}

public class Solution2 {
    public static void main(String[] args) {
        Solute s = new Solute();
        try (Scanner sc = new Scanner(System.in)) {
            String str = sc.nextLine();
            s.romanToInt(str);
            sc.close();
        }
    }
}
