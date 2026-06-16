# Shop-Management
mall store-management
# Mall Store Management System

products = {
    "Shampoo": {"price": 120, "stock": 20},
    "Soap": {"price": 40, "stock": 50},
    "Biscuits": {"price": 30, "stock": 35}
}

def show_products():
    print("\n--- Product List ---")
    for item, details in products.items():
        print(item, "| Price:", details["price"], "| Stock:", details["stock"])

def add_product():
    name = input("Enter product name: ")
    price = int(input("Enter price: "))
    stock = int(input("Enter stock quantity: "))

    products[name] = {"price": price, "stock": stock}
    print("Product added successfully!")

def sell_product():
    name = input("Enter product name to sell: ")

    if name in products:
        qty = int(input("Enter quantity: "))

        if qty <= products[name]["stock"]:
            total = qty * products[name]["price"]
            products[name]["stock"] -= qty

            print("\n----- BILL -----")
            print("Product:", name)
            print("Quantity:", qty)
            print("Total Amount: ₹", total)
            print("----------------")
        else:
            print("Not enough stock available!")
    else:
        print("Product not found!")

while True:
    print("\n===== MALL STORE MANAGEMENT =====")
    print("1. Show Products")
    print("2. Add Product")
    print("3. Sell Product")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        show_products()

    elif choice == "2":
        add_product()

    elif choice == "3":
        sell_product()

    elif choice == "4":
        print("Thank you!")
        break

    else:
        print("Invalid choice!")
