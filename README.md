#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define BOYUT 20

void DiziKarıstır(int dizi[])
{
	for (int i = 0; i < BOYUT; i++)
	{
		int j = rand() % (i + 1);

		int temp = dizi[i];
		dizi[i] = dizi[j];
		dizi[j] = temp;
	}
}
int main()
{
	int dizi[BOYUT];
	for (int i = 0; i < BOYUT; i++)
	{
		dizi[i] = i + 1;
	}


	srand(time(NULL));
	DiziKarıstır(dizi);

	printf("\n\n");
	for (int i = 0; i < BOYUT; i++)
	{
		for (int j = 0; j < BOYUT; j++)
		{
			if (dizi[j] >= BOYUT - i)
			{
				printf("  *");
			}
			else
			{
				printf("   ");
			}
		}
		printf("\n");
	}

	for (int i = 0; i < BOYUT; i++)
	{
		printf(" %2d", dizi[i]);
	}
	printf("\n\n");

	return 0;
}
