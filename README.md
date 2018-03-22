# repository1
Myhomework
main.c 的源代码如下：（要求通过实际运行调试，程序中包含适当的注释）
#include <stdio.h>  
int main(void)
 {
     char buf[128] = {0};  // 这里要都初始化为0
     FILE *fp = fopen("a.txt", "r");
     while (0 != fread(buf, 1, 127, fp))   // 这里不能读满，最大只能用127      {
         printf("%s",  buf);
         memset(buf, 0, 128);      // 这里每次都要清0
    }
fclose(fp);
return 0;
}

Makefile内容如下：
main:main.o
gcc -o main main.c
