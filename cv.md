# CV
1. **Matvey Daineko**

1. **Contacts**:
    * Phone number: **+375445442936**
    * Email: **matveydaineko@gmail.com**
    * [VK](https://vk.com/matvey.na_popei)
    * [Instagram](https://www.instagram.com/_._mot_._/?hl=ru)
    * [Facebook](https://www.facebook.com/matvey.daineko/)
    * [LinkedIn](https://www.linkedin.com/in/matvey-daineko-bb7542196/)

1. **About me**\
My attention was attracted by such a direction as front-end development. At the moment I'm studying this direction and my purpose is to become a full stack developer using **MERN** or **MEVN**. I'm an enegetic man, sociable and resposive. I'm ready to communicate and establish connections and contacts with colleagues. I'm able to work effectivly as part of a team. Honesty, creativity, accuracy and love for details. I'm able to learn quickly and discover new things. I consider they are my strengths. Sometimes I have problems with motivation. I my opinion the reason of it is the boring tasks that I get, but I'm working on it and people close to me are helping me. 

1. **Skills**\
Above all I should say that I still don't know any of the programming languages and frameworks but I'm making an effort to study them. At the beginning of my studying at the university we got acquainted with such technologies as **C** and **Git**. We have been study **JavaScript** and **Vue.js** for it with our lecturer and **Object Oriented Programming** using **C#** as an example at the university since the beginning of this term. At course from [RS-School](https://rs.school/) with [EPAM](https://training.by/#!/Home?lang=ru) we learn framework **React** for **JavaScript**.

1. **Code examples**\
There are some exapmles of **C** and **Arduino-code**. They were written on practical lessons of *"Basics of Algorithms and Programming"* and *"Basics of Computer Technologies"*.

    * ```
        #include <stdio.h>
        #include <stdlib.h>

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

        ```

    * ```
        #include <stdio.h>
        #include <stdlib.h>

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
        ```

    * ```
        #include <Bounce2.h>

        int ledPin = 13;
        int buttonPin = 12;
        int trigger = 0;  

        void setup() {
        pinMode(ledPin, OUTPUT);
        digitalWrite(buttonPin, HIGH);  
        }

        void loop() {
        if(digitalRead(buttonPin) == LOW)
        {
        delay(100);
        if(digitalRead(buttonPin) == LOW)    
        trigger=~trigger;
        }
        digitalWrite(ledPin, trigger);
        }
        ```


1. **Loading...**

1. **Education**\
I'm a third-year student. I'm completing by bachelor's degree from *Francisk Skorina Gomel State University*. Course title is *Programming Mobile Systems*. Currently I've been doing "*Frontend developer*" course on [Hexlet](https://ru.hexlet.io) since our training started as a complemet to the training from [fRS-School](https://rs.school/) with [EPAM](https://training.by/#!/Home?lang=ru) within the framework of self-education.

1. **English level**: *Intermediate*