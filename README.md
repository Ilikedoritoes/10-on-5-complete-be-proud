#define _CRT_SECURE_NO_WARNINGS
#include <stdlib.h>
#include <stdio.h>
#define row 10
#define colume 10

int main()
{
    int sum100 = 0, ro = 0, co = 0, half = 0, startX = 0, startY = 0, x = 0, y = 0, sum4 = 0;
    //row שורה
    //colum טור
    int mtrx3[row][colume] = { {1,2,3,4,0,0,0,0,0,0},
                               {5,6,7,8,0,0,0,0,0,0},
                               {9,10,11,12,0,0,0,0,0,0},
                               {13,14,15,16,0,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,0,0},
                               {0,0,0,0,0,0,0,0,136,0},
                               {0,0,0,0,0,0,0,0,0,0} };
    //קולט את הסכום של מטריצה בגודל 100
    for (ro = 0; ro < colume; ro++)
    {
        for (co = 0; co < row; co++)
        {
            sum100 = mtrx3[ro][co] + sum100;
        }
    }
    half = sum100 / 2;
    printf("sum of 100 is %d %d\n", sum100, half);


    for (ro = 0; ro < colume; ro++)
    {
        for (co = 0; co < row; co++)
        {
            startX = ro;
            startY = co;
            for (x = startX; x < startX + 4; x++)
            {
                for (y = startY; y < startY + 4; y++)
                {

                    sum4 = sum4 + mtrx3[x][y];

                    //printf("sum4 is %d\n", sum4);
                }
            }
            //כשהסכום של המטריצה הקטנה יהיה שווה לשאר המטריצה התוכנה תקליד את הסכום.
            if (sum4 == half)
            {
                printf("sum of 4 is %d, and the other half is %d\n", sum4, half);
                break;
            }

        }
    }
}
