# C-p83-C-2-
C语言学习笔记 p83 初识C语言
#include<stdio.h>
int main()
{
    int num1=0;
    int num2=0;
    
    scanf("%d%d",&num1,&num2)
    sum=num1+num2;
    printf("sum=%d\n",sum);
    return 0;
}


常量分为：
1.字面常量
2.const修饰的常量
3.#define定义和标识符常量
4.枚举常量
int main()
{
    int num=4;
    //字面常量
    300；
    3.14；
    
    
    //const-常属性
    const int n=10;//n是变量，但是又有常属性，所以n是常变量
    int arr[10]={0};
    //const修饰的常变量
    constn int num=10;
      return 0;
}
    #define定义的标识符常量
    #define MAX 10
    int main()
    {
        int arr[MAX]={0};
        printf("%d\n",MAX);
        return 0;
    }
 
     枚举常量
     枚举常量关键字-enum
     enum Sex
     {
        MALE,
        FEMALE,
        SECRET
     };
     //MALE,FEMALE,SECRET为枚举常量
      int main()
     {
        //enum Sex s=FEMALE;
        printf("%d\n",MALE);//0
        printf("%d\n",FEMALE);//1
        printf("%d\n",SECRET);//2
        //每个枚举常量都是有值的，都是无法改变的
        return 0;
     }

enum Color
{
    RED,
    YELLOW,
    BLUE
};
int main()
{
    enum Color color=BLUE;
    color=YELLOW;//color这个变量是可以改变的
    //但是颜色代表的数字是不可以改变的
    return 0;
}


//字符串类型
int main()
{
    "abcdef";
    "hello world";
    //这些由双引号引起来的字符串叫字符串
    “”//空字符串
    return 0;
}

int main()
{
    char arr1[]="abc";//数组
    char arr2[]={'a','b','c'};
    printf("%s\n",arr1);
    printf("%s\n",arr2);
    //以上的区别是，arr1比arr2多了一个\0，arr2编不过去，如果给arr2加一个\0，输出结果则一致
    return 0;
}


int main()
{
    char arr1[]="abc";
    char arr2[]={'a','b','c'};
    printf("%d\n",strlen(arr1));//strlen-string length-计算字符串长度，输出为3
    printf("%d\n",strlen(arr1))//输出为随机数
    return 0;
}


转义字符：转变原来的意思
int main()
{
    printf("abc\n");//\n把原来的字符n的意思转变了，\n成了换行符
    return 0;
}

int main()
{
    printf("c:\test")// \t则转换成了水平制表符
    return 0;
}

int main()
{
    printf("%d\n",strlen("c:\test\32\test.c"));
    //\32-32是2个8进制数字
    //32作为8进制的那个十进制数字，作为ASCII码值，对应的字符
    //32-10进制 26->作为ASCII码值代表的字符
    return 0;
}

\ddd  ddd表示1-3个八进制的数字
\xdd  dd表示2个十六进制的数字


//选择语句
int main()
{
    input=0;
    printf("加入world\n");
    printf("你要好好学习吗？（1/0）>：“）；
    scanf("%d", &input);1/0
    if(input==1)
    {
        printf("好offer\n");
    }
    else
    {
        printf("卖红薯“\n);
    }
    return 0;
}

C语言包含3种循环
1.while循环
2.for循环
3.do...while语句

int main()
{
    printf("加入比特\n");
    while(line<20000)
    {
        printf("敲一行代码:%d\n");
        line++;
    }
    if(line>=20000)
        printf("好offer\n");
    return 0;
}


函数
int Add(int x,int y)//自定义函数，另外一种为库函数，例如printf
{
    int z=x+y;
    return z;
}
int main()
{
    int num1=10;
    int num2=20;
    int sum=0;
    int a=100;
    int b=200;
    sum=Add(num1,num2);
    sum=Add(a,b);
    sum=Add(2,3);
    printf("sum=%d\n",sum);
    return 0;
}


数组
int main()
{
    int arr[10]={1,2,3,4,5,6,7,8,9,10};//定义一个存放10个整形数字的数组
    char ch[20];
    float arr2[5];
    return 0;
}
//数组的第一个元素的下标规定为0，一个数组的第n个元素的下标为n-1
//下标的设计用来访问元素
int main()
{
    int arr[10]={1,2,3,4,5,6,7,8,9,10}//定义一个存放10个整数数字的数组
    int i=0;
    while(i<10)
    {
        printf("%d",arr[i]);
        i++;
    }
    return 0;
}


操作符
算数操作符
+-*\%（取模得余数）
移位操作符
移位移的是二进制操作符
//<<左移
//>>右移
int a=1;
int b=a<<1;
//左移左边丢弃右边补0
//00000000000000000000000000000001
//左移后
//00000000000000000000000000000010
//左移相当于*2
//注：这里变的是b，a是不会变的


位操作（二进制位）
//&按位与
//｜按位或
//^按位异或
int a=3;
int b=5;
int c=a&b;
//3的二进制序列为011
//5的二进制序列为101
//按位与：只要有一个为假则位假，只有两个都为真才为真
//所以c为1 001

//按位或：只要有一个为真则为真
int c=a|b
c=7 111
//按位异或：按位异或的二进制位相同，则为0，不同则为1
所以a^b=6 110


赋值操作符
int main()
{
   //=赋值；==判断相等
   a=a+10;
   a+=10;
   //这两种方法完全一样
   a=a-20;
   a-=20;
   //也一样
   a=a&2;
   a&=2;
   //复合赋值符
   //+=，-=，/=，%=，>>=, <<=, &=, |=, ^=
    return 0;
}


单目操作符
单目操作符相对应还有双目三目操作符
int main()
{
    //C语言中0为假；0之外一切数为真
    int a=0;
    printf("%d\n",a);
    printf("%d\n",!a);
    return 0;
}
C中!位逻辑反操作符，把假变为真，真变为假
int main()
{
    int a=10;
    //sizeof计算的是变量/类型所占空间的大小，单位是字节
    printf("%d\n",sizeof(a));
    printf("%d\n",sizeof(int));
    printf("%d\n",sizeofa);
    printf("%d\n",sizeof int);//注：int的括号不可省略
    return 0;
}

int main()
{
    int sz=0;
    int arr[10]={0};//10个整形元素的数组
    //10*sizeof（int）=40
    printf("%d\n",sizeof(arr));
    //计算数组元素的个数
    //个数=数组总大小/每个元素大小
    sz=sizeof(arr)/sizeof(arr[0]);
    printf("sz=%d\n",sz);
    return 0;
}
