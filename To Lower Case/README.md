```
class Solution {
public:
    string toLowerCase(string str) {
        int i = 0;
        while (str[i])
        {
            if (isupper(str[i]))
            {
                str[i]=tolower(str[i]);
            }
            i++;
        }
        return str;
    }
};
```
