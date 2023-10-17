// -nsertion_Sort
// İnsertion sort sıralama algoritmasının c dili ile örneği aşağıdaki gibidir...
// Dizi 1'den 100'e kadar olan tam sayılardan rastgele oluşmaktadır. İsertionsort fonksiyonu kullanılarak sayılar küçükten büyüğe doğru sıralanmaktadır.
#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
#include <time.h>

void insertionsort(int array[], int size)
{
	int i,j;
	int eleman;
	
	for (i=1; i<size; i++)
	{
		eleman = array[i];
		j = i-1;
		
		while (i>0 && array[j]>eleman)
		{
			array[j+1] = array[j];
			j--;
		}
		array[j+1] = eleman;
	}
	printf("Dizinin Elemanlarinin Siralanmis Halali:\n");
	for(i=0;i<size;i++){
		printf("%d - ",array[i]);
	}
}

int main() {
	
	srand(time(NULL));
	int girilen_sayi_adedi=100;
	int dizi[girilen_sayi_adedi]={0};
	int i;
	int index = 0; //diziye eklenen eleman sayısı
	
	while(index < girilen_sayi_adedi)
	{
		int rastsayi = rand()%girilen_sayi_adedi+1;
		int varmi = 0;
		
		for ( i=0; i<index; i++)
		{
			if(dizi[i] == rastsayi)
			{
				varmi = 1;
				break;
			}
		} 
		
		if(!varmi)
		{
			dizi[index] = rastsayi;
			index++;
		}
	}	
	
	printf("Dizinin Elemanlari:\n");
	for(i=0;i<girilen_sayi_adedi;i++)
	{
		printf("%d - ",dizi[i]);
	}
	
	printf("\n\n\n");

	insertionsort(dizi,girilen_sayi_adedi);

	return 0;
}
