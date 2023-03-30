#informatica

---

# Imports

```java
import java.util.*;
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
```

# Objects

- `JFrame`
- `JPanel`
- `JButton`
- `JLabel`
- `JTextField`
- `JTextArea`
- `ArrayList ( Maybe? )`

# Snippets

## Custom JFrame

```java
class CustomFrame extends JFrame {

    public CustomFrame(String title) {
        super(title);
        setSize(500, 500);
        setLocationRelativeTo(null);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setVisible(true);
    }

    public void refresh(){
        setVisible(false);
        setVisible(true);
    }
}
```

## Custom JPanel + Paint method

**Panel:**

```java
class CustomPanel extends JPanel {

    public CustomPanel() {
        super();
        setBackground(Color.{any});
    }

    public void paint(Graphics g) {
        super.paint(g);
        Graphics2D g2 = (Graphics2D) g;
        //code
    }
}
```

**Paint methods:**

- `{ JPanel, JFrame }.repaint()`
- `Graphics2D.setColor( Color.{ any } )`
- `Graphics2D.draw( { Rect, Oval, RoundRect } )`
- `Graphics2D.fill( { Rect, Oval, RoundRect } )`
- - `*Rect( x, y, width, height )`
- - `*Oval( x, y, width, height )`
- - `*RoundRect( x, y, width, height, arcWidth, arcHeight )`

## Custom JButton

**Button:**

```java
class CustomButton extends JButton {

    public CustomButton(String title) {
        super(title);

        addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                //code
            }
        });
    }
}
```

**EventListener:**

```java
JButton.addActionListener(new ActionListener() {
    public void actionPerformed(ActionEvent e) {
        //code
    }
});
```

## Set a layout

**Layout syntax:**

```java
{ JFrame, JPanel }.setLayout(new Layout(args));
```

**Layouts:**

- `GridLayout( row , cols )`
- `BoxLayout( JPanel, BoxLayout.{ Y_AXIS , X_AXIS } )`
