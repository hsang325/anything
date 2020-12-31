#include<stdio.h>

int x[10] = { 3,7,2,5,6,4,1,9,10,8 };

void array(int a, int b) {

	int q = x[a];
	int temp = 0;

	for (int i = a; i <= b; i++ ) {

		
		
		if (x[i] > q){
			for (int j = b; j >= a; j--) {

				if (j == a) {
					q = x[i];
					a = i;
					break;
				}
				if (x[j] < q) {

					if (j < i) {
						temp = x[j];
						x[j] = x[a];
						x[a] = temp;
						
						

						array(a, j);

						q = x[i];
						a = i;
						break;
					}

					else{
						temp = x[i];
						x[i] = x[j];
						x[j] = temp;
						break;
					}
					
				}
			}

		}
		
	}

	return ;
}

void main() {

	

	array(0,9);
	for (int i = 0; i <= 9; i++ ) {
		printf("%d ", x[i]);
	}

	

	return ;
}
