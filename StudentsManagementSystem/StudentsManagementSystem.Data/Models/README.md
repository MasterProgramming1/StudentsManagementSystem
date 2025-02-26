# Models Folder

The Models folder is a critical part of the Data Layer in our application. It contains classes that represent the structure of the data used in the application. These classes are often referred to as Data Models or Entity Classes.

## Purpose
The primary purpose of the Models folder is to:

- **Define Data Structures**: Each class in this folder represents a table in the database or a data structure used in the application.
- **Encapsulate Business Logic**: Models can include validation logic, data annotations, and relationships between entities.
- **Enable Data Access**: Models are used by Entity Framework (or other ORM tools) to interact with the database.

## Structure

- Each model class corresponds to a database table or a data entity.
- Models should follow the **Single Responsibility Principle** and represent a single entity or concept.
- Use **Data Annotations** or **Fluent API** to define constraints, relationships, and validation rules.

## Example Model Class

```csharp
namespace MyApp.Data.Models
{
    public class Product
    {
        public int Id { get; set; } // Primary key
        public string Name { get; set; } // Product name
        public decimal Price { get; set; } // Product price
        public int StockQuantity { get; set; } // Available stock

        // Relationships
        public int CategoryId { get; set; } // Foreign key
        public Category Category { get; set; } // Navigation property
    }
}
```

## Best Practices

### Naming Conventions:
- Use **PascalCase** for class and property names.
- Name models in **singular form** (e.g., `Product`, not `Products`).

### Data Annotations:
- Use attributes like `[Required]`, `[MaxLength]`, and `[DataType]` to enforce validation rules.

### Relationships:
- Define relationships (e.g., one-to-many, many-to-many) using navigation properties.

### Separation of Concerns:
- Avoid adding business logic directly to models. Use **Service Classes** or **Repositories** for complex logic.

### Documentation:
- Add **XML comments** to describe the purpose of each model and its properties.

## Folder Structure

```
/Data
  /Models
    Product.cs
    Category.cs
    Order.cs
    README.md
```

## When to Add a New Model
Add a new model when:

- A new table is added to the database.
- A new data structure is required for the application.
- A new entity is introduced in the business logic.
