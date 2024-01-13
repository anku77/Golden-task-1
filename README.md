# Golden-task-1
import java.util.ArrayList;
import java.util.Scanner;

class Alumni {
    private String name;
    private int graduationYear;
    private String contactInfo;

    public Alumni(String name, int graduationYear, String contactInfo) {
        this.name = name;
        this.graduationYear = graduationYear;
        this.contactInfo = contactInfo;
    }

    public String getName() {
        return name;
    }

    public int getGraduationYear() {
        return graduationYear;
    }

    public String getContactInfo() {
        return contactInfo;
    }

    @Override
    public String toString() {
        return "Name: " + name + "\nGraduation Year: " + graduationYear + "\nContact Info: " + contactInfo;
    }
}

class AlumniManagementSystem {
    private ArrayList<Alumni> alumniList;
    private Scanner scanner;

    public AlumniManagementSystem() {
        alumniList = new ArrayList<>();
        scanner = new Scanner(System.in);
    }

    public void addAlumni(String name, int graduationYear, String contactInfo) {
        Alumni newAlumni = new Alumni(name, graduationYear, contactInfo);
        alumniList.add(newAlumni);
        System.out.println("Alumni added: " + name);
    }

    public void displayAlumni() {
        System.out.println("\n--- Alumni List ---");
        for (Alumni alumni : alumniList) {
            System.out.println(alumni);
            System.out.println("-------------");
        }
    }

    public static void main(String[] args) {
        AlumniManagementSystem alumniSystem = new AlumniManagementSystem();
        int choice;

        do {
            System.out.println("\n1. Add Alumni");
            System.out.println("2. Display Alumni");
            System.out.println("3. Exit");
            System.out.print("Enter your choice: ");
            choice = alumniSystem.scanner.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter alumni name: ");
                    String name = alumniSystem.scanner.next();
                    System.out.print("Enter graduation year: ");
                    int graduationYear = alumniSystem.scanner.nextInt();
                    System.out.print("Enter contact info: ");
                    String contactInfo = alumniSystem.scanner.next();
                    alumniSystem.addAlumni(name, graduationYear, contactInfo);
                    break;
                case 2:
                    alumniSystem.displayAlumni();
                    break;
                case 3:
                    System.out.println("Exiting Alumni Management System. Goodbye!");
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        } while (choice != 3);
    }
}
