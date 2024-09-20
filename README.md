class Solution {
    public void rotate(int[] nums, int k) {
        int n = nums.length;  // 得到数组长度
        k = k % n;  // 确保 k 不大于数组长度
        int[] temp = new int[n];  // 创建一个临时数组存储轮转后的结果
        
        // 轮转：将最后的 k 个元素放到数组的开头
        for (int i = 0; i < k; i++) {
            temp[i] = nums[n - k + i];  // 将 nums 的最后 k 个元素移到 temp 开头
        }
        
        // 轮转：将前面的 n-k 个元素顺序向右移动 k 个位置
        for (int i = k; i < n; i++) {
            temp[i] = nums[i - k];  // 将 nums 的前 n-k 个元素移到 temp 的后面
        }
        
        // 把临时数组 temp 的内容复制回原数组 nums
        for (int i = 0; i < n; i++) {
            nums[i] = temp[i];
        }
    }
}
