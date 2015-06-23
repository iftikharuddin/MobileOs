/*

Project : Mobile Operating System Model in C++
Author : Iftikhar uddin

*/

#include<iostream.h>
#include<stdio.h>
#include<graphics.h>
#include<conio.h>
#include<dos.h>
#include<process.h>
//#include<ctime>
#include <string.h>
//#include <windows.h>
//#include<string>
//using namespace std;
 int truevalue=0; // Flag Security
 char user_name[7]={'h','u','n','t','e','r','\0'};
 char pass_word[7]={'h','u','n','t','e','r','\0'};


	class UetOS{

		private:
			int input;
			int loop;
			//string getUsername,getPass;
			//string getPass;


		public:
		   UetOS() {input=0;loop=0;}
		   //UetOS(string x) {}
	       //	 void checkIf();
		 void startView(); //Prototype
		 void checkUser(char[],char[]);
		 void loadingBar();
		 void runclock(); // For Showing Clock in Mobile Desktop!
		 void coolAnimation();
		 void navigateToMenu();
		 void siginIntoApps();
		 void siginIntoGames();
		 void light();
		 void lightApp();
		 void archeryGame();
		 void catapult(int); // Prototype for CataPult!
		 int man(int);
		 void arrow();
		 void manhit(); //When The Target get hit prototype
		 void hitmsg();
		 void playMusic();
		 void musicPlayer(int);
		~UetOS() {} //Destructor
	};

	//void UetOS::checkIf(){
	    //	   int truevalue=0; //Flag for Security!
	  //	 }

	void UetOS::startView(){
			 if(truevalue==1){


				runclock();
				outtextxy(180,10,"DESKTOP");
				gotoxy(27,11);
				//rectangle(220,240,500,110);
				rectangle(170,260,490,120);
				rectangle(170,200,490,120);
				cout<<"Welcome To IfTi Operating System!"<<endl;
				gotoxy(27,12);
				cout<<"1 -> To Run The OS"<<endl;
				gotoxy(27,13);
				cout<<"2 -> For Exit"<<endl;
				gotoxy(27,14);
				cin>>input; //Input From User

					switch(input){

						case 1:
							cleardevice();
							//gotoxy(35,12);
							//rectangle(200,300,20,120);
							runclock();
							outtextxy(180,10,"UET OS");
							gotoxy(30,11);
							//rectangle(220,240,500,110);
							rectangle(170,260,490,120);
							rectangle(170,200,490,120);
							cout<<"Welcome Buddy!";
						    //	runclock();
							gotoxy(30,12);
							cout<<"MENU (m)";
							gotoxy(30,13);
							cout<<"Exit (esc)\n";
							char getChar;
							gotoxy(30,14);
							cin>>getChar;
								if(getChar=='m'){
									cleardevice();
									navigateToMenu();

								}

								 else if(getChar==27){
										exit(0);
								 }

							break;
						case 2:
							//cout<<"Iam Logout!";
							exit(0);
							break;
						default:
							cout<<"Sa kae Professor sab!!??";
					}

			 }
			}

			void UetOS::checkUser(char getUsername[],char getPass[]){

				if(strcmp(getUsername, user_name) == 0){
				   if(strcmp(getPass, pass_word) ==0){
					  truevalue=1;
					  cout<<"Otas You are in Baby!\n";
					}

				}
				else {

					cout<<"\nUsername or Password is incorrect Buddy!";
				}


			}
			//UET OS Starting Loading Bar
		void UetOS::loadingBar(){

				for(loop=1;loop<=24;loop++){
					gotoxy(28+loop,14);
					printf("%c",177);
					delay(200);
				}


		}
		void UetOS::runclock(){

			struct date d;
			getdate(&d);
			gotoxy(28,7);
			setcolor(3);

			printf("Y: %d ",d.da_year);
			gotoxy(36,7);
			//settextstyle(TRIPLEX_FONT, HORIZ_DIR, 4);
			printf("D: %d ",d.da_day);
			gotoxy(41,7);

			printf(" M: %d ",d.da_mon);

			struct  time t;

			gettime(&t);

			printf("| %d ", t.ti_hour);
			printf(": %d ", t.ti_min);
			printf(": %d ", t.ti_sec);

		/* Add one to the minutes struct element and then call settime  */
			t.ti_min++;
			settime(&t);

		}
	    void UetOS::navigateToMenu(){
			cleardevice();
			settextstyle(1,0,6);
			setcolor(GREEN);
			outtextxy(200,35,"Main Menu");
			runclock();
			gotoxy(27,11);
			rectangle(170,260,490,120);
			rectangle(170,200,490,120);
			cout<<"PHONE BOOK (p)";
			gotoxy(41,11);
			cout<<" | "<<"APPLICATIONS (a)";

			gotoxy(27,12);
			cout<<"GAMES (g)";
			gotoxy(39,12);
			cout<<" | "<<"MUSIC (m)";

			gotoxy(27,13);
			cout<<"EXIT (esc) \n";
			gotoxy(39,13);
			cout<<" | "<<"BACK (b)";

			gotoxy(35,15);
			cout<<"CAMERA (c)";
			  char getChar2;
			  gotoxy(26,16);
			  cin>>getChar2;
			   if(getChar2=='a'){
					   cleardevice();
					   siginIntoApps();
					 }

			   else if(getChar2=='g'){
					cleardevice();
					siginIntoGames();
			   }
			   else if(getChar2==27){
					exit(0);
			   }
			   else if(getChar2=='b'){
					cleardevice();
					startView();

			   }
			   //else if(getChar2=='p'){
			     //		cleardevice();
			       //		phoneBook();

			  // }
			   else if(getChar2=='m'){
					cleardevice();
					playMusic();

			   }
			   //else if(getChar2=='c'){
			     //		cleardevice();
			  //		runCamera();

			   //} */

		}
		void UetOS::siginIntoApps(){

			light();

		}

		void UetOS::siginIntoGames(){
			settextstyle(1,0,6);
			setcolor(GREEN);
			outtextxy(165,35,"GAMES");
			runclock();
			gotoxy(26,11);
			//rectangle(220,240,500,110);
			rectangle(170,260,490,120);
			rectangle(170,200,490,120);
			cout<<"ARCHERY GAME (a)";
			gotoxy(26,12);
			cout<<"EXIT (esc)";
			gotoxy(26,13);
			cout<<"BACK (b)\n";
			char getBackChar;
			gotoxy(27,13);
			cin>>getBackChar;
				if(getBackChar=='b'){
					cleardevice();
					navigateToMenu();

				}else if(getBackChar=='a'){

					archeryGame();
				}
				else if(getBackChar==27){
					exit(0);
				}

		}
		void UetOS::light(){
				runclock();
				outtextxy(200,35,"redLight");
				//gotoxy(20,11);
				//rectangle(220,240,500,110);

				outtextxy(100,276,"BACK (b)");
				outtextxy(100,329,"EXIT (esc)");
				outtextxy(80,379,"Up Arrow To On Light");
				lightApp();
		}
	    void UetOS::coolAnimation() {
				int loop;
				 for(loop=1;loop<=50;loop++) {
				  circle(220,200+loop,loop);
				  circle(220,200+loop,loop);
				  setcolor(WHITE);
				  delay(20);
				  }

		}
	    void UetOS::lightApp(){

			char ch;
			while(1) { //While Starts
					  setcolor(WHITE);
					  setfillstyle(SOLID_FILL, BLACK);
					  pieslice(380,200,0,360,30);
					  rectangle(370,280,390,230);
					  delay(200);

					 if(kbhit()) {
					    ch=getch();
					  if(ch==72) {
					   setcolor(RED);
					   setfillstyle(SOLID_FILL, RED);
					   pieslice(380,200,0,360,30);
					   rectangle(370,280,390,230);
					   delay(2000);
						
					  }
					   if(ch=='b'){
					       navigateToMenu();

					   }
					   
					   if(ch==80) { //DOWN
					    setcolor(YELLOW);
					    setfillstyle(SOLID_FILL, YELLOW);
					    pieslice(380,200,0,360,30);
					    rectangle(370,280,390,230);
					    delay(2000);

					   }
					   if(ch==27)
					     exit(0);
					 }
			  }//While END

		}
		void UetOS::archeryGame(){
		cleardevice();
		int i,loop,score=0,x=4,ch,target;

		   while(1) { //While Starts
			 //printf("Your Score is %d",score);
			 //cleardevice();
			 catapult(0); //Arrow Shape Func Called
			 settextstyle(1,0,3);
			 outtextxy(15,380,"Want To Shoot that Person: ? If Yes Press Arrow Key");
			 outtextxy(15,250,"BACK (b) || EXIT (Esc) ");
			 man(0); //SHOW Man


			 if(kbhit()) {  //KBHIT IF STARTS
				ch=getch();

				//WHEN UP ARROW IS PRESS DO THE BELOW
				if(ch==72) { //up
					  for(loop=1;loop<=20;loop++) {
					 gotoxy(x=x+3,1);

					 arrow();
					 delay(40);
					 cleardevice();
					 catapult(loop);
					 target=man(loop+30);

					 //Here Comes the Case when the man get hits..
					  if(loop==20) {
						 cleardevice();
						 score++;
						 printf("Your Score is %d",score);
						 manhit();
						 hitmsg();
						 delay(40);
					  } //if end when loop==20
					  //else{ continue;}
					  }//for end
				}// if UP End

				if(ch==27)
					exit(0);
				if(ch=='b'){
				  navigateToMenu();
				}
			 } //KBHIT IF END
		   } //While Loop End



		}

		void UetOS::catapult(int i) {
			//setviewport(100,30,50,-30,3);
			line(2+2,42+i,42,40+i);
			setbkcolor(BLACK);
			arc(-2,40+i,-92,85,30);
			arc(-1,40+i,-92,85,30);
			delay(40);
		 //cleardevice();
		}

		int UetOS::man(int i) {
			//Show Man
			 circle(590,30+i,30);
			 circle(585,25+i,3);
			 circle(600,25+i,3);
			 rectangle(630,60+i,550,160+i);
			 return i;

		}

		void UetOS::arrow() {

			printf("%c--",29);
		}

		void UetOS::manhit() {
			   //MAN When HIT
			setfillstyle(1,RED);
			pieslice(590,30,0,360,30);
			circle(585,25,3);
			circle(600,25,3);

		}

		void UetOS::hitmsg() {
			settextstyle(1,0,8);
			outtextxy(25,240,"Bush Killed!");

		}
		void UetOS::playMusic(){
		   rectangle(170,260,490,120);
		   rectangle(170,200,490,120);
		   outtextxy(45,280,"Taste The Player!");
		   gotoxy(30,12);
		   cout<<"Singer 1 (p)";
		   gotoxy(30,13);
		   cout<<"Singer 2 (k)";
		   gotoxy(30,14);
		   cout<<"BACK (b)";
		   gotoxy(30,16);
		     char input;
		     cin>>input;
		     if(input=='p'){
				musicPlayer(1);
			 }
		      else if(input=='k'){
				musicPlayer(2);
		      }
		      else if(input=='b'){

				navigateToMenu();

		      }




		}

		void UetOS::musicPlayer(int get){
			int ch;
			int boss=0;
			if(get==1){
				cleardevice();
				settextstyle(1,0,6);
				outtextxy(25,240,"Welcome To Music Player");
				gotoxy(30,12);
				cout<<"PAUSE (p)";
				gotoxy(30,13);
				cout<<"PLAY AGAIN (a)";
				gotoxy(30,14);
				cout<<" Close (x)";
				int loop=1;
				//int input=0;
				  while(loop){
					if(boss==1){
					 gotoxy(30,14);
					 cout<<"MUSIC PAUSED";
					 gotoxy(30,15);
					 cout<<"Press a To Start Again";
					 gotoxy(30,16);
					 cout<<"To Close Press (x)";
					}else{

					setbkcolor(loop);
					sound(loop);
					setcolor(loop);
					circle(250,140,50+loop);
					delay(40);
					}
					if(kbhit()){
					   ch=getch();
					  if(ch=='p'){
					      nosound();
					      boss=1;
					      continue;

					  }

					  if(ch=='x'){
						   nosound();
						   cleardevice();
						   playMusic();
				      }

					  if(ch=='a'){
						 nosound();
						 //loop=1;
						 cleardevice();
						 musicPlayer(1);
					  }
					  if(ch==27)
					     exit(0);
					  }//Kb end
					  loop++;
					}//while end
					nosound();
					cleardevice();
					playMusic();
				  //	}

			}
			if(get==2){
				cleardevice();
				settextstyle(1,0,6);
				outtextxy(25,240,"Welcome To Music Player");
				gotoxy(30,12);
				cout<<"PAUSE (p)";
				gotoxy(30,13);
				cout<<"PLAY AGAIN (a)";
				gotoxy(30,14);
				cout<<" Close (x)";
				int loop=1;
				//int input=0;
				  while(loop){
					if(boss==1){
					 gotoxy(30,14);
					 cout<<"MUSIC PAUSED";
					 gotoxy(30,15);
					 cout<<"Press a To Start Again";
					 gotoxy(30,16);
					 cout<<"To Close Press (x)";
					}else{

					setbkcolor(loop);
					sound(loop);
					setcolor(loop);
					circle(250,140,50+loop);
					delay(40);
					}
					if(kbhit()){
					   ch=getch();
					  if(ch=='p'){
					      nosound();
					      boss=1;
					      continue;

					  }

					  if(ch=='x'){
						   nosound();
						   cleardevice();
						   playMusic();
					}

					  if(ch=='a'){
						 nosound();
						 //loop=1;
						 cleardevice();
						 musicPlayer(1);
					  }
					  if(ch==27)
					     exit(0);
					  }//Kb end
					  loop++;
					}//while end
					nosound();
					cleardevice();
					playMusic();
				  //	}

			}
		}

int main(){
	char username[7];
	char pass[7];
	UetOS play;
		int gd=DETECT,gm;
		initgraph(&gd,&gm,"..\\BGI");

	settextstyle(1,0,8);
	setcolor(WHITE);
	outtextxy(269,85,"UET");
	delay(1100);
	outtextxy(280,205,"S v 1.0");
	delay(1100);
	play.coolAnimation();
	delay(1200);
	//outtextxy(280,205,"S v 1.0");
	//delay(1800);
	char key='y';
	do{
		cleardevice();
		outtextxy(230,30,"LOGIN");
		rectangle(170,200,490,120);
		gotoxy(30,10);
		cout<<"Enter Username:> ";
		cin>>username;
		gotoxy(30,11);
		//rectangle(200,30,400,10);
		cout<<"Enter Password:>";
		cin>>pass;
			UetOS run;
			run.loadingBar();
			run.checkUser(username,pass);
			cleardevice();
			run.startView();

			if(truevalue==0){
				rectangle(220,200,490,140);
				gotoxy(30,12);
				cout<<"Want 2 Login Again Y/N : ";
				cin>>key;

			}
			else if(truevalue==1){

				key='n';

			}
	}while(key=='y');


	return 0;
}
