DAY-7-Increasing Triplet Subsequence
<img width="1899" height="808" alt="image" src="https://github.com/user-attachments/assets/f557e12d-9fce-44fa-93dc-c7bffb8d4ad4" />
#Code
class Solution {
public:
    bool increasingTriplet(vector<int>& nums) {
        int first = INT_MAX, second = INT_MAX;
        for (int num : nums) {
            if (num <= first) {
                first = num;
            } else if (num <= second) {
                second = num;
            } else {
                return true;
            }
        }
        return false;
    }
};
