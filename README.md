menu = {
    "Burger": 5.99,
    "Pizza": 8.99,
    "Salad": 4.99,
    "Soda": 1.99,
    "Fries": 2.99
}
def take_order():
    order = {}
    print("Welcome to the Restaurant Billing System")
    print("Here is the menu:")
    for item, price in menu.items():
        print(f"{item}: ${price:.2f}")
    
    while True:
        item = input("Enter the item you want to order (or 'done' to finish): ").strip().title()
        if item.lower() == 'done':
            break
        if item in menu:
            quantity = int(input(f"Enter the quantity for {item}: "))
            if item in order:
                order[item] += quantity
            else:
                order[item] = quantity
        else:
            print("Item not found in the menu. Please try again.")
    
    return order
    def calculate_total(order):
    total = 0.0
    for item, quantity in order.items():
        total += menu[item] * quantity
    return total
    def generate_receipt(order, total):
    print("\n--- Receipt ---")
    for item, quantity in order.items():
        print(f"{item} x {quantity}: ${menu[item] * quantity:.2f}")
    print(f"Total Amount: ${total:.2f}")
    print("----------------")
    print("Thank you for dining with us!")

def main():
    order = take_order()
    total = calculate_total(order)
    generate_receipt(order, total)

# Run the billing system
main()
