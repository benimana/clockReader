package clockreader;

import javax.swing.*;
import java.awt.*;
import java.util.Scanner;
/**
 * Lab Exercise: 3 (A program to help children read a clock)
 * Course: BBIT
 * Faculty of IT
 * Strathmore University
 * 
 * Date: 2016-DEC-08
 * 
 * Lab Assignment 3
 * 
 * Objective: To write a program that teaches children how to read a clock.
 * 
 * Use a repetition statement of your choice to continuously ask the user for 
 * input. Upon receiving each valid input, your program should draw a clock. The
 * input should contain the hour and the minute. This is fed through the console
 * window using a Scanner object.
 * For validation: use a selection statement of your choice to accept only 
 * numbers between 0 and 12 for the hour and between 0 and 59 for the minute. 
 * Print out an appropriate error message for an invalid input value. 

 * @author Allan O. Omondi (aomondi@strathmore.edu)
 */
public class Clockreader {
    /*
    The javax.swing package and the java.awt package contain the classes that are
    needed to create a window frame (an instance of the class JFrame) and also to create
    a content pane (an instance of the class Container) and a graphics object (an
    instance of the class Graphics).
    */
    private static JFrame window;
    private static Container contentPane;
    private static Graphics graphics;
    
    private static int theHour;
    private static int theMinute;
   /**
    * A description of the main method.
    * @param args 
    */ 
    public static void main(String[] args) {
        drawClock();
    }
    private static void drawClock() {
        
        prepareCanvas();
        
        Scanner scanner = new Scanner(System.in);
        do{
            System.out.println("Please input the hour (0 to exit): ");
            theHour = scanner.nextInt();
            if (theHour == 0){
                System.out.println("\n\nSentinel encountered!\n"
                        + "Program shall now terminate.");
                System.exit(0);
            }
            System.out.println("\nPlease input the minute: ");
            theMinute = scanner.nextInt();
            /*Use a while loop to validate the input such that it should check
            if theHour is between 1 and 12 and minute is between 0 and 59. If it
            is not valid, it should loop and ask the user to input the value again*/
            
            contentPane.repaint();
            try{Thread.sleep(200);}catch (InterruptedException e){}
            graphics.drawOval(50, 50, 200, 200);
            
            /*These two statements will draw 3 o'clock*/
            graphics.drawLine(150, 150, (int)(150+(85*Math.cos((90-theMinute*6.0)*(Math.PI/180)))),(int)(150-(85*Math.sin((90-theMinute*6.0)*(Math.PI/180)))));//The minute hand
            
            graphics.drawLine(150,150,(int)(150+(55*Math.cos(((90-((theHour+(theMinute/60))*30))*(Math.PI/180))))), (int)(150-(55*Math.sin((90-(theHour+theMinute/60))*30)*(Math.PI/180)))); //The hour hand
            
            
   
// Erase if necessary, and redraw

        } while (true);
    }
    
    private static void prepareCanvas(){
        window = new JFrame ("Clock Reader");
        window.setSize(330, 330);
        window.setLocation(200,200);
        window.setVisible(true);
        
        contentPane = window.getContentPane();
        graphics = contentPane.getGraphics();
        try{Thread.sleep(200);}catch (InterruptedException e){}
        graphics.drawOval(50, 50, 200, 200);
    }
    
}
