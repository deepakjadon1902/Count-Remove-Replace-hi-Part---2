
import java.util.*;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        System.out.println( countHi(str));
        System.out.println( removeHi(str));
        System.out.println( replaceHi(str));
    }

    public static int countHi(String str) {
        if (str.length() < 2) {
            return 0;
        } else if (str.startsWith("hi") && !str.startsWith("hit")) {
            return 1 + countHi(str.substring(2));
        } else {
            return countHi(str.substring(1));
        }
    }

    public static String removeHi(String str) {
        if (str.length() < 2) {
            return str;
        } else if (str.startsWith("hi") && !str.startsWith("hit")) {
            return removeHi(str.substring(2));
        } else {
            return str.substring(0, 1) + removeHi(str.substring(1));
        }
    }

    public static String replaceHi(String str) {
        if (str.length() < 2) {
            return str;
        } else if (str.startsWith("hi") && !str.startsWith("hit")) {
            return "bye" + replaceHi(str.substring(2));
        } else {
            return str.substring(0, 1) + replaceHi(str.substring(1));
        }
    }
}
