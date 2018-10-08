```
class Solution {
public:
    int maxIncreaseKeepingSkyline(vector<vector<int>>& grid) {
        
        int i, j, k;
        int maxr, maxc, sum = 0;
        int r = grid.size();
        int c = grid[0].size();
        int row[r], col[c];
        
        for(i=0; i<r; i++)
        {
            maxr = -1;
            for(j=0; j<c; j++)
            {
                if(grid[i][j]>=maxr)
                {
                    maxr=grid[i][j];
                }
            }
            row[i]=maxr;
        }
        
        for(i=0; i<c; i++)
        {
            maxc = -1;
            for(j=0; j<r; j++)
            {
                if(grid[j][i]>=maxc)
                {
                    maxc=grid[j][i];
                }
            }
            col[i]=maxc;
        }
        
        for(i=0; i<r; i++)
        {
            for(j=0; j<c; j++)
            {
                if(row[i]<=col[j])
                {
                    sum+=row[i]-grid[i][j];
                }
                else
                {
                    sum+=col[j]-grid[i][j];
                }
            }
        }
        
        return sum;
        
    }
};
```
