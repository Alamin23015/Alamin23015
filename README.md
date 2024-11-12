import java.io.FileNotFoundException;
import java.util.Formatter;
import java.util.Scanner;

class FileDemo {
    public static void main(String[] args) {
        String id, name;
        
        try {
            Formatter formatter = new Formatter("D:/JAVA/student Details.txt");
            Scanner input = new Scanner(System.in);

            System.out.println("How many students: ");
            int num = input.nextInt();
            for (int i = 1; i <= num; i++) {
                System.out.println("Enter the student name and id:");
                id = input.next();
                name = input.next();
                formatter.format("%s %s\r\n", id, name);
            }
            formatter.close();
            input.close();
        } catch (FileNotFoundException e) {
            System.out.println(e);
        }
    }
}
