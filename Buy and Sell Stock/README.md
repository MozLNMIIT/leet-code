```
class Solution {
public:
    int maxProfit(vector<int>& prices) {
     
        int i, j, k, min = INT_MAX;
        int max = 0;
        k = prices.size();
        if(k==0)
        {
            return 0;
        }
        int sum;
        for(i=0; i<k; i++)
        {
            if(prices[i]<min)
            {
                min = prices[i];
            }
            else if(prices[i]-min>max)
            {
                max = prices[i]-min;
            }
        }
        
        return max;
    }
};
```
