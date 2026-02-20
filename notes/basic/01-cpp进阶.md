# 进阶
## STL之vector使用
###
 - vector在头文件vector中定义了一个vector模板。创建vector模板对象，使用<type>指出类型。vector模板使用动态内存分配，可用初始化参数来指出需要多少矢量
- vector<int> ratings(5);
- vector<int> candies(n, 1);
 - 创建一个名为 candies 的向量（动态数组）‌。
 - 该向量包含 n 个元素‌（n 是一个整数变量，通常表示孩子的数量）。
 - 所有元素的初始值都被设置为 1‌。

sort(开始位置, 结束位置, 排序规则); 排序规则 0升序，1降序--返回拍好顺序的内容，排序规则可以是一个函数（实现自定义的排序方式）
` 
#include <algorithm>
#include <vector>
// 按降序排序整数
bool cmp_desc(int a, int b) {
    return a > b; // true 表示 a 应该在 b 前面
}
std::vector<int> nums = {3, 1, 4, 1, 5};
std::sort(nums.begin(), nums.end(), cmp_desc); // 结果: {5, 4, 3, 1, 1}
// 按结构体成绩降序排序
struct Student { std::string name; int score; };
bool cmp_by_score(const Student& a, const Student& b) {
    return a.score > b.score;
}
`
 - vector<int>& ratings   一维整数向量的引用‌，通常用于表示一组‌离散的评分值‌或‌数值列表‌
   - vector<int> ratings = {4, 5, 3, 4, 5};
 - vector<vector<int>>& intervals  二维向量的引用‌，通常用于表示一组‌区间‌（interval）。每个内部的 vector<int> 包含两个整数，分别代表区间的起始点和结束点
    - vector<vector<int>> intervals = {{1,3}, {2,6}, {8,10}, {15,18}};
 - 排序：sort(intervals.begin(), intervals.end()); 默认按每个区间的起始点升序排列。










