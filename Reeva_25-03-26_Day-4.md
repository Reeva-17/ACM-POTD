#DAY-4-Two Sum II - Input Array Is Sorted(Intermediate)

<img width="1904" height="883" alt="image" src="https://github.com/user-attachments/assets/9fdce3ec-392c-46ac-a9cd-ef490b184e67" />
#CODE
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
       
        int left = 0, right = numbers.size() - 1;
        while (left < right) {
            int sum = numbers[left] + numbers[right];
            if (sum == target) return {left + 1, right + 1};
            else if (sum < target) left++;
            else right--;
        }
        return {};
    }
};
