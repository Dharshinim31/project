#include <stdio.h>

float calculateGST(float price, float gst) {
    return price + (price * gst / 100);
}

int res(int totalTables, int bookedTables) {
    return totalTables - bookedTables;
}

int displayMenu() {
    
      float gst,price;
    printf("\n  Menu list        GST     Price     ");
        gst=2;
        price=100;
        printf("\nChicken briyani  : %.2f : %.2f",gst,price);
        gst = 5;
        price = 150;
        printf("\nFish fry         : %.2f : %.2f",gst,price);
        gst=4;
        price=120;
        printf("\nButter naan      : %.2f : %.2f",gst,price);
        gst=3;
        price=80;
        printf("\nPepper chicken   : %.2f : %.2f",gst,price);
        gst=2;
        price=50;
        printf("\nNoodles          : %.2f : %.2f",gst,price);
        gst=1;
        price=40;
        printf("\nJuices           : %.2f : %.2f",gst,price);
        gst=3;
        price=70;
        printf("\nIce cream        : %.2f : %.2f",gst,price);
        gst=7;
        price=450;
        printf("\nCakes            : %.2f : %.2f",gst,price);
        gst=3;
        price=150;
        printf("\nPasta            : %.2f : %.2f",gst,price);
        gst=3;
        price=80;
        printf("\nStarters         : %.2f : %.2f",gst,price);
          
}

int main() {
    int totalTables=10, bookedTables=5;
    printf("Enter the number of totalTables: %d",totalTables);
    printf("Enter the number of bookedTables: %d",bookedTables);
    int available_tables = res(totalTables, bookedTables);
    printf("Number of available_tables: %d\n", available_tables);

    printf("Tables arrangement\n");
    for (int i = 0; i < available_tables; i++) {
        printf("*");
    }
    printf("\n");

    displayMenu();

    int choice;
    float totalAmount = 0.0;

    printf("\nEnter the item number you want to order (0 to exit): ");
    scanf("%d", &choice);

    while (choice != 0) {
        float price, gst;
        switch (choice) {
            case 1:
                printf("Chicken Biryani\n");
                gst = 2.0;
                price = 100.0;
                break;
            case 2:
                printf("Fish Fry\n");
                gst = 5.0;
                price = 150.0;
                break;
            case 3:
                printf("Butter Naan\n");
                gst=4;
                price=120;
                break;
            case 4:
                printf("Pepper Chicken\n");
                gst=3;
                price=80;
                break;
            case 5:
                printf("Noodles\n");
                gst=2;
                price=50;
                break;
            case 6:
                printf("Juices\n");
                gst=1;
                price=40;
                break;
            case 7:
                printf("Ice cream\n");
                gst=3;
                price=70;
                break;
            case 8:
                printf("Cakes\n");
                gst=7;
                price=450;
                break;
            case 9:
                printf("Pasta\n");
                gst=3;
                price=150;
                break;
            case 10:
                printf("Starters\n");
                 gst=3;
                 price=80;
                break;

            default:
                printf("Invalid choice. Please enter a valid item number.\n");
                continue;
        }

        
        float totalWithGST = calculateGST(price, gst);

        
        totalAmount += totalWithGST;

        scanf("%d", &choice);
    }

    printf("\nTotal Bill Amount: %.2f\n", totalAmount);

    return 0;
}
