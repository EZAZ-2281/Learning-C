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
```
Using Python 
str = input("Enter a string: ")
new_str = ""

for i in str:
    if i != ' ':
        new_str += i

print("String after removing spaces: ", new_str)
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
### String Detection 
```
#include <stdio.h>

int main() {
    char input[100], output[100];
    int i = 0, j = 0;

    printf("Enter a string: ");
    gets(input); 

    while (input[i] != '\0') {
        if ((input[i] >= 'a' && input[i] <= 'z') || (input[i] >= 'A' && input[i] <= 'Z')) {
            output[j++] = input[i];
        }
        i++;
    }
    output[j] = '\0';

    if (output[0] != '\0') {
        printf("String part: %s\n", output);
    } else {
        printf("No String detected.\n");
    }

    return 0;
}
```
### Count number of '\\' or '\*' in an input 
```
txt = input("Enter input: ") 

count = 0 
for i in range(len(txt)): 
    if txt[i] == '\\': 
        count = count + 1
        
print(count) 
```
### Finding Same Pattern 
```
import re

# Initializing text and pattern
pattern=["Life","journey"]
s1="Life is a Journey not a destination"

# Iterating over the text to search for pattern
for i in pattern:
    print("Searching ",i)
    if(re.search(i,s1)):
        print("Found ",i, "in the string - ", s1)
    else:
        print(i," not found in the string - ", s1)   
 ```
 
### Valid or Invalid Identifier 
```
import re

identifier = input("Enter an identifier: ")

if re.match(r'^[a-zA-Z_]\w*$', identifier):
    print("Valid identifier")
else:
    print("Invalid identifier")
```
> The regular expression pattern r'^[a-zA-Z_]\w*$' matches an identifier that starts with an alphabetic character or an underscore, followed by zero or more alphanumeric characters or underscores.
