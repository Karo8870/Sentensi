# Sentensi: Interactive Whiteboard for Teaching Grammar

**Sentensi** is an interactive whiteboard designed for drawing and manipulating words, specifically created for teaching and evaluating primary and middle school students in grammar and contextual analysis. It includes two modes: **Teacher Mode** and **Student Mode**.  

---

## Home (https://www.sentensi.com)

The **Home page** contains a list of all the lessons made. You can create a new lesson by clicking on the create new lesson button or play an activity by clicking on the play button on one of the activities

<img width="1736" alt="image" src="https://github.com/user-attachments/assets/c538570b-024c-4733-a5e1-8988bad2be84" />

## Canvas (https://www.sentensi.com/create)

![image](https://github.com/user-attachments/assets/9439b1a3-55f3-4da8-8adc-e4c06dbb1596)

The **Canvas page** allows adding words, drawing, and manipulating them. You can add words by simply typing and then dragging them on the canvas

Words can be manipulated in the following ways:

- **Stretch**: Drag the last character of the word
- **Scale**: Drag the last character of the word
- **Resize**: Make a selection by clicking on empty space and dragging the square in the bottom left corner
- **Move**: Drag the first letter of the word
- **Color**: Select a color using the color menu and click on the word
- **Double color**: Drag the last character of the word while the double color switch is turned on
- **Rotate**: Make a selection by clicking on empty space and rotate the selected words using the rotation cursor in the middle
- **Bend**: Drag one of the letters in the middle of the word

Once the teacher is satisfied with the current page, they can switch to **activity mode (Text Maker)** to manage pages and create activities.

---

## Text Maker

![image](https://github.com/user-attachments/assets/28603533-0ab9-4147-9675-3cf217c22a7e)


In **activity mode**, teachers can:

- Click on words, punctuation, glueing, or capitalization to modify the textbox at the bottom of the screen.
- Choose from activity types:
  - **Right or Wrong**
  - **Listen and Write**
  - **Remember and Write**
- Manage pages (create, delete, or modify).

Use the text maker to create sentences and activity types that will apear in the player mode

---

## Player

![image](https://github.com/user-attachments/assets/581f9ce5-0539-4c68-aaa4-10df8bf45531)

In **player mode**, students can complete the activities created by the teacher, aiming for the highest possible score.

---

## Technologies

- **NextJS**
- **Tailwind CSS**
- **Canvas API**
- **PostgreSQL**
- **Prisma**

---

## Database

The database stores information related to:

- Saved canvases
- Student attempts at activities

---

## Mathematics Behind Sentensi

All interactions and rendering are handled at a low level using the **Canvas API** (2D context). Words are positioned on **quadratic Bézier curves** with a single control point. Here’s how it works:

1. **Curve Calculations**:
   - Iteratively calculate the total length of the Bézier curve.
   - Determine the total size of the word along the curve.
   - Ensure equal spacing between letters for proper alignment.

2. **Transformations**:
   - All manipulations (stretch, scale, bend, etc.) are handled using **trigonometry** and **planar geometry**, ensuring that letter positions remain intact.

3. **Organic Line Drawing**:
   - Drawing is achieved by connecting multiple points with Bézier curves that intersect, creating a smooth, organic line effect while avoiding sharp turns.

### Note:
The entire rendering, interaction, and calculation process is implemented **natively** in the browser using the **Canvas API** and JavaScript events, without relying on external libraries.
