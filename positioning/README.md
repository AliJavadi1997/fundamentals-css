# Positioning

Positioning allows us to produce interesting results by overriding normal document flow.
What if you want to create a UI element that floats over the top of other parts of the page and/or always sits in the same place inside the browser window no matter how much the page is scrolled? Positioning makes such layout work possible.

## Static Position

Static positioning is the **default** that every element gets.

## Relative Position

The element is positioned according to the normal flow of the document, and then offset _relative to itself_ based on the values of `top`, `right`, `bottom`, and `left`.

## Absolute Position

The element is removed from the normal document flow, and no space is created for the element in the page layout. The element is positioned relative to its closest positioned ancestor (if any) or to the initial . Its final position is determined by the values of `top`, `right`, `bottom`, and `left`.

An absolutely positioned element takes its position relative to its closest ancestor with non-static positioning (either `relative` or `absolute`). By setting the parent to `relative`, you create a reference point within the document flow for the child element.

## Fixed Position

he element is removed from the normal document flow, and no space is created for the element in the page layout. The element is positioned relative to its initial, which is the viewport in the case of visual media. Its final position is determined by the values of `top`, `right`, `bottom`, and `left`.

## Sticky Position

The element is positioned according to the normal flow of the document, and then offset relative to its _nearest scrolling ancestor_ , including table-related elements, based on the values of `top`, `right`, `bottom`, and `left`. The offset does not affect the position of any other elements.

# What is Stacking Context?

In HTML and CSS, stacking context refers to a layered system that determines the order in which elements overlap on a webpage. Imagine the webpage as a stack of transparent sheets, with elements on each sheet. Stacking context dictates which element goes on which sheet and the order of the sheets themselves.

Here's a breakdown of stacking context:

- **Conceptualizing the Z-axis:** Elements are positioned along an imaginary z-axis, similar to a 3D space. Elements closer to the user (positive z-axis) appear in front of elements further away (negative z-axis).
- **Creating Stacking Contexts:** Several CSS properties can create new stacking contexts:

  - **The root element:** The `<html>` element itself inherently creates the initial stacking context for the entire page.
  - **Positioned elements:** Elements with `position: absolute`, `position: relative` (with `z-index` other than `auto`), `position: fixed`, or `position: sticky` create new stacking contexts.
  - **Opacity:** An element with `opacity` less than 1 (semi-transparent) also establishes a new stacking context.
  - **Other properties:** Newer CSS properties like `transform`, `will-change`, and container queries can also trigger stacking contexts.

- **Layering within a Context:** Elements inside a stacking context are layered based on their position and `z-index` property.

  - **Z-index:** This property allows you to specify the stacking order within a context. Higher `z-index` values appear on top of elements with lower values.

- **Nested Contexts:** Stacking contexts can be nested. Child elements that create new stacking contexts become their own mini-stacks within the parent context.
