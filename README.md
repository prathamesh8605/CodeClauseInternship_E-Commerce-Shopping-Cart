import java.util.ArrayList;
import java.util.List;

class Product {
    private String name;
    private double price;

    public Product(String name, double price) {
        this.name = name;
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public double getPrice() {
        return price;
    }
}

class ShoppingCart {
    private List<Product> items;

    public ShoppingCart() {
        items = new ArrayList<>();
    }

    public void addItem(Product product) {
        items.add(product);
        System.out.println(product.getName() + " added to cart.");
    }

    public void removeItem(Product product) {
        items.remove(product);
        System.out.println(product.getName() + " removed from cart.");
    }

    public double getTotalPrice() {
        double totalPrice = 0.0;
        for (Product item : items) {
            totalPrice += item.getPrice();
        }
        return totalPrice;
    }

    public void displayCart() {
        System.out.println("Items in your cart:");
        for (Product item : items) {
            System.out.println("- " + item.getName() + ": $" + item.getPrice());
        }
        System.out.println("Total Price: $" + getTotalPrice());
    }
}

public class Main {
    public static void main(String[] args) {
        Product laptop = new Product("Laptop", 1000.0);
        Product phone = new Product("Phone", 500.0);

        ShoppingCart cart = new ShoppingCart();

        cart.addItem(laptop);
        cart.addItem(phone);

        cart.displayCart();

        cart.removeItem(laptop);

        cart.displayCart();
    }
}
