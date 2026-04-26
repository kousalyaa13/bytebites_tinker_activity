classDiagram
    class Customer {
        -name: String
        -purchaseHistory: List~Transaction~
        +getName(): String
        +getPurchaseHistory(): List~Transaction~
        +addTransaction(transaction: Transaction): void
    }

    class FoodItem {
        -name: String
        -price: Float
        -category: String
        -popularityRating: Float
        +getName(): String
        +getPrice(): Float
        +getCategory(): String
        +getPopularityRating(): Float
        +setPopularityRating(rating: Float): void
    }

    class Menu {
        -items: List~FoodItem~
        +addItem(item: FoodItem): void
        +removeItem(item: FoodItem): void
        +getItems(): List~FoodItem~
        +filterByCategory(category: String): List~FoodItem~
    }

    class Transaction {
        -items: List~FoodItem~
        -totalCost: Float
        +addItem(item: FoodItem): void
        +removeItem(item: FoodItem): void
        +getItems(): List~FoodItem~
        +calculateTotal(): Float
        +getTotalCost(): Float
    }

    Customer --> Transaction: has purchase history
    Menu --> FoodItem: contains
    Transaction --> FoodItem: contains