#include <stdio.h>
#include <cs50.h>
#include <math.h>

int main(void) {
    // Asks the user to input the amount of change due
    printf("Hey! How much do I owe you in dollars?\n");
    float change_due = GetFloat();
    
    // Makes sure that user cooperates
    while (change_due <= 0) {
        printf("Mmm... How about positive number?\n");
        change_due = GetFloat();
    }
    
    // Converts dollars into cents and rounds the floating variable
    int change_cents = round(change_due * 100);
    
    // Does the rest of the job, which is fairly straight forward
    int coins = 0;
    while (change_cents >= 25) {
        change_cents = change_cents - 25;
        coins ++;
    }
    
    while (change_cents >= 10) {
        change_cents = change_cents - 10;
        coins ++;
    }
    
    while (change_cents >= 5) {
        change_cents = change_cents - 5;
        coins ++;
    }
    
    while (change_cents >= 1) {
        change_cents = change_cents - 0.01;
        coins ++;
    }
    
    printf("The ammount of coins is %i\n", coins);
}
