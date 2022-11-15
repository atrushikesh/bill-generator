# Pizza Bill Generator Using Java
This is a project made 100% using Java.


I created a Bill Gererator interface where the customer can order two types of pizzas, a "Regular" one and a "Max" pizza.


Both of these have the option of veg and non veg.


There is also an option of the regular pizza for add-ons of :
1. Extra Cheeze
2. Extra Toppins


Both of these cost a few extra.


There is also option to take away with additional costs.
```
public class pizza{
    public static void main(String args[]){
        //pizza regularPizza = new pizza(true);
        //regularPizza.addExtraCheese();
        //regularPizza.addToppings();
        //regularPizza.TakeAway();
        //regularPizza.getBill();

        MaxPizza mp = new MaxPizza(false);
        mp.addExtraCheese();
        mp.TakeAway();
        mp.getBill();
    }
    private int price;
    private boolean veg;

    //Add-ons
    private int extraCheesePrice = 50;
    private int extraToppingsPrice = 100;
    private int getpackage = 20;

    private int regularPizzaPrice;

    private boolean isExtraCheeseAdded = false;
    private boolean isExtraToppingsAdded = false;
    private boolean isTakeAwayOpted = false;

public pizza(Boolean veg){
    this.veg = veg;
    if(this.veg){
        // price of regular veg pizza
        this.price = 250;
    }
    else{
        // price of regular non-veg pizza
        this.price = 350;
    }
    regularPizzaPrice = this.price;
}

// Add-on for Extra Cheeze
public void addExtraCheese(){
    System.out.println("");
    isExtraCheeseAdded = true;
    this.price += extraCheesePrice;
}

// Add-on for Extra Toppings
public void addToppings(){
    System.out.println("");
    isExtraToppingsAdded = true;
    this.price += extraToppingsPrice;
}

// Option for Take Away
public void TakeAway(){
    System.out.println("");
    isTakeAwayOpted = true;
    this.price += getpackage;
}

// Option to get Bill Statement
public void getBill(){ // Option to get Bill Statement
    System.out.println("");
    System.out.println("      -------- Here is our Bill --------");
    System.out.println("Pay through UPI or Cash at your convinience :) ");
    System.out.println("");
    System.out.println("");
    System.out.println("=> Your Pizza            | ₹" +regularPizzaPrice);
    System.out.println("");

    if(isExtraCheeseAdded){
        System.out.println("=> Extra Cheese Added    | ₹" + extraCheesePrice);
        System.out.println("");
    }

    if(isExtraToppingsAdded){
        System.out.println("=> Extra Toppings Added  | ₹" + extraToppingsPrice);
        System.out.println("");
    }
    
    if(isTakeAwayOpted){
        System.out.println("=> You opted Take Away   | ₹" + getpackage);
        System.out.println("");
    }

    System.out.println("TOTAL AMOUNT TO BE PAID  | ₹"+ this.price);
    System.out.println("");
    }
}

// Class for Max Pizza
class MaxPizza extends pizza{
    public MaxPizza(Boolean veg){
        super(veg);
        super.addExtraCheese();
        super.addToppings();
    }
    @Override
    public void addExtraCheese(){}

    @Override
    public void addToppings(){}
}
```
