# CV
1. *Matvey Daineko*

1. **Contacts**:
    * Phone number: **+375445442936**
    * Email: **matveydaineko@gmail.com**
    * [VK](https://vk.com/matvey.na_popei)
    * [Instagram](https://www.instagram.com/_._mot_._/?hl=ru)
    * [Facebook](https://www.facebook.com/matvey.daineko/)
    * [LinkedIn](https://www.linkedin.com/in/matvey-daineko-bb7542196/)

1. ** **

1. ** **

1. **Code examples**. 
    There are some exapmles of C-code. They were written on practical lessons of *"Basics of Algorithms and Programming"*.


* '''
\#include <stdio.h>
\#include <stdlib.h>

int main(void) { 
    float A[3][4]; 
    int i, j, k; 
    float Buffer; 
    float x1 = 0, x2 = 0, x3 = 0;

    for ( i = 0; i < 3; i++) { 
        for ( j = 0; j < 4; j++) { 
            printf ("Enter A[%d][%d] = ", i+1, j+1); 
            scanf ("%f", &A[i][j]);
        } 
    } 
    Buffer = A[0][0];

    for ( j = 0; j < 4; j++) { 
        A[0][j]/= Buffer; 
    } 
    Buffer = 0; 
    Buffer =(-1)*A[1][0];

    for ( j = 0; j < 4; j++) { 
        A[0][j]*= Buffer; 
        A[1][j] = A[0][j] + A[1][j]; 
        A[0][j]/= Buffer;
    } 
    Buffer = 0; 
    Buffer =(-1)*A[2][0];

    for ( j = 0; j < 4; j++) { 
        A[0][j]*= Buffer; 
        A[2][j] = A[0][j] + A[2][j]; 
        A[0][j]/= Buffer;
    } 
    Buffer = 0; 
    Buffer = A[1][1];

    for ( j = 0; j < 4; j++) { 
        A[1][j]/= Buffer; 
    }
    Buffer = 0; 
    Buffer = A[2][1]*(-1);

    for ( j = 0; j < 4; j++) { 
        A[1][j]*= Buffer; 
        A[2][j] = A[1][j] + A[2][j]; 
        A[1][j]/= Buffer;
    } 
    Buffer = 0; 
    Buffer = A[2][2];

    for ( j = 0; j < 4; j++) { 
        A[2][j]/= Buffer; 
    } 
    Buffer = 0;

    x3 = A[2][3]; 
    x2 = A[1][3] + (-1)*A[1][2]*x3; 
    x1 = A[0][3] + (-1)*A[0][1]*x2 + (-1)*A[0][2]*x3;

    printf ("Answer:\n x1 = %.2f\nx2 = %.2f\nx3 = %.2f\n", x1, x2, x3);

    return 0;
}
'''


* '''
\#include <stdio.h>
\#include <math.h>
\#include <stdlib.h>
\#include <stdbool.h>
\#define N 3         //Array size

    float a[N][N+1] ={2.5, -3.12, -4.03, 0, 0.61, 0.71, -0.05, 0, -1.03, -2.05, 0.87};         //Array A
    float d[N]= {-7.5, 0.44, -1.16};            //Array B

void matrixA (float ArrayA[N][N+1]);
void matrixD (float ArrayB[N]);
void version6 ();
void IterativeView ();
bool Convergence (float Array[N][N+1]);
void logic (float e);

int main() {
    float e;
    //Precision input
    do {
        printf ("Enter accuracy = ");
        scanf ("%f", &e);
    } while (e < 0);

    //Array output
    matrixA (a);
    matrixD (d);

    //ONLY FOR 6 OPTIONS
    version6 ();   
    IterativeView ();
    
    //Check
    if (Convergence(a)) {
		printf ("Convergence condition check successful\n");
	}
	else {
		printf ("Convergence condition check failed\n" );
		exit (1);
	}
    
    //System solution
    logic (e);
    
    //Answer
    for (int i = 0; i < N; i++) {
        printf( "x%d = %f\n", i+1, a[i][3]);
    }

    return 0;  
}

void matrixA (float ArrayA[N][N+1]) {
    printf ("Matrix A:\n");
    for  (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            printf ("%.2f\t", ArrayA[i][j]);   
        }
        printf ("\n");    
    }
}
void matrixD (float ArrayB[N]) {
    printf ("Matrix B:\n");
    for (int i = 0; i < N; i++) {
        printf ("%.2f\n", ArrayB[i]);       
    }
}

void version6 () {
    float z = 0;
    for (int i=0; i < N; i++) {
        a[1][i] = a[1][i] * 3 + a[0][i];
        z = a[0][i]; a[0][i] = a[2][i]; a[2][i] = z;
        z = a[0][i]; a[0][i] = a[1][i]; a[1][i] = z;     
    }  
    z=0;
    d[1] = d[1] * 3 + d[0];    
    z = d[0]; d[0] = d[2]; d[2] = z;   
    z = d[0]; d[0] = d[1]; d[1] = z;
    z=0;
}
void IterativeView () {
    float z = 0 ;
    for (int i = 0; i < N; i++) {
        z = a[i][i];
        d[i] /= z; 
        for (int j = 0; j < N; j++) {
            a[i][j] = a[i][j] / z * (-1);
        }
        a[i][i] = 0;
    }
}
bool Convergence (float Array[N][N+1]) {
    int s= 0;
    for (int i = 0; i < N; i++) {
		for (int j = 0; j < N; j++) {
		    s += Array[i][j] * Array[i][j];
		}
	}
    return sqrt (s) < 1;
}
void logic (float e) {
    float x[N] ={ 0, 0, 0} ;
	float q[N];
    float max = 0;
    do {
        for (int i = 0; i < N; i++) {
            x[i] = a[i][3];
        }
        for (int i = 0; i < N; i++) {
            a[i][3] = d[i] + a[i][0] * x[0] + a[i][1] * x[1] +a[i][2] * x[2];
            q[i] = fabs (a[i][3] - x[i]);
        }
        max = q[0];
        for (int i = 1; i < N; i++) {
            if (q[i] > max) {
                max = q[i];
            }
        }
    } while(max > e );
}
'''

1. **Loading...**

1. **Education**. I'm a third-year student. I'm completing by bachelor's degree from *Francisk Skorina Gomel State University*. Course title is *Programming Mobile Systems*. Currently I've been doing "*Frontend developer*" course on [Hexlet](https://ru.hexlet.io) since our training started as a complemet to the training from [RS-School](https://rs.school/) with [EPAM](https://training.by/#!/Home?lang=ru) within the framework of self-education.

1. **English level**: *Intermediate*