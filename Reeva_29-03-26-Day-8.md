#DAY-8-Reverse Nodes in k-Group

<img width="1867" height="786" alt="image" src="https://github.com/user-attachments/assets/47c2e8fd-927f-4d37-b920-389678edc23a" />
#CODE

class Solution {
public:
    ListNode* reverseKGroup(ListNode* head, int k) {
        ListNode* curr = head;
        for (int i = 0; i < k; i++) {
            if (!curr) return head;
            curr = curr->next;
        }
        
        ListNode* prev = nullptr;
        curr = head;
        for (int i = 0; i < k; i++) {
            ListNode* next = curr->next;
            curr->next = prev;
            prev = curr;
            curr = next;
        }
        
        head->next = reverseKGroup(curr, k);
        return prev;
    }
};
