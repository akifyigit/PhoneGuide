#include <stdio.h>  
#include <conio.h>   		
#include <windows.h> 
#include <stdlib.h>  
#include <unistd.h> //windows.h function in linux ?
#define str_size 100

FILE *guidefile;

void AddPerson();
void Show();
void Update(char Name[str_size]);
void Delete(char name[str_size]);
void PersonCheck();
void calling(char y[str_size],int determ);
void continuefunction();

struct Database // giving a little database to our code.
{
	char name[str_size];
	char surname[str_size];
	char phonenumber[str_size];
	char dateofbirth[str_size];
	char email[str_size];
}data;

int main()
{
system("color e1"); //color for the 
int choice,answer;
char answer2;
char name,surname,phonenumber,dateofbirth,email;
	printf("------------------MENU-------------------------------\n");
	printf("--------CHOOSE WHAT YOU WANT TO DO-------------------\n");
	printf("           Press 1 to add person\n"						);
	printf("           Press 2 to Show Guide\n"						);
	printf("           Press 3 to Update a Person\n"				);
	printf("           Press 4 to Delete a Person\n"				);
	printf("           Press 5 to Look for a Person in the Guide\n" );
	printf("           Press 6 to EXIT\n"						    );
	printf("-----------------------------------------------------\n");
	printf("Please enter what you want to do(as number):"			);
	scanf("%d",&choice);
	
	
	
	if( choice == 1 || choice == 2 || choice == 3 || choice == 4 || choice == 5 || choice == 6)
	{
	 switch(choice)
	 	{
	 	case 1: AddPerson(); break;
	 	
		case 2: Show(); break;

		case 3: 
				{
					printf("Enter the name you want to update:");
					_flushall(); //cleans the memory
					gets(data.name);
					Update(data.name);
						for(;;)
						{
							printf("For keep doing the update press (1)\n");
							printf("For going back to menu press (2)\n");
							printf("For exiting press(3)\n");
							printf("Your choice is :");
							scanf("%d",&answer);
								if(answer==1)
								{
									choice == 3 ; break;
								}
								else if(answer=2)
								{
									main(); break;
								}
								else if(answer=3)
								{
									exit(1); break;
								}
								else 
								{
								printf("You entered a wrong letter!\n We will return you to main menu.");
								main(); break;
								}
						}
				}
				
		case 4: 
				{
				printf("Enter the name that will get deleted:");
				_flushall();
				gets(data.name);
				Delete(data.name);
				for(;;)
						{
							printf("For doing an update press (1)\n");
							printf("For going back to menu press (2)\n");
							printf("For exiting press(3)\n");
							printf("Your choice is :");
							scanf("%d",&answer);
								if(answer==1)
								{
								choice = 3; break;
								}
								else if(answer=2)
								{
									main(); break;
								}
								else if(answer=3)
								{
									exit(1); break;
								}
								else 
								{
								printf("You entered a wrong letter!\n We will return you to main menu.");
								main(); break;
								}
						}
			}
		
	    case 5: PersonCheck();break;
		case 6: exit(1); break	;
		default: printf("Please use the numbers that menu gives you!"); break;
		}
	}
	return 0;
}
			void AddPerson()
			{

				guidefile = fopen("guide.txt", "a");
				rewind (guidefile); // setting the file position to the beginning of the file
				if(guidefile==NULL) { ("There is not such thing as a guide file!"); }
				else
				{	
					system ("cls"); 				//cleaning the screen
					printf("New person\n");
					printf("-------\n\n\n\n");
					printf("Enter Name: ");
					scanf("%s",&data.name);
					fprintf(guidefile,"%s\n ",&data.name);
					printf("Enter Surname: ");
					scanf("%s",&data.surname);
					fprintf(guidefile,"%s\n ",&data.surname);
					printf("Phone number:");
					scanf("%s",&data.phonenumber);
					fprintf(guidefile,"%s\n ",&data.phonenumber);
					printf("Date of birth(dd/mm/yyyy): ");
					scanf("%s", &data.dateofbirth);
					fprintf(guidefile, "%s\n ",&data.dateofbirth);
					printf("email: ");
					scanf("%s",&data.email);
					fprintf(guidefile, "%s\n ",&data.email);
					fclose(guidefile);
				}
			}
			
			void Show()
			{
				printf("1");
				guidefile = fopen("guide.txt","r");
				int choice2;
				if(guidefile==NULL)
			{ 
				while(1)
				{
					printf("There is no person in this Guide.\nPress (1) to add a person");
					scanf("%d",&choice2);
					if(choice2==1)
					{
						AddPerson();
						 break;
					}
					else 
					{
					printf("You entered a wrong choose!\n Please start again");
					main();
					}
				}
			}
				else
				{
					system("cls");
					printf("--------PHONE GUIDE-------\n");
					printf("--------------------------\n\n");
					while(fscanf(guidefile, "%s%s%s%s%s%s%s",&data.name,&data.surname,&data.phonenumber,&data.dateofbirth,&data.email) != EOF ) //EOF stands for end of file
					{
						printf("Name:%s\nSurname:%s\nPhone Number:%s\nDate of Birth:%s\nEmail:%s\n",data.name,data.surname,data.phonenumber,data.dateofbirth,data.email);
					}
					fclose(guidefile);
					continuefunction();
				}
			}
			
			void Update(char name[str_size])
			{
				
				char Name[str_size],Surname[str_size],Phonenumber[str_size],Dateofbirth[str_size],Email[str_size];
				FILE *guidefile	,*newfile;
				int x = 0;
				system("cls");
				guidefile = fopen("guide.txt",("r")); // opens in reading mode
				newfile = fopen("guide2.txt",("w")); // opens is writing mode
				if(guidefile==NULL) { ("There is not such thing as a guide file!"); }
				else
				{
					while(!feof(guidefile)) // scans all the file
					{
					fscanf(guidefile,"%s %s %s %s %s",&data.name,&data.surname,&data.phonenumber,&data.dateofbirth,&data.email) ;
						if(strcmp(data.name,Name) == 0)
						{
							x = 1;
							printf("Updated Information\n");
							printf("---------------------");
							printf("Name: ");
							scanf("%s",data.name);
							fprintf(guidefile,"%s",Name);
							printf("Surname: ");
							scanf("%s",data.surname);
							fprintf(guidefile,"%s",Surname);
							printf("Phone number:");
							scanf("%s",data.phonenumber);
							fprintf(guidefile, "%s\n ",Phonenumber);
							printf("Date of birth(dd/mm/yyyy): ");
							scanf("%s", data.dateofbirth);
							fprintf(guidefile, "%s\n ", Dateofbirth);
							printf("email: ");
							scanf("%s",data.email);
							fprintf(guidefile,"%s\n",Email);
							printf("Informations are updated!\n");
							fprintf(newfile,"%s %s %s %s %s\n",Name,Surname,Phonenumber,Dateofbirth,Email);
						}
						else
						{
						fprintf(newfile,"%s %s %s %s %s\n",Name,Surname,Phonenumber,Dateofbirth,Email);
						}
					}
					_fcloseall(); //closes all the files
					remove("guide.txt");
					rename("guide2.txt","guide.txt");
					if(x==0)
					{
						printf("This person is not in this guide.\n");
						Sleep(200);
						main();		
					}
				}
			}
			void Delete(char name[str_size])
			{
				char Name[str_size],Surname[str_size],Phonenumber[str_size],Dateofbirth[str_size],Email[str_size];
				int answer;
				FILE *guidefile	,*newfile;
				int a,x = 0;
				system("cls");
				guidefile = fopen("Guide.txt",("r")); // opens in reading mode
				newfile = fopen("Guide2.txt",("w")); // opens is writing mode
				if(guidefile==NULL) { ("There is nobody in this guide! "); }
				else
				{
					rewind(guidefile);
					rewind(newfile);
					printf("Are you sure you want to delete %s ?\nfor yes press (1)\nfor no press(2)",Name);
					scanf("%d",&answer);
						if(answer == 1)
						{
							while(!feof(guidefile))
							{
								fscanf(guidefile,"%s %s %s %s %s",Name,Surname,Phonenumber,Dateofbirth,Email);
									if(strcmp(data.name,Name))
									{
										printf("Deleted person info\n");
										printf("-------------------\n");
										printf("Name:%s\nSurname:%s\nPhone Number:%s\nDate of birth:%s\nEmail:%s",Name,Surname,Phonenumber,Dateofbirth,Email);
										printf("Person has been deleted.\n");
										a=1;
									}
									else fprintf(newfile,"%s %s %s %s %s",Name,Surname,Phonenumber,Dateofbirth,Email);
								
							}
							_fcloseall();
							remove("guide.txt");
							rename("guide2.txt","guide.txt");
							if (a==0) printf("This person is not in the guide!\n");
						}
						else if(answer == 2)
						{
							printf("Going back to the menu.");
							sleep(300);
							main();
						}
						else
						{
							printf("Wrong button!\n Going back to the menu.");
							sleep(300);
							main();
						}					
				}	
			}
			void PersonCheck()
			{
				FILE *guidefile;
				char name2[str_size],determ;
				int choice,flag=0;
				fopen("guide.txt","r");
				if(guidefile==NULL)
				{
				  printf("There is no file! ");
				}
				
				else
				{
					system("cls");
					printf("Please enter the name you looking for:");
					_flushall();
					gets(name2);
					printf("%s\n",name2);
					calling(name2,determ);
					continuefunction();
				}	
			}
			void calling(char y[str_size],int determ)
			{
			system("cls");
			int flag=0;
			rewind(guidefile);
				while(fscanf(guidefile,"%s",y) != EOF)
				{
				fscanf(guidefile, "%s",data.surname);
				fscanf(guidefile, "%s",data.phonenumber);
				fscanf(guidefile, "%s",data.dateofbirth);
				fscanf(guidefile, "%s",data.email);
					if(determ==0)
					{
					
						if(!strcmp (data.name,y))
						{
							printf("Person info:");
							printf("Name:%s\nSurname:%s\nPhone Number:%s\nDate of Birth:%s\nEmail:%s",data.name,data.surname,data.phonenumber,data.dateofbirth,data.email);
							flag = 1;
						}
					}
					if(determ==1)
					{
					
						if(!strcmp (data.name,y))
						{
							printf("Person info:");
							printf("Name:%s\nSurname:%s\nPhone Number:%s\nDate of Birth:%s\nEmail:%s",data.name,data.surname,data.phonenumber,data.dateofbirth,data.email);
							flag = 1;
						}
					}
						if(determ==2)
					{
					
						if(!strcmp (data.name,y))
						{
							printf("Person info:");
							printf("Name:%s\nSurname:%s\nPhone Number:%s\nDate of Birth:%s\nEmail:%s",data.name,data.surname,data.phonenumber,data.dateofbirth,data.email);
							flag = 1;
						}
					}
				}
				if(flag==0)
				{
					printf("This person is not in the guide.\n");
				}		
			}
			void continuefunction()
			{
				int answer;
				while(1)
				{
					printf("For adding a new person press (1)\n");
					printf("For going back to menu press (2)\n");
					printf("For calling someone press (3)\n");
					printf("For seeing the guide press (4)\n");
					printf("For  exit press (5)");
					scanf("%d",&answer);
					if(answer== 1)
					{
						AddPerson() ; break;
					}
					if(answer== 2)
					{
						main(); break;
					}
					if(answer== 3)
					{
						PersonCheck(); break;
					}
					if(answer== 4)
					{
						Show(); break;
					}
					if(answer== 5)
					{
						exit(1); break;
					}
				}
			}
			
