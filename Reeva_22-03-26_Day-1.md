#DAY-1-3Sum(Intermediate)

<img width="1903" height="874" alt="image" src="https://github.com/user-attachments/assets/e14ed17c-e520-48f6-8162-5433d2a499dd" />
#Code

#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        vector<vector<int>> ans;
        sort(nums.begin(), nums.end());
        int n = nums.size();

        for(int i = 0; i < n - 2; i++) {
            if(i > 0 && nums[i] == nums[i - 1]) continue;

            int left = i + 1;
            int right = n - 1;

            while(left < right) {
                int sum = nums[i] + nums[left] + nums[right];

                if(sum < 0) left++;
                else if(sum > 0) right--;
                else {
                    ans.push_back({nums[i], nums[left], nums[right]});
                    left++;
                    right--;

                    while(left < right && nums[left] == nums[left - 1]) left++;
                    while(left < right && nums[right] == nums[right + 1]) right--;
                }
            }
        }

        return ans;
    }
};
