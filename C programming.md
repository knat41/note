


http://www.cburch.com/cso/

https://www.alphacodingskills.com/c/c-format-specifiers.php


CS hidden class 

https://missing.csail.mit.edu/

Get bit 
https://github.com/greenteawarrior/C/tree/master/Chapter2-TypesOperatorsandExpressions

```c
#include <stdio.h>

int main(void){
	int base10, base2[16];
	int i = 0, j, r;
	printf("Enter base 10 : ");
	scanf("%d", &base10);
	while (base10 > 0){
		r = (base10 % 2);
		base2[i] = r;
		base10 = base10 / 8;
		i++;
	}
	for(j = i - 1; j >= 0; j--){
		printf("%d", base2[j]);
	}
	return 0;
}
```
