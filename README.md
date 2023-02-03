#include <stdio.h>
#include <stdlib.h>
#include <windows.h>

void gotoxy(int x, int y){
    COORD coord;
    coord.X = x;
    coord.Y = y;
    SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE), coord);
}

int main()
{
    system("cls");
    system("COLOR F9");
    cover();
    int position = 1;
    int keyPressed = 0;
    int maxoption = 3;
    gotoxy(51,9);
    printf("Tugas Quiz");
    while(keyPressed != 13){
        gotoxy(50,12);
        arrowhere(1,position); printf(" Lavel 1");
        gotoxy(50,13);
        arrowhere(2,position); printf(" Lavel 2");
        gotoxy(50,14);
        arrowhere(3,position); printf(" Level 3");
        gotoxy(50,15);
        arrowhere(4,position); printf(" EXIT");
        keyPressed = getch();
        if(keyPressed == 80 && position !=4){
            position++;
        }else if(keyPressed == 72 && position !=1){
            position--;
        }else{
            position = position;
        }
    }
    printf(" Select Option ,%d \n",position);
    int x = position;
    int a;
    int b;

    switch (x){
        case 1:
            level1();
            main();
            break;
        case 2:
            level2();
            main();
            break;
        case 3:
            level3();
            main();
            break;
        case 4:
            menukeluar();
    }
}

void level1(){
    system("cls");
    system("COLOR F9");
    int a, j, n;
    printf ("Program membuat segitiga \n");
    printf("Masukkan Tinggi Segitiga: ");
    scanf("%i", &n);
    printf("\n\n\n");
    for (a = 1; a <= n; a++){
        for (j = 1; j <= a; j++){
            int b = a + j - 2;
            if (b < 10){
                printf("%d  ", b);
            }else{
                printf("%d ", b);}
        }
        printf("\n");
    }
    getch();
}

void level2(){
   system("cls");
    system("COLOR F9");
    int a, j, n;
    printf ("Program membuat segitiga pangkat\n");
    printf("Masukkan Tinggi: ");
    scanf("%i", &n);
    printf("\n\n\n");
    for (a = 1; a <= n; a++){
        for (j = 1; j <= a; j++){
            int b = a * j;
            if (b < 10){
                printf("%d  ",b);
            }else{
                printf("%d ",b);}
        }
        printf("\n");
    }
    system("pause");
}


void level3(){
system("cls");
system("COLOR F9");
int n, i, j, s;
    printf ("Program membuat jajar genjang\n");
    printf ("Masukan jumlah kolom = ");
    scanf ("%d",&n);
    printf("\n\n\n");

    for (i = 1; i <= n; i++)

    {
        for (j = 1; j <= n - i; j++)
        {
            printf (" ");
        }
            for (s = 1; s <= i; s++)
            {
                printf ("%d",s);
            }
                for (s = i - 1; s >= 1; s--)
                {
                    printf ("%d",s);
                }
                printf ("\n");
    }
    n = n - 1;
        for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= i; j++)
        {
            printf (" ");
        }
            for (s = 1; s <= n - i + 1; s++)
            {
                printf ("%d",s);
            }
                for (s = n - i; s >= 1; s--)
                {
                    printf ("%d",s);
                }
                printf ("\n");
    }
    getch();

}


void cover(){
    int i;
    for (i=46;i<=65;i++){
        gotoxy(i,8);
        printf("%c",219);
    }
    for (i=46;i<=65;i++){
        gotoxy(i,17);
        printf("%c",219);
    }
    for (i=46;i<=65;i++){
        gotoxy(i,10);
        printf("%c",219);
    }
    for (i=8;i<=16;i++){
        gotoxy(46,i);
        printf("%c",219);
    }
      for (i=8;i<=16;i++){
        gotoxy(65,i);
        printf("%c",219);
    }
}


void arrowhere (int realposition,int arrowposition){
    if(realposition == arrowposition){
        printf("=>");
    }else{
        printf("  ");
    }
}
