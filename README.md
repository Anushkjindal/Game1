#include<stdio.h>
#include<stdlib.h>
#include<time.h>

int snakewatergun(char you, char comp){
    if(you == comp){
        return 0;
    }

if(you=='s' && comp=='g'){
    return -1;
}
else if(you=='g' && comp=='s'){
    return 1;
}

if(you=='w' && comp=='g'){
    return 1;
}
else if(you=='g' && comp=='w'){
    return -1;
}

if(you=='w' && comp=='s'){
    return -1;
}
else if(you=='s' && comp=='w'){
    return 1;
}

}

int main(){
    char you, comp;
    srand(time(0));
    int number = rand()%100 + 1;

    if(number<33){
        comp = 's';
    }

    else if(number>33 && number<66){
        comp = 'w';
    }

    else{
        comp = 'g';
    }

printf("enter 's' for snake, 'w' for water, 'g' for gun\n");
scanf("%c",&you);
int result = snakewatergun(you, comp);
if(result==0){
    printf("game draw\n");
}

else if(result==1){
    printf("you win\n");
}

else{
    printf("you lost\n");
}
printf("you chose %c and comp chose %c." , you, comp);

    return 0;
}
