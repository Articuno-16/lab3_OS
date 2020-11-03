#include <stdio.h>
#include <stdlib.h> 
#include <unistd.h>

void getArray(char* fname);

int main(int argc, char** argv) 
{
    char* filename = argv[1];
	int size = 0;
	getArray(filename);
	return 0;
}

void getArray(char* fname)
{
	FILE *fp;
    fp = fopen(fname,"r");
	int* arr = (int *)malloc(256 * sizeof(int));
	int size = 0;
	short num_2 = 0;
	short num_3 = 0;

	if(fp == NULL)
		exit(1);
	
	
	while(fscanf(fp,"%d", &arr[size]) != EOF)
	{
        size++;
	}

	fclose(fp);

	int child = fork();

	if (child > 0){
		for (int i = 0; i < size; i++){
			if (arr[i] % 2 == 0 && arr[i]>=0 )  num_2++;
		}
		printf ("%d\n",num_2);
	}
	if (child == 0){
		for (int i = 0; i < size; i++){
			if (arr[i] % 3 == 0 && arr[i]>= 0)  num_3++;
		}
		printf ("%d\n",num_3);
	}				
	free(arr);
}
