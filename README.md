# Add-Two-Numbers-II
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        r1=[]
        r2=[]
        def add(root,r):
            while root:
                r.append(root.val)
                root=root.next
        add(l1,r1)
        add(l2,r2)
        r=[]
        c=0
        i=len(r1)-1
        j=len(r2)-1
        while i>=0 or j>=0 or c:
            if i>=0:
                a=r1[i]
            else:
                a=0
            if j>=0:
                b=r2[j]
            else:
                b=0
            s=a+b+c
            r.append(s%10)
            c=s//10
            i-=1
            j-=1
        
        head=ListNode(0)
        root=head
        for i in r[::-1]:
            root.next=ListNode(i)
            root=root.next
        return head.next
