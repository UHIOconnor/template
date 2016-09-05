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

int PossiblyChangeSmileyState(Smiley* smiley, int adjSmiley){

    if (adjSmiley = 6){
        smiley->Status = SICK;
    }

    if (adjSmiley = 4){
        smiley->Health = 5;
        smiley->Status = HEALTHY;}

    if (smiley->Status == 2) {
        smiley->Health = (smiley->Health -1);
        if (smiley->Health == 0){
            return 1;}
    }
    if (adjSmiley == 5){
        int temp = rand() % 6;
        if (temp == 1){
            smiley->Smileytype = 5;}
    }
    if (adjSmiley == 2){
        int temp = rand() % 4;
        if (temp == 1){
            smiley->Smileytype = 2;}
    }
    if(adjSmiley == 3){
        int temp = rand() % 3;
        if (temp == 1){
            smiley->Smileytype = 3;}
    }
    smiley->Change = 1;
    return 0;
}

// prints a character corresponding to each type //
void PrintSmileyStateSymbol(Smiley* smiley){

    if(smiley->Smileytype == 1){
        printf("I");}
    if(smiley->Smileytype == 3){
        printf("G");}
    if(smiley->Smileytype == 2){
        printf("H");}
    if(smiley->Smileytype == 4){
        printf("D");}
    if(smiley->Smileytype == 5){
        printf("L");}
    if(smiley->Smileytype == 6){
        printf("X");}
}
// goes through the array and possibly changing each smiley it encounters and moving them //
void IterateBoard(Smiley* Sarray[BOARD_SIZE][BOARD_SIZE]){

    int temp;
    int i = 0;
    int j = 0;
    int k = -1;
    int r = -1;
    for (i = 0;i < BOARD_SIZE;i++){
        for(j = 0;j < BOARD_SIZE;j++){
            if(Sarray[j][i] != NULL && Sarray[j][i]->Smileytype != 6){
                for (k = -1;k<3;k++){
                    for (r = -1; r<3;r++){
                        if(Sarray[j+r][i+k] != NULL && j+r < 9 && i+k < 9){
                            if (Sarray[j][i] == 0){
                                temp = PossiblyChangeSmileyState(Sarray[j][i],Sarray[j+r][i+k]->Smileytype);
                                if (temp == 1){
                                    free(Sarray[j][i]);
                                }
                            }
                        }
                    }
                }
                                temp = rand() % 9;
                                switch(temp){
                                case 1:
                                    if (Sarray[j-1][i+1] == NULL){
                                        Sarray[j-1][i+1] = Sarray[j][i];}
                                    if(Sarray[j][i]->Status == HEALTHY){
                                        free(Sarray[j][i]);}
                                    else{
                                        Sarray[j][i]->Smileytype = 6;}
                                    break;
                                case 2:
                                    if (Sarray[j][i+1] == NULL){
                                        Sarray[j][i+1] = Sarray[j][i];}
                                    if(Sarray[j][i]->Status == HEALTHY){
                                        free(Sarray[j][i]);}
                                    else{
                                        Sarray[j][i]->Smileytype = 6;}
                                    break;
                                case 3:
                                    if (Sarray[j+1][i+1] == NULL){
                                        Sarray[j][i+1] = Sarray[j][i];}
                                    if(Sarray[j][i]->Status == HEALTHY){
                                        free(Sarray[j][i]);}
                                    else{
                                        Sarray[j][i]->Smileytype = 6;}
                                    break;
                                case 4:
                                    if (Sarray[j-1][i] == NULL){
                                        Sarray[j-1][i] = Sarray[j][i];}
                                    if(Sarray[j][i]->Status == HEALTHY){
                                        free(Sarray[j][i]);}
                                    else{
                                        Sarray[j][i]->Smileytype = 6;}
                                    break;
                                case 5:
                                    if (Sarray[j][i] == NULL){
                                        Sarray[j][i] = Sarray[j][i];}
                                    if(Sarray[j][i]->Status == HEALTHY){
                                        free(Sarray[j][i]);}
                                    else{
                                        Sarray[j][i]->Smileytype = 6;}
                                    break;
                                case 6:
                                    if (Sarray[j+1][i] == NULL){
                                        Sarray[j+1][i] = Sarray[j][i];}
                                    if(Sarray[j][i]->Status == HEALTHY){
                                        free(Sarray[j][i]);}
                                    else{
                                        Sarray[j][i]->Smileytype = 6;}
                                    break;
                                case 7:
                                    if (Sarray[j-1][i-1] == NULL){
                                        Sarray[j-1][i-1] = Sarray[j][i];}
                                    if(Sarray[j][i]->Status == HEALTHY){
                                        free(Sarray[j][i]);}
                                    else{
                                        Sarray[j][i]->Smileytype = 6;}
                                    break;
                                case 8:
                                    if (Sarray[j][i-1] == NULL){
                                        Sarray[j][i-1] = Sarray[j][i];}
                                    if(Sarray[j][i]->Status == HEALTHY){
                                        free(Sarray[j][i]);}
                                    else{
                                        Sarray[j][i]->Smileytype = 6;}
                                    break;
                                case 9:
                                    if (Sarray[j+1][i-1] == NULL){
                                        Sarray[j+1][i-1] = Sarray[j][i];}
                                    if(Sarray[j][i]->Status == HEALTHY){
                                        free(Sarray[j][i]);}
                                    else{
                                        Sarray[j][i]->Smileytype = 6;}
                                    break;
                                }
                }
            }
        }
    }


	// prints the array of smileys//
void PrintBoard(Smiley* Sarray[BOARD_SIZE][BOARD_SIZE]){

    int i = 0;
    int j = 0;
    for (i = 0; i < BOARD_SIZE;i++){
        for(j = 0;j < BOARD_SIZE;j++){
            if(Sarray[j][i] != NULL){
                PrintSmileyStateSymbol(Sarray[j][i]);}
            else {
                printf(" ");}
        }
        printf("\n");
    }
   
}
