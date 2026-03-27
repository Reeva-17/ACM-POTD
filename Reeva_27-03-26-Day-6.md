#DAY-6-Check If N and Its Double Exist

<img width="1889" height="814" alt="image" src="https://github.com/user-attachments/assets/a1490099-67ed-45e9-b3b2-47e1cd025d03" />
#Code
class Solution {
public:
    bool checkIfExist(vector<int>& arr) {
        unordered_set<int> st;
        for (int num : arr) {
            if (st.count(2 * num) || (num % 2 == 0 && st.count(num / 2))) {
                return true;
            }
            st.insert(num);
        }
        return false;
    }
};
