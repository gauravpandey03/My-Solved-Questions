/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* reverseBetween(ListNode* head, int left, int right) {
        vector<int > v1;
        ListNode* temp =head;
        while(temp!=NULL){
            v1.push_back(temp->val);
            temp = temp->next;
        }
        reverse(v1.begin()+left-1,v1.begin()+right);
        temp=head ;
        int n =v1.size();
        int i=0;
        while(temp!=NULL){
            temp->val=v1[i];
            temp = temp->next;
            i++;
        }

        return head;
    }
};