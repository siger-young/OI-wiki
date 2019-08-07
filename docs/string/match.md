## 字符串匹配问题

字符串匹配问题分为好多类：

### 单串匹配

一个模式串 (pattern)，一个待匹配串，找出前者在后者中的所有出现位置

### 多串匹配

多个模式串，一个待匹配串（多个待匹配串还用说，直接连起来）

直接当做单串匹配肯定是可以的，但是效率不够高

### 匹配一个串的任意后缀

### 匹配多个串的任意后缀

## 暴力做法

对于每个位置，尝试对模式串和待匹配串进行比对

（伪代码）

```text
match(char *a, char *b, int n, int m) {
	ans = new vector();
	for (i = 0; i < n - m + 1; i++) {
		for (j = 0; j < m; j++) {
			if (a[i + j] != b[j]) break;
		}
		if (j == m) ans.push_back(i);
	}
	return ans;
}
```

时间复杂度分析：

最坏时间复杂度是 $O(nm)$ 的，

最好是 $O(n)$ 的。

如果字符集的大小大于 1（有至少两个不同的字符），平均时间复杂度是 $O(n)$ 的。

## Hash 的方法

参见 [Hash](/string/hash) 

## KMP 算法

参见 [KMP](/string/prefix-function/#knuth-morris-pratt) 
