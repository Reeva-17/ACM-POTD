#DAY-5- Move Zeroes(EASY)
<img width="1829" height="776" alt="image" src="https://github.com/user-attachments/assets/f79388cd-7f3c-4623-9607-ed3f9e5a3e00" />
#CODE
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int j = 0;

        for(int i = 0; i < nums.size(); i++){
            if(nums[i] != 0){
                swap(nums[i], nums[j]);
                j++;
            }
        }
    }
};
