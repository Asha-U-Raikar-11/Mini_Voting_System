#include <stdio.h>
int bjp=0, congress=0, aap=0, bsp=0, jds=0;

void Result()
{
    int wonTheVote;
    if (bjp > congress && bjp > aap && bjp > bsp && bjp > jds)
    {
        printf("\n**BJP[@] won the election**\n\n");
        printf("Total vote of BJP[@] : %d\n",bjp);
        wonTheVote=bjp-congress;
        printf("BJP[@] won by %d votes to Congress[#]\n",wonTheVote);
        wonTheVote=bjp-aap;
        printf("BJP[@] won by %d votes to AAP[$]\n",wonTheVote);
        wonTheVote=bjp-bsp;
        printf("BJP[@] won by %d votes to BSP[%%]\n",wonTheVote);
        wonTheVote=bjp-jds;
        printf("BJP[@] won by %d votes to JDS[&]\n",wonTheVote);
    }
    else if (congress > aap && congress > bsp && congress > jds)
    {
        printf("\n**Congress[#] won the election**\n\n");
        printf("Total vote of Congress[#] : %d\n",congress);
        wonTheVote=congress-bjp;
        printf("Congress[#] won by %d votes to BJP[@]\n",wonTheVote);
        wonTheVote=congress-aap;
        printf("Congress[#] won by %d votes to AAP[$]\n",wonTheVote);
        wonTheVote=congress-bsp;
        printf("Congress[#] won by %d votes to BSP[%%]\n",wonTheVote);
        wonTheVote=congress-jds;
        printf("Congress[#] won by %d votes to JDS[&]\n",wonTheVote);
    }
    else if (aap > bsp && aap > jds)
    {
        printf("\n**AAP[$] won the election**\n\n");
        printf("Total vote of AAP[$] : %d\n",aap);
        wonTheVote=aap-congress;
        printf("AAP[$] won by %d votes to Congress[#]\n",wonTheVote);
        wonTheVote=aap-bjp;
        printf("AAP[$] won by %d votes to BJP[@]\n",wonTheVote);
        wonTheVote=aap-bsp;
        printf("AAP[$] won by %d votes to BSP[%%]\n",wonTheVote);
        wonTheVote=aap-jds;
        printf("AAP[$] won by %d votes to JDS[&]\n",wonTheVote);
    }
     else if (bsp > jds)
    {
        printf("\n**BSP[%%] won the election**\n\n");
        printf("Total vote of BSP : %d\n",aap);
        wonTheVote=bsp-congress;
        printf("BSP[%%] won by %d votes to Congress[#]\n",wonTheVote);
        wonTheVote=bsp-bjp;
        printf("BSP[%%] won by %d votes to BJP[@]\n",wonTheVote);
        wonTheVote=bsp-aap;
        printf("BSP[%%] won by %d votes to AAP[$]\n",wonTheVote);
        wonTheVote=bsp-jds;
        printf("BSP[%%] won by %d votes to JDS[&]\n",wonTheVote);
    }
    else if(bjp == congress && bjp == aap && bjp == bsp && bjp == jds)
    {
        printf("\n No one won the election\n\n");
        printf("            BJP---Congress---AAP---BSP---JDS\n");
        printf("Total Vote   %d       %d        %d     %d        %d\n",bjp,congress,aap,bsp,jds);
    }
    else
    {
        printf("\n**JDS won the election**\n\n");
        printf("Total vote of JDS[&] : %d\n",jds);
        wonTheVote=jds-congress;
        printf("JDS[&] won by %d votes to Congress[#]\n",wonTheVote);
        wonTheVote=jds-aap;
        printf("JDS[&] won by %d votes to AAP[$]\n",wonTheVote);
        wonTheVote=jds-bjp;
        printf("JDS[&] won by %d votes to BJP[@]\n",wonTheVote);
        wonTheVote=jds-bsp;
        printf("JDS[&] won by %d votes to BSP[%%]\n",wonTheVote);
    }
}
void evaluateVotes(int votes)
{
    switch (votes)
    {
    case 1:
        bjp+=1;
        break;
    case 2:
        congress+=1;
        break;
    case 3:
        aap+=1;
        break;
    case 4:
        bsp+=1;
        break;
    case 5:
        jds+=1;
        break;
    }
}
int main()
{
    int choose,age ;
    
    
        printf("\n****Welcome to the simple voting system project****\n\n");
        printf("\n Enter your age : \n");
        scanf("%d",&age);
        if(age>=18)
        {
        	printf("****You are eligible to vote****j");
        	
		}
		else
		{
			printf("****You are not eligible to vote(You are too young have patience)****");
			return 0;
		}
		
        printf("\n!!!!^^^^Voting is not only our right-it is our power^^^^!!!!\n\n");
        printf("                         MP election                        \n\n");
        printf("\n*********************---------------------*********************\n");
        printf("|           1.BJP[@]             |          2.Congress[#]        |\n");
        printf("\n*********************---------------------*********************\n");
        printf("|           3.APP[$]             |             4.BSP[%%]              |\n");
        printf("\n*********************---------------------*********************\n");
        printf("|           5.JDS[&]             |\n");
        printf("\n^^^^^^^^^^^^^^^^^^^^^!!!!!!!!!!!!!!!!!!!!!^^^^^^^^^^^^^^^^^^^^^\n\n");
    do
    {    
        printf("Press 1 to vote BJP[@]\n");
        printf("Press 2 to vote Congress[#]\n");
        printf("Press 3 to vote APP[$]\n");
        printf("Press 4 to vote BSP[%%]\n");
        printf("Press 5 to vote JDS[&]\n");
        printf("Press 6 to show election result\n");
        printf("Please choose : ");
        scanf("%d", &choose);
        if (choose==6)
        {
            Result();
        }
		else
        {
            evaluateVotes(choose);            
        } 
        printf("\n\n");
    } while (choose != 6);
}
