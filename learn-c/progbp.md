```c
//阶乘
int loop(int x)
{
	for (int a = x; a > 1;)
	{
		return loop(a - 1) * a;
	}
}

int loop_2(int x)
{
	if (x > 1)
		return loop_2(x - 1) * x;
	else
		return 1;
}
```