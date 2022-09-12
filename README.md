# CellPhoneService.java

import java.util.*;
public class CellPhoneService {
    public static void main (String args[]) {
        Scanner InputService = new Scanner(System.in);

        final int PLAN_A = 49;
        final int PLAN_B = 55;
        final int PLAN_C = 61;
        final int PLAN_D = 70;
        final int PLAN_E = 79;
        final int PLAN_F = 87;
        
        final int TALK_MIN = 500;
        final int TEXT_MIN = 100;
        final int DATA_MIN = 3;

        char plan;
        int totalPrice;

        System.out.println("Enter talk minutes needed ");
        int talk = InputService.nextInt();
        System.out.println("Enter text messages needed");
        int text = InputService.nextInt();
        System.out.println("Enter gigabytes of data needed");
        int data = InputService.nextInt();

        if (data > 0) {
            if (data >= DATA_MIN) {
                plan = 'F';
                totalPrice = PLAN_F;
            } else {
                plan = 'E';
                totalPrice = PLAN_E;
            }
        } else {
            if (talk < TALK_MIN) {
                if (text == 0) {
                    plan = 'A';
                    totalPrice = PLAN_A;
                } else {
                    plan = 'B';
                    totalPrice = PLAN_B;
                }
            } else {
                if (text >= TEXT_MIN) {
                    plan = 'D';
                    totalPrice = PLAN_D;
                } else {
                    plan = 'C';
                    totalPrice = PLAN_C;
                }
            }
        }
        System.out.println("Plan " + plan + "  $" + totalPrice + " per month");
    }
}
