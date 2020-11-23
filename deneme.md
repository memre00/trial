#include <stdlib.h>
#include <stdio.h>
#include <math.h>

int maxValue(int num1, int num2, int num3, int num4, int num5, int num6)
{
	int max;
	if (num1 <= num2)
	{
		max = num2;
	}
	if (num1>=num2)
	{
		max = num1;
	}
	else if (max <= num3)
	{
		max = num3;
	}
	else if (max <= num4)
	{
		max = num4;
	}
	else if (max <= num5)
	{
		max = num5;
	}
	else if (max <= num6)
	{
		max = num6;
	}
	return max;
}


int main()
{
	int frequency1 = 0;
	int frequency2 = 0;
	int frequency3 = 0;
	int frequency4 = 0;
	int frequency5 = 0;
	int frequency6 = 0;

	int roll, face;

	for (roll = 0; roll <= 10000; roll++)
	{
		face = 1 + (rand() % 6);

		switch (face)
		{
		case 1:
			++frequency1;
			break;
		case 2:
			++frequency2;
			break;
		case 3:
			++frequency3;
			break;
		case 4:
			++frequency4;
			break;
		case 5:
			++frequency5;
			break;
		case 6:
			++frequency6;
			break;
		}
	}

	int maxStar = maxValue(frequency1, frequency2, frequency3, frequency4, frequency5, frequency6);

	int space1, space2, space3, space4, space5, space6;

	space1 = maxStar - frequency1;
	space2 = maxStar - frequency2;
	space3 = maxStar - frequency3;
	space4 = maxStar - frequency4;
	space5 = maxStar - frequency5;
	space6 = maxStar - frequency6;
	
	int maxSpace = maxValue(space1, space2, space3, space4, space5, space6);

	int space[] = {space1, space2, space3, space4, space5, space6};
	
	int i, j, k;

	for (i = 1; i <= maxSpace; i++)
	{
		for (j = 1; j <= 6; j++)
		{
			if (space[j] < i)
			{
				printf("* ");
			}
			else
				printf("  ");
		}
		printf("\n");
	}

	printf("* * * * * *\n* * * * * *\n* * * * * *\n1 2 3 4 5 6");
