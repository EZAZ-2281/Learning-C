### Remove Black Space
```
#include <stdio.h>

int main()
{
    char str[100], new_str[100];
    int i, j;
    
    printf("Enter a string: ");
    gets(str);
    
    for(i = 0, j = 0; str[i]; i++)
    {
        if(str[i] != ' ')
        {
            new_str[j] = str[i];
            j++;
        }
    }
    new_str[j] = '\0';
    
    printf("String after removing spaces: %s", new_str);
    
    return 0;
}
```

### Single and Multi-Line Commnet 
```
#include <stdio.h>

int main()
{
    char str[1000];
    int i, single_flag = 0, multi_flag = 0;
    
    printf("Enter a string: ");
    gets(str);
    
    for(i = 0; str[i]; i++)
    {
        if(str[i] == '/' && str[i+1] == '/')
        {
            single_flag = 1;
            printf("Single-line comment detected: ");
            i += 2;
            while(str[i] != '\0')
            {
                printf("%c", str[i]);
                i++;
            }
            printf("\n");
        }
        else if(str[i] == '/' && str[i+1] == '*')
        {
            multi_flag = 1;
            printf("Multi-line comment detected: ");
            i += 2;
            while(str[i] && str[i+1])
            {
                if(str[i] == '*' && str[i+1] == '/')
                {
                    //printf("*/");
                    i += 2;
                    break;
                }
                printf("%c", str[i]);
                i++;
            }
            if(str[i] && !str[i+1])
            {
                printf("%c", str[i]);
            }
            printf("\n");
        }
    }
    if(!single_flag && !multi_flag)
    {
        printf("No comment detected.\n");
    }
    return 0;
}
```
