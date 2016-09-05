---
layout: project
type: project
image: images/Blue.png
title: Rock Paper Scissors
permalink: projects/RPS
date: 2013
labels:
  - C++
  - GitHub
summary: simple rock paper scissors code made for a class project.
---

int declareWin(int, int);

main() {

 srand(time(0));
 
 int num;
 
 int result;
 
 int compnum = rand() % 3;
 
 string done = false;
 
 while(done == true){
 
cout << " please choose rock, paper, or scissors\n";

string input = cin.getline();

if (input == "rock")

		 num = 1;
		 
	else {
	
	   if ( input == "paper")
	   
		 num = 2;
		 
		   if (input == "scissors")
		   
			    num = 3;
			    
		   else {
		   
			   cout << "error";}
			   
	       }
	}
	
int result = declareWin(num, compnum);

if (result == 1){

	cout << "\nYou Win";
	
done = true;}

else{

	if (result == 3)
	
		cout << "\nYou Lose";
		
		done = true;}
		
	}
}

int declareWin(int player,int comp) {

if (player == 1 || comp == 3)

		 return 1;
		 
	else {
	
	   if ( player == 2 || comp == 1)
	   
		 return 1;
		 
	   else{
	   
		   if (player == 3 || comp == 2)
		   
			    return 1;
			    
		   else {
		   
			   if (player == comp)
			   
		        return 2;
		        
			   else 
			   
				return 3;
				
		   }
	       }
	}
}
