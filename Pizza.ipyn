import csv
import datetime

class Pizza:
    def __init__(self, description, cost):
        self.description = description
        self.cost = cost
    
    def get_description(self):
        return self.description
    
    def get_cost(self):
        return self.cost

class PizzaDecorator(Pizza):
    def __init__(self, pizza):
        self.pizza = pizza
    
    def get_description(self):
        return self.pizza.get_description()
    
    def get_cost(self):
        return self.pizza.get_cost()

class Olives(PizzaDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Olives"
        self.cost = 8.0
    
    def get_description(self):
        return self.pizza.get_description() + ", " + self.description
    
    def get_cost(self):
        return self.pizza.get_cost() + self.cost

class Mushrooms(PizzaDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Mushrooms"
        self.cost = 15.5
    
    def get_description(self):
        return self.pizza.get_description() + ", " + self.description
    
    def get_cost(self):
        return self.pizza.get_cost() + self.cost

class GoatCheese(PizzaDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Goat Cheese"
        self.cost = 17.0
    
    def get_description(self):
        return self.pizza.get_description() + ", " + self.description
    
    def get_cost(self):
        return self.pizza.get_cost() + self.cost

class Meat(PizzaDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Meat"
        self.cost = 20.5
    
    def get_description(self):
        return self.pizza.get_description() + ", " + self.description
    
    def get_cost(self):
        return self.pizza.get_cost() + self.cost

class Onions(PizzaDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Onions"
        self.cost = 8.5
    
    def get_description(self):
        return self.pizza.get_description() + ", " + self.description
    
    def get_cost(self):
        return self.pizza.get_cost() + self.cost

class Corn(PizzaDecorator):
    def __init__(self, pizza):
        super().__init__(pizza)
        self.description = "Corn"
        self.cost = 8.0
    
    def get_description(self):
        return self.pizza.get_description() + ", " + self.description
    
    def get_cost(self):
        return self.pizza.get_cost() + self.cost

def main():
    # create menu file
    with open("Menu.txt", "w") as f:
        f.write("* Please Choose a Pizza Base:\n1: Classic\n2: Margherita\n3: TurkPizza\n4: PlainPizza\n")
        f.write("* and sauce of your choice:\n11: Olives\n12: Mushrooms\n13: GoatCheese\n14: Meat\n15: Onions\n16: Corn\n")
        f.write("* Thank you!\n")
    
    # display menu
    with open("Menu.txt", "r") as f:
        print(f.read())
    
    # get user input for pizza base and sauce
    pizza_base = input("Please choose a pizza base (1-4): ")
    sauce = input("Please choose a sauce (11-16): ")
    
    # create pizza object based on user input
    if pizza_base == "1":
        pizza = Pizza("Classic Pizza", 70.0)
    elif pizza_base == "2":
        pizza = Pizza("Margherita Pizza", 52.0)
    elif pizza_base == "3":
        pizza = Pizza("TurkPizza", 85.0)
    elif pizza_base == "4":
        pizza = Pizza("PlainPizza", 48.0)
    else:
        print("Invalid pizza base selection")
        return
    
    # add selected sauce(s) to pizza object
    if sauce == "11":
        pizza = Olives(pizza)
    elif sauce == "12":
        pizza = Mushrooms(pizza)
    elif sauce == "13":
        pizza = GoatCheese(pizza)
    elif sauce == "14":
        pizza = Meat(pizza)
    elif sauce == "15":
        pizza = Onions(pizza)
    elif sauce == "16":
        pizza = Corn(pizza)
    else:
        print("Invalid sauce selection")
        return
    
    # calculate total cost of pizza
    total_cost = pizza.get_cost()
    
    # get user information for payment
    name = input("Enter your name: ")
    id_num = input("Enter your ID number: ")
    cc_num = input("Enter your credit card number: ")
    cc_pass = input("Enter your credit card password: ")
    
    # create timestamp for order
    timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    
    # write order information to database
    with open("Orders_Database.csv", "a") as f:
        writer = csv.writer(f)
        writer.writerow([name, id_num, cc_num, cc_pass, pizza.get_description(), timestamp])
    
    # display total cost of pizza to user
    print("Your total cost is: ₺", total_cost)

    main ()

    
