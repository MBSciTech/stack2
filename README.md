import java.util.Scanner;

class Stack1{
    final static int limit = 5;
    static int arr[] = new int[limit];
    static int top = -1;
    public static final String ANSI_RESET = "\u001B[0m";
    public static final String ANSI_RED = "\u001B[31m";
    public static final String ANSI_GREEN = "\u001B[32m";

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int choice = 0;

        do {
            System.out.println("1.push\n2.pop\n3.exit\n4.display");
            System.out.print(ANSI_RED + "Enter choice : "+ ANSI_RESET);
            choice = sc.nextInt();

            switch (choice) {
                case 1:
                    push(sc);
                    break;

                case 2:
                    pop();
                    break;

                case 4:
                    display();
                    break;
            }
        } while (choice != 3);
        
      
    }

    public static void push(Scanner sc) {
        if (top >= limit - 1) {
            System.out.println("Stack is full");
            return;
        }
        System.out.println("Enter element : ");
        top++;
        arr[top] = sc.nextInt();
    }

    public static void pop() {
        top--;
    }

    public static void display() {
        if (top == -1) {
            System.out.println("Stack is empty");
            return;
        }
        for (int i = 0; i <= top; i++) {
            System.out.println(ANSI_GREEN + arr[i] + ANSI_RESET);
        }
    }
}

