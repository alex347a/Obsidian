```
// Checks if a string is a palindrome ignoring spaces and punctuation
bool isStrictPalindrome(string s) {
    int left = 0, right = s.length() - 1;
    while (left < right) {
        if (s[left++] != s[right--]) {
            return false;
        }
    }
    return true;
}

// Checks if two strings are anagrams (case insensitive)
bool areAnagrams(string s1, string s2) {
    if (s1.length() != s2.length()) return false;
    
    int count[256] = {0};
    
    for (char c : s1) count[tolower(c)]++;
    for (char c : s2) count[tolower(c)]--;
    
    for (int i = 0; i < 256; i++) {
        if (count[i] != 0) return false;
    }
    return true;
}

// Checks for balanced brackets of different types: (), [], {}
bool areBracketsBalanced(const string& expr) {
    stack<char> s;
    
    for (char c : expr) {
        if (c == '(' || c == '[' || c == '{') {
            s.push(c);
        } else if (c == ')' || c == ']' || c == '}') {
            if (s.empty()) return false;
            
            char top = s.top();
            s.pop();
            
            if ((c == ')' && top != '(') || 
                (c == ']' && top != '[') || 
                (c == '}' && top != '{')) {
                return false;
            }
        }
    }
    return s.empty();
}

// Finds the first occurrence of a number in an unsorted array
int findFirstOccurrence(const int arr[], int size, int target) {
    for (int i = 0; i < size; i++) {
        if (arr[i] == target) {
            return i;
        }
    }
    return -1; // Not found
}

// Finds the first occurrence in a sorted array with duplicates
int findFirstInSorted(const int arr[], int size, int target) {
    int left = 0, right = size - 1;
    int result = -1;
    
    while (left <= right) {
        int mid = left + (right - left) / 2;
        
        if (arr[mid] == target) {
            result = mid;
            right = mid - 1; // Continue searching left half
        } else if (arr[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return result;
}

// Checks if a number is prime
bool isPrime(int n) {
    if (n <= 1) return false;
    if (n == 2) return true;
    if (n % 2 == 0) return false;
    
    for (int i = 3; i * i <= n; i += 2) {
        if (n % i == 0) return false;
    }
    return true;
}

// Computes the greatest common divisor using Euclidean algorithm
int gcd(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

// Checks if a string is a valid number (integer)
bool isNumeric(const string& s) {
    if (s.empty()) return false;
    
    size_t i = 0;
    if (s[0] == '-') {
        if (s.length() == 1) return false;
        i = 1;
    }
    
    for (; i < s.length(); i++) {
        if (!isdigit(s[i])) {
            return false;
        }
    }
    return true;
}

// Checks if a string is a valid palindrome considering alphanumeric only
bool isAlphanumericPalindrome(const string& s) {
    int left = 0, right = s.length() - 1;
    
    while (left < right) {
        while (left < right && !isalnum(s[left])) left++;
        while (left < right && !isalnum(s[right])) right--;
        
        if (tolower(s[left]) != tolower(s[right])) {
            return false;
        }
        
        left++;
        right--;
    }
    return true;
}

vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> numMap;
    for (int i = 0; i < nums.size(); i++) {
        int complement = target - nums[i];
        if (numMap.count(complement)) {
            return {numMap[complement], i};
        }
        numMap[nums[i]] = i;
    }
    return {}; // No solution found
}

int reverse(int x) {
    int rev = 0;
    while (x != 0) {
        int pop = x % 10;
        x /= 10;
        if (rev > INT_MAX/10 || (rev == INT_MAX/10 && pop > 7)) return 0;
        if (rev < INT_MIN/10 || (rev == INT_MIN/10 && pop < -8)) return 0;
        rev = rev * 10 + pop;
    }
    return rev;
}

bool isValid(string s) {
    stack<char> st;
    for (char c : s) {
        if (c == '(' || c == '{' || c == '[') {
            st.push(c);
        } else {
            if (st.empty()) return false;
            char top = st.top();
            st.pop();
            if ((c == ')' && top != '(') || 
                (c == '}' && top != '{') || 
                (c == ']' && top != '[')) {
                return false;
            }
        }
    }
    return st.empty();
}

bool isPalindrome(int x) {
    if (x < 0 || (x % 10 == 0 && x != 0)) {
        return false;
    }
    
    int reverted = 0;
    while (x > reverted) {
        reverted = reverted * 10 + x % 10;
        x /= 10;
    }
    
    return x == reverted || x == reverted / 10;
}

int removeDuplicates(vector<int>& nums) {
    if (nums.empty()) return 0;
    
    int k = 0;
    for (int i = 1; i < nums.size(); i++) {
        if (nums[i] != nums[k]) {
            nums[++k] = nums[i];
        }
    }
    return k + 1;
}

int maxSubArray(vector<int>& nums) {
    int maxSum = nums[0];
    int currentSum = nums[0];
    
    for (int i = 1; i < nums.size(); i++) {
        currentSum = max(nums[i], currentSum + nums[i]);
        maxSum = max(maxSum, currentSum);
    }
    
    return maxSum;
}

void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
    int i = m - 1, j = n - 1, k = m + n - 1;
    
    while (i >= 0 && j >= 0) {
        if (nums1[i] > nums2[j]) {
            nums1[k--] = nums1[i--];
        } else {
            nums1[k--] = nums2[j--];
        }
    }
    
    while (j >= 0) {
        nums1[k--] = nums2[j--];
    }
}

int search(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;
    
    while (left <= right) {
        int mid = left + (right - left) / 2;
        
        if (nums[mid] == target) {
            return mid;
        } else if (nums[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    
    return -1;
}

int climbStairs(int n) {
    if (n == 1) return 1;
    
    int first = 1, second = 2;
    for (int i = 3; i <= n; i++) {
        int third = first + second;
        first = second;
        second = third;
    }
    
    return second;
}

int maxProfit(vector<int>& prices) {
    int minPrice = INT_MAX;
    int maxProfit = 0;
    
    for (int price : prices) {
        if (price < minPrice) {
            minPrice = price;
        } else if (price - minPrice > maxProfit) {
            maxProfit = price - minPrice;
        }
    }
    
    return maxProfit;
}

bool hasDigit(string s) {
    for (char c : s) {
        if (isdigit(c)) {
            return true;
        }
    }
    return false;
}

char findMaxASCIIChar(const string& str) 
{
    char maxChar = str[0];
    
    for (char c : str) 
    {
        if (c > maxChar) 
        {
            maxChar = c;
        }
    }
    
    return maxChar;
}
```