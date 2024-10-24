# CSS Grid System

YT: https://youtu.be/xI9G0Zh5DVA?si=ItIkvElPezTd45VC

# Grid CSS Beginner Notes

## 1. What is CSS Grid?
CSS Grid is a layout system for creating complex web layouts easily. It works by defining rows and columns to organize content, similar to HTML tables but more powerful. It lets you place items wherever you want on the grid, making responsive design simpler.

## 2. Basic Concepts

- **Grid Container**: The parent element that defines the grid. It becomes a grid container when `display: grid` is applied.
- **Grid Items**: The child elements of the grid container. These are placed inside the grid's defined rows and columns.

## 3. Key Properties for Grid Layout

- `display: grid`: Turns the container into a grid.
- `grid-template-columns`: Defines the number and size of columns.
- `grid-template-rows`: Defines the number and size of rows.
- `grid-column` and `grid-row`: Position items within the grid by specifying start and end lines.
- `gap`: Sets space between rows and columns.

## Basic Usage

### Creating a Grid Container

```css
.container {
  display: grid;
  grid-template-columns: 100px 200px 1fr;
  grid-template-rows: 100px 50px;
}
```

- Defines a container with three columns and two rows.
  - **Columns**: 100px, 200px, and the remaining space (1fr).
  - **Rows**: 100px and 50px.

### Using Fractional Units (fr)

- `1fr` represents a fraction of the available space.
- Example: `grid-template-columns: 1fr 2fr` divides the space into three parts, with the second column taking two-thirds.

### Using the repeat() Function

- Allows repeated patterns without manually specifying each column/row.

```css
grid-template-columns: repeat(3, 100px);
```
