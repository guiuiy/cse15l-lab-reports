# Lab Report 2
---
## Part 1: 
LinkedList Append Bug:

Failure-Inducing Input:
```
@Test
    public void appendTest2() {
        LinkedList test = new LinkedList();
        test.append(1);
        test.append(2);
        test.append(3);
        assertEquals("1 2 3 " , test.toString());
    }
```
Non-Failure-Producing Input:
```
    @Test
    public void appendTest1() {
        LinkedList test = new LinkedList();
        test.append(1);
        test.append(2);
        assertEquals("1 2 " , test.toString());
    }
```
Symptoms:

![Image](cse_15l_lab_images/LabReport3Part1Img1.png)

Bug:

Before:
```
public void append(int value) {
        if(this.root == null) {
            this.root = new Node(value, null);
            return;
        }
        // If it's just one element, add if after that one
        Node n = this.root;
        if(n.next == null) {
            n.next = new Node(value, null);
            return;
        }
        // Otherwise, loop until the end and add at the end with a null
        while(n.next != null) {
            n = n.next;
            n.next = new Node(value, null);
        }
    }
```
After:
```
    public void append(int value) {
        if(this.root == null) {
            this.root = new Node(value, null);
            return;
        }
        // If it's just one element, add if after that one
        Node n = this.root;
        if(n.next == null) {
            n.next = new Node(value, null);
            return;
        }
        // Otherwise, loop until the end and add at the end with a null
        while(n.next != null) {
            n = n.next;
        }
        n.next = new Node(value, null);
    }
```
The fix was to move the `n.next - new Node(value, null);` statement outside the while loop. When it was inside the while loop, as we iterate through the list, we would keep on adding onto the list, so we would never reach the end. Moving the statement outside the loop would make it so that we would only add onto the list once we reach the end and stop iterating.
