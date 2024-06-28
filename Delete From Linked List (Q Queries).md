```java
import java.util.*;

class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class LinkedList {
    Node head;

    LinkedList() {
        this.head = null;
    }

    void insert(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
        } else {
            Node temp = head;
            while (temp.next != null) {
                temp = temp.next;
            }
            temp.next = newNode;
        }
    }

    void deleteAtIndex(int index) {
        if (index == 0) {
            head = head.next;
            return;
        }
        Node temp = head;
        for (int i = 0; temp != null && i < index - 1; i++) {
            temp = temp.next;
        }
        if (temp == null || temp.next == null) {
            return;
        }
        temp.next = temp.next.next;
    }

    void printList() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        int q = scanner.nextInt();

        LinkedList list = new LinkedList();
        for (int i = 0; i < n; i++) {
            int data = scanner.nextInt();
            list.insert(data);
        }

        for (int i = 0; i < q; i++) {
            int index = scanner.nextInt();
            list.deleteAtIndex(index);
            list.printList();
        }
    }
}
```
