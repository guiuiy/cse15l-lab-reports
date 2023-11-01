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
```
