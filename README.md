# FirstRepository
//Andru Ramirez
//Assignment 6 q 1
//12/11/19 

import java.util.Scanner;
class Main {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);

    //Get input length and width
    System.out.print("\nEnter length of the room in feet: ");
    double length = input.nextDouble();
    System.out.print("Enter width of the room in feet: ");
    double width = input.nextDouble();
    System.out.print("Enter the cost of carpeting per square foot: $");
    double cost = input.nextDouble();
		//calls calsses
    RoomDimension dimenstion = new RoomDimension(length, width);
    RoomCarpet carpet = new RoomCarpet(dimenstion, cost);

    //Display the total cost
    System.out.print("\nTotal cost: $" + carpet.returnCost());

    input.close();
  }
}

class RoomDimension{
  private double length, width;

  //Constructor
  RoomDimension(double length, double width){
    this.length = length;
    this.width = width;
  }

  //calls the area of the room
  public double returnArea(){
    return length * width;
  }
}

class RoomCarpet{
  private double area, cost;

  //Constructor
  RoomCarpet(RoomDimension room, double money){
    area = room.returnArea();
    cost = money;
  }

  //Return the cost of the carpet
  public double returnCost(){
    return area * cost;
  }
}
