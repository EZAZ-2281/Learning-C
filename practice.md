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
