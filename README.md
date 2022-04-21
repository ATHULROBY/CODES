# CODES
class node:
    def __init__(self,data):
        self.item=data
        self.ref=None
class linkedlist:
    def __init__(self):
        self.head=None
    def insert_at_beg(self,data):
        newnode=node(data)
        newnode.ref=self.head
        self.head=newnode
    def insert_at_end(self,data):
        newnode=node(data)
        if self.head is None:
            self.head=newnode
            return
        n=self.head
        while n.ref!=None:
            n=n.ref
        n.ref=newnode
    def insert_after_item(self,data,x):
        n=self.head
        while n!=None:
            if n.item==x:
                break
            n=n.ref
        newnode=node(data)
        newnode.ref=n.ref
        n.ref=newnode                    
    def printt(self):
        n=self.head
        while n!=None:
            print(n.item)
            n=n.ref
    def delete_from_begining(self):
        temp=self.head
        self.head=temp.ref
    def delete_from_end(self):
        if self.head is None:
            print("it is an empty list")
        n=self.head
        while n.ref.ref is not None:
            n=n.ref
        n.ref=None
        self.printt()
            
a=linkedlist()
a.insert_at_beg(3)
a.insert_at_beg(1)
a.printt()
            
