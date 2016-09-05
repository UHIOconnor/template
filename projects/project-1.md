---
layout: project
type: project
image: images/green.png
title: Smiles
permalink: projects/Smiles
date: 2014
labels:
  - Design
  - C++
summary: a simple game developed for a school project.


void main(){

int done = 1;

int xpos;

int ypos;

int type;

int i;

int j;

Smiley* newSmiley;

Smiley* Sarray[BOARD_SIZE][BOARD_SIZE];

srand(time(NULL));

printf("Welcome to the Smiley game \nfollow prompts to add smileys to the board\n");

for (i = 0; i < BOARD_SIZE;i++){

        for(j = 0;j < BOARD_SIZE;j++){
            Sarray[j][i] = NULL;
        }
}
while (done != 0){

    printf("please add a smiley to the board by type two numbers(x y) for its position\n");
    scanf("%d",&xpos);
    scanf("%d",&ypos);
    printf("please select the smiley you would like \n1:Indifferent \n2:Happy \n3:Grumpy \n4:Doctor \n5:Leader \n6:Germ\n");
    scanf("%d",&type);
    newSmiley = malloc(sizeof(Smiley));
    newSmiley->Smileytype = type;
    newSmiley->Health = 5;
    newSmiley->Xpos = xpos;
    newSmiley->Ypos = ypos;
    newSmiley->Status = HEALTHY;
    Sarray[xpos][ypos] = newSmiley;
    IterateBoard(Sarray);
    PrintBoard(Sarray);
    printf("press 0 to exit or any other number to continue\n");
    scanf("%d",&done);
   
}
}


