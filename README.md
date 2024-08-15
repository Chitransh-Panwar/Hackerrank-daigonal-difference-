# Hackerrank-daigonal-difference-
//this is solution of of hackerrank problem of daigonal differnce 
import java.io.*;

class Result {

    /*
     * Complete the 'timeConversion' function below.
     *
     * The function is expected to return a STRING.
     * The function accepts STRING s as parameter.
     */

    public static String timeConversion(String s) {
        // Extract the AM/PM part
        String ampm = s.substring(s.length() - 2);

        // Extract the hour part
        String hour = s.substring(0, 2);

        String result = s.substring(0, s.length() - 2);  // Remove AM/PM

        if (ampm.equals("AM")) {
            // If it's AM and hour is 12, change to 00
            if (hour.equals("12")) {
                result = "00" + s.substring(2, s.length() - 2);
            }
        } else if (ampm.equals("PM")) {
            // If it's PM and hour is not 12, add 12 to the hour
            if (!hour.equals("12")) {
                int hr = Integer.parseInt(hour);
                hr += 12;
                result = hr + s.substring(2, s.length() - 2);
            }
        }

        return result;
    }
}

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        String s = bufferedReader.readLine();

        String result = Result.timeConversion(s);

        bufferedWriter.write(result);
        bufferedWriter.newLine();

        bufferedReader.close();
        bufferedWriter.close();
    }
}
