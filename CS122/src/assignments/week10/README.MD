public interface StackADT {  

   

   public void push(Object val);


   public Object pop();
  

   public boolean isEmpty();

  
   public boolean isFull();

}

public class LinkedStack implements StackADT {

   private Node top; 

   public LinkedStack() {

       this.top = null;

   }

   public void push(Object val) {

       Node node = new Node(val);

       node.setNext(top);

       top = node;

   }

   public Object pop() {

       Node temp = top;

       top = top.getNext();

      return temp.getElement();

   }

   public boolean isEmpty() {

       return (top == null);  

   }

   
   public boolean isFull() {


       return false;

   }

}


public class Node {

   private Node next;

   private Object element;


   public Node() {

       next = null;

       element = null;

   }

   public Node(Object element)   {

       next = null;

       this.element = element;

   }

   public Node getNext() {

       return next;

   }

   public void setNext(Node node) {

       next = node;

   }

   public Object getElement() {

       return element;

   }

   public void setElement(Object element) {

       this.element = element;

   }

}


public class StackTest {

   public static void main(String[] args)   {

       StackADT stack = new LinkedStack();

       for (int i = 0; i < 10; i++) {

           stack.push(i * 2);

       }

       while (!stack.isEmpty()) {

           System.out.print(stack.pop() + " ");
       }  

       System.out.println();


       for (int i = 1; i <= 6; i++) {

           stack.push(i);

       }  

       while (!stack.isEmpty()) {

           System.out.print(stack.pop() + " ");
       }  
       System.out.println();

   }

}
