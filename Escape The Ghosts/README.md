```
class Solution {
public:
    bool escapeGhosts(vector<vector<int>>& ghosts, vector<int>& target) {
        
        int i, j, k;
        int g = ghosts.size();
        int c[g]={0};
        int flag = 1;
        int res = 0;
        if(target[0]<0)
        {
            res+= (-1)*target[0];
        }
        else
        {
            res+= target[0];
        }
        
        if(target[1]<0)
        {
            res+= (-1)*target[1];
        }
        else
        {
            res+= target[1];
        }
        
        for(i=0; i<g; i++)
        {
            if(target[0]>=ghosts[i][0])
            {
                c[i]+= target[0] - ghosts[i][0];
            }
            else
            {
                c[i]+= ghosts[i][0] - target[0];
            }

            if(target[1]>=ghosts[i][1])
            {
                c[i]+= target[1] - ghosts[i][1];
            }
            else
            {
                c[i]+= ghosts[i][1] - target[1];
            }
        }
        
        for(i=0; i<g; i++)
        {
            if(res>=c[i])
            {
                return false;
            }
            else
            {
                flag = 1;
            }
        }
        
        if(flag)
        {
            return true;
        }
    }
};
```
