class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        auto left = lower_bound(nums.begin(), nums.end(), target);
        auto right = upper_bound(nums.begin(), nums.end(), target);

        if (left == nums.end() || *left != target)
            return {-1, -1};

        return {int(left - nums.begin()), int(right - nums.begin() - 1)};
    }
};
