class GfG
{
    Node flatten(Node root)
    {
	// Your code here

 Node first = root.next;

 while(first!=null){

     Node sec = first;

     first = first.next;

     root = merge(root,sec);

 }

 return root;

    }

    Node merge(Node one , Node two){

        Node head = new Node(0);

        Node curr = head;

        while(one!= null && two!=null){

            if(one.data<two.data){

                curr.bottom = one;

                one = one.bottom;

            }

            else{

                curr.bottom = two;

                two = two.bottom;

            }

            curr = curr.bottom;

        }

        if(one!=null){

            curr.bottom = one;

        }

         if(two!=null){

            curr.bottom = two;

        }

        return head.bottom;

    }

}
