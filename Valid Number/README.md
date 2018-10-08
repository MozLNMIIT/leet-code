```
class Solution {
public:
    bool isNumber(string s) {
        
        int f = 1, b = 1, flag = 1;
        long i, j, k;
        long temp = s.length();
        
        i = 0;
        k=temp-1;
        while(s[i]==' ')
        {
            i++;
        }
        while(s[k]==' ')
        {
            k--;
        }
        
        if(i==temp)
        {
            return false;
        }
        
        if(s[i]=='-' || s[i]=='+')
        {
            i++;
        }
        
        if(s[i]=='.' && i+1==temp || s[i]=='.' && isdigit(s[i+1])!=1)
        {
            return false;
        }
        
        if(s[i]=='.')
        {
            flag = 0;
            i++;
        }
        
        for(; i<temp; i++)
        {
            if(s[i]==' ')
            {
                if(i<k)
                {
                    return false;
                }
            }
            else if(s[i]=='.')
            {
                if(flag==1)
                {
                    flag = 0;
                    if( ((i-1)<0 && (i+1)==temp) || isdigit(s[i-1])!=1 && s[i-1]!=' ')
                    {
                        return false;
                    }
                }
                else
                {
                    return false;
                }
                    
            }
            else if(s[i]=='e')
            {
                if(b==1)
                {
                    b=0;
                    flag=0;
                    if((i-1)<0 || (i+1)==temp)
                    {
                      
                        return false;
                    }

                    if(s[i-1]=='.')
                    {
                        if(isdigit(s[i-2])!=1)
                        {
                                                 
                            return false;
                        }
                    }
                    else if(isdigit(s[i-1])!=1)
                    {
                                               
                        return false;
                    }
                    
                    if( ((s[i+1]=='+' || s[i+1]=='-')) &&  (i+2)<temp)
                    {
                        i++;
                    }
                    else if(isdigit(s[i+1])!=1)
                    {
                                               
                        return false;
                    }
                    
                    
                }
                else
                {
                                           
                    return false;
                }
            }
            else if(isdigit(s[i]))
            {
                f=0;
            }
            else
            {
                                       
                return false;
            }
        }
        
        return true;      
        
    }
};
```
