// Project-Rock-scissor-Paper
#include<stdio.h>
#include<stdlib.h>
#include<time.h>
void Logic ();
void userInput();
void Player();
 int comScore=0;
    int playerScore=0;
    int player;
    int com;
    int i;
    char name[2][32];
    char list[3][32]={"Rock","paper","scissor"};
                           
                       
   

//=====taking input from machine========

int machine()
{
    srand(time(0));
    int number1=(rand()%3);

}
//======= user input interface==========

void userInput()
{
    printf("\n>>> round %d <<<\n\n %s, ENTER YOUR CHOICE ==> \n 1.rock \n 2.paper \n 3.scissor\nENTER :",i,name);
    scanf("%d",&player);
    if(player>=4 || player<=0)
    {
       system("cls");
        printf("WRONG ENTER --> CHOOSE BETWEEN 1-3 :");

       userInput();
    }
}
void Player()
{
    // player 
    printf("\n\n<====  WELLCOME TO ROCK PAPER SCISSOR GAME =====>\n\n");
    printf ("ENTER YOUR NAME :");
    scanf("%s",name);
    for( i=1; i<=3;i++)
  {
    userInput();
    system("cls");
    printf("\n<<----------------ROUND %d'S RESULT-------------------->>\n\n",i);
   
    printf("YOU HAVE CHOSEN : %s",list[player+1]);

    printf("\n");

    //storing, machine generate input into int com;

     com = machine();
     com++;
    printf("I HAVE CHOSEN :%s",list[com]);

    printf("\n\n");

    Logic();
  }  
}
    //========= logic part==============

   void Logic()
{

    if(player==1 && com==2)
    {
        printf("hehe.. I WON");
        comScore++;
    }
    else if (player==2 && com==1)
    {
        printf("great you won ");
        playerScore++;
    }
    if(player==1 && com==3)
    {
        printf("great You won");
        playerScore++;
    }
    else  if (player==3 && com==1)
    {
        printf("hehe: I won");
        comScore++;
    }
    if(player==2 && com==3)
    {
        printf("hehe I won ");
        comScore++;
    }
    else if(player==3 && com==2)
    {
        printf("great you won ");
        playerScore++;
    }
    if(player==com)
    {
        printf("no result, match draw \n");
    }
    printf("\n<====== SCORELINE ======>\n");  

     printf("Your Score    computer's Score \n  ");
    printf("\n");
   
    printf("  %d  \t \t %d",playerScore ,comScore);

    // printf("your Score       :%d\n",playerScore);
    // printf("Computer's Score :%d\n",comScore);
     printf("\n");    
}

// ========= making score calculating interface ========
void score()
{
         printf("===FINAL SCORE===\n");
    printf("Your Score    My Score \n  ");
    printf("\n");
   
    printf("  %d  \t \t %d",playerScore ,comScore);
    if(playerScore>=comScore)
    {
        printf("\n\nCONGRATS %s... You won the match.",name);
    }
    else if(playerScore<=comScore)
    {
        printf("\n\nHehe...I won the match.");
    }
    else if (playerScore==comScore)
    {
        printf("Aree yrrr..!!! Match draw,Well done %s, You played well",name);
    }
}


int main()
{  
   Player();
   score();
    printf("\n\n\n\n");
    return 0;
}
