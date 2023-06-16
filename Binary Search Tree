package com.vallamgurubabu;

import java.util.ArrayList;

public class BinaryTree {


    private class Node{
        private int value;
        private Node leftchild;
        private Node rigthchild;
        public Node(int value){
            this.value=value;
        }
        @Override
        public String toString(){
            return "Node="+value;
        }
    }
    private Node root;

    //1.insert a value in a tree
    public void insert(int value){
        var node=new Node(value);
        if (root==null){
            root=node;
            return;
        }
        var current =root;
        while (true){
            if (current.value>value){
                if (current.leftchild==null){
                    current.leftchild=node;
                    break;
                }
                current= current.leftchild;
            }else {
                if (current.rigthchild==null){
                    current.rigthchild=node;
                    break;
                }
                current=current.rigthchild;
            }
        }
    }

    //2.finding element in a tree
    public boolean Find(int value){
        var current= root;
        while(current!=null){
            if (value<current.value){
                current=current.leftchild;
            }else if (value>current.value){
                current=current.rigthchild;
            }else{
                return true;
            }
        }
        return false;
    }

    //3.Depth First Search
    public void traversePreOrder(){
        System.out.println("");
        System.out.println("In pre traversal:-");
        traversePreOrder(root);
    }
    private void traversePreOrder(Node root){

        //root-->print
        //left-->print
        //right-->print
        if (root==null)
            return;

        System.out.print("\t"+root.value);
        traversePreOrder(root.leftchild);
        traversePreOrder(root.rigthchild);
    }
    public void traverseInOrder(){
        System.out.println("");
        System.out.println("In order traversal:-");
        traverseInOrder(root);
    }
    private void traverseInOrder(Node root){
        //left-->print
        //root-->print
        //right-->print
        if (root==null)
            return;

        traversePreOrder(root.leftchild);
        System.out.print("\t"+root.value);
        traversePreOrder(root.rigthchild);
    }
    public void traversePostOrder(){
        System.out.println("");
        System.out.println("post order traversal:-");
        traversePostOrder(root);
    }
    private void traversePostOrder(Node root){

        //left-->print
        //right-->print
        //root-->print
        if (root==null)
            return;

        traversePreOrder(root.leftchild);
        traversePreOrder(root.rigthchild);
        System.out.print("\t"+root.value);
    }

    //4.height of a tree
    public int height(){
        return height(root);
    }
    private int height(Node root){
        if (root==null)
            return -1;
        if (isLeaf(root))
            return 0;
        return 1+Math.max(
                height(root.leftchild),
                height(root.rigthchild));
    }

    //5.minimum value from a tree
    public int min() {
        if (root==null)
            throw new IllegalArgumentException();
        var current = root;
        var last = current;
        while (current != null){
            last = current;
        current = current.leftchild;

        }

        return last.value;
    }
    private int min(Node root){
        if (isLeaf(root))
            return root.value;

        var left=min(root.leftchild);
        var right=min(root.rigthchild);

        return Math.min(Math.min(left,right),root.value);
    }

    //6.find leaf Node in a tree
    private boolean isLeaf(Node root){

        return root.leftchild==null && root.rigthchild==null;

    }

    //7.Compare two tree
    public boolean equals(BinaryTree other){
        if (other==null)
            return false;
        return equals(root,other.root);
    }
    private boolean equals(Node first,Node second){
        if (first==null&&second==null)
            return true;
        if (first!=null&&second!=null)
            return first.value==second.value
                    && equals(first.leftchild,second.leftchild)
                    && equals(first.rigthchild,second.rigthchild);

        return false;
    }

    //8.validating BinarySearch tree.
    public boolean isBinaryTree(){
      return isBinaryTree(root,Integer.MIN_VALUE,Integer.MAX_VALUE);
    }
    private boolean isBinaryTree(Node root,int min,int max){
        if (root==null)
            return true;
        if (root.value<min||root.value>max)
            return false;
        return isBinaryTree(root.leftchild,min,root.value-1)
                &&isBinaryTree(root.rigthchild,root.value+1,max);
    }

    //9.swap the nodes left to right
    public void swapRoot(){
        var temp =root.leftchild;
        root.leftchild= root.rigthchild;
        root.rigthchild=temp;
   }

   //10.Nodes at k Distance from the Root
    public ArrayList<Integer> getNodeAtDistance (int distance){
        var list=new ArrayList<Integer>();
       getNodesAtDistance(root,distance,list);
        return list;
    }
    private void getNodesAtDistance(Node root,int distance,ArrayList<Integer> list){
        if (root==null) {
            return;
        }
        if (distance==0){
            list.add(root.value);
            return;
        }
        getNodesAtDistance(root.leftchild,distance-1,list);
        getNodesAtDistance(root.rigthchild,distance-1,list);
    }

    //11.breadth first Search or Level order Traversal
    public void LevelOrder(){

        for (int i=0;i<=height();i++){
            var list=getNodeAtDistance(i);
            for (var item:list)
                System.out.println(item);
        }
    }
}


