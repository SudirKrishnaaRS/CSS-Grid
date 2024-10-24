# CSS Grid System

YT: https://youtu.be/xI9G0Zh5DVA?si=ItIkvElPezTd45VC

# Grid CSS Notes

**1. What is CSS Grid?**

CSS Grid is a layout system for creating complex web layouts easily. It works by defining rows and columns to organize content, similar to HTML tables but more powerful. It lets you place items wherever you want on the grid, making responsive design simpler.

**2. Basic Concepts**

- **Grid Container**: The parent element that defines the grid. It becomes a grid container when `display: grid` is applied.
- **Grid Items**: The child elements of the grid container. These are placed inside the grid's defined rows and columns.

**3. Key Properties for Grid Layout**

- **`display: grid`**: Turns the container into a grid.
- **`grid-template-columns`**: Defines the number and size of columns.
- **`grid-template-rows`**: Defines the number and size of rows.
- **`grid-column` and `grid-row`**: Position items within the grid by specifying start and end lines.
- **`gap`**: Sets space between rows and columns.

## Basic Usage

1. **Creating a Grid Container**
    
    ```css
    
    .container {
      display: grid;
      grid-template-columns: 100px 200px 1fr;
      grid-template-rows: 100px 50px;
    }
    ```
    
    - Defines a container with three columns and two rows.
    - Columns: 100px, 200px, and the remaining space (`1fr`).
    - Rows: 100px and 50px.
    
2. **Using Fractional Units (`fr`)**
    - `1fr` represents a fraction of the available space.
    - Example: `grid-template-columns: 1fr 2fr` divides the space into three parts, with the second column taking two-thirds.
    
3. **Using the `repeat()` Function**
    - Allows repeated patterns without manually specifying each column/row.
    
    ```css
    
    grid-template-columns: repeat(3, 100px);
    
    ```
    

## Advanced Usage

1. **Positioning Items Using `grid-column` and `grid-row`**
    - Move items to different rows/columns.
    
    ```css
    
    .item {
      grid-column: 2 / 4; /* Starts at column 2, spans to column 4 */
      grid-row: 1 / 3;    /* Starts at row 1, spans to row 3 */
    }
    ```
    
2. **Overlapping Items**
    - Items can overlap, similar to the CSS `position` property.
    - Use `z-index` to control which item appears on top.
    
3. **Grid Area for Simplified Layout Management**
    - Instead of using `grid-column` and `grid-row`, define areas.
    
    ```css
    
    .container {
      grid-template-areas:
        "header header header"
        "sidebar content content"
        "footer footer footer";
    }
    
    .header { 
    	grid-area: header; 
    }
    
    .sidebar { 
    	grid-area: sidebar; 
    }
    
    .content { 
    	grid-area: content; 
    }
    
    .footer { 
    	grid-area: footer; 
    }
    
    ```
    

## Responsive Design with Grid

1. **Using Media Queries**
    - Adjust the number of columns or rows based on the screen size.
    
    ```css
    
    @media (max-width: 768px) {
      .container {
        grid-template-columns: repeat(2, 1fr);
      }
    }
    
    ```
    
2. **Using `auto-fill` and `auto-fit` for Dynamic Columns**
    - Automatically adjust the number of columns to fit the available space.
    
    ```css
    
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    
    ```
    

# Cheatsheet

| **Property** | **Description** | **Example** |
| --- | --- | --- |
| `display: grid` | Turns on grid layout. | `.container { display: grid; }` |
| `grid-template-columns` | Defines column sizes and numbers. | `grid-template-columns: 100px 1fr 2fr;` |
| `grid-template-rows` | Defines row sizes and numbers. | `grid-template-rows: 50px auto;` |
| `grid-column` | Positions an item in the grid columns. | `grid-column: 1 / 3;` |
| `grid-row` | Positions an item in the grid rows. | `grid-row: 2 / 4;` |
| `gap` | Sets space between grid items. | `gap: 10px 20px;` |
| `grid-template-areas` | Defines named areas for layout. | See "Grid Area for Simplified Layout Management" |
| `auto-fill` / `auto-fit` | Automatically adjusts column count based on screen size. | `repeat(auto-fill, minmax(100px, 1fr));` |

## Tips

- **Use `fr` units for flexible layouts**: Makes it easy to adapt to different screen sizes.
- **Combine `repeat()` with `auto-fill/auto-fit` for dynamic grids**: It reduces the need for media queries.
- **Use `grid-template-areas` for intuitive layouts**: Makes the code more readable.

