# 자료구조

## Basic

- Queue
    - FIFO
- Stack
    - LIFO
- Linked List
    - Array의 단점인 기본사이즈를 보완
    - [TODO](https://github.com/cptbong/TBL/blob/main/Algo/ImplementationsOfJavaList.md). 매일 ArrayList만 쓰지 말고 JAVA의 List를 구현한 녀석들 확인
    - Node, Pointer - Node : Data + Pointer - Pointer : 이전, 다음 Node정보

- Linked List 구현
```java
public class LinkedList {
    public static void main(String[] args) {
        Node node1 = new Node("First node");
        Node node2 = new Node("Second node");
        Node node3 = new Node("Third node");
        node1.setPointer(node2);
        node2.setPointer(node3);

        System.out.printf("%s, %s\n", node1.getData(), System.identityHashCode(node1.getPointer()));
        System.out.printf("%s, %s\n", node2.getData(), System.identityHashCode(node2.getPointer()));
        System.out.printf("%s, %s\n", node3.getData(), System.identityHashCode(node3.getPointer()));
    }
}

class Node {
private String data;
private Node pointer;

    public Node(String data) {
        this.data = data;
    }

    public void setPointer(Node pointer) {
        this.pointer = pointer;
    }

    public String getData() {
        return data;
    }

    public Node getPointer() {
        return pointer;
    }

}
```    

```java
public class LinkedList {
    public static void main(String[] args) {
        Node node1 = new Node("First");
        node1.add("Second");
        node1.add("Third");
        node1.add("Fourth");
        node1.allPrint();
    }
}

class Node {
    private String data;
    private Node next = null;

    public Node(String data) {
        this.data = data;
    }

    public void add(String data) {
        Node end = new Node(data);
        Node current = this;
        while (current.next != null) {
            current = current.next;
        }
        current.next = end;
    }

    public void allPrint() {
        Node current = this;
        while (current.next != null) {
            System.out.println(current.data);
            current = current.next;
        }
        System.out.println(current.data);
    }
}
```


- ...

