# CSE-103-Mini-Project
03.09.2022


#include<stdio.h>
#include<string.h>

struct user
{

    char name[100] ;
    char phn[20] ;
    char address[200] ;
    int activation ;
    
}userList[10000];

struct book
{

    char name[100] ;
    char author[100] ;
    char ISBN[50] ;
    int numCopy ;
    
}bookList[1000];

struct mapping
{

    char userPhn[20] ;
    char bookISBN[100] ;
    
}assignBook[10000];

int main()
{

    int choice ;
    int num = 0 ;
    int numBook = 0 ;
    int count = 0 ;
    char buf[10] ;
    while(true){
        printf("Press 1 for Registration\n") ;
        printf("Press 2 for Search\n") ;
        printf("Press 3 for Borrow\n") ;
        printf("Press 4 for Return\n") ;
        printf("Press 5 for Deactivate\n") ;
        printf("Press 6 for Add book\n") ;
        printf("Press 7 for Update user\n")
        printf("Press 8 for Update book\n")
        printf("Press 9 for Exit\n") ;

        printf("Option: ") ;
        scanf("%d", &choice) ;
        gets(buf) ;

        if(choice == 1){
            printf("Name: ") ;
            gets(userList[num].name) ;
            printf("Phone: ") ;
            gets(userList[num].phn) ;
            printf("Address: ") ;
            gets(userList[num].address) ;
            userList[num].activation = 1 ;
            num++ ;
        }
        else if(choice == 2){
            int i, option ;
            printf("Press 1 for search user by phone number\n") ;
            printf("Press 2 for search book by ISBN number\n") ;

            printf("Option: ") ;
            scanf("%d", &option) ;
            gets(buf) ;

            if(option == 1){
                int flag = 0 ;
                char usercell[20] ;
                printf("Enter user phone number: ") ;
                gets(usercell) ;
                for(i = 0 ; i < num ; i++){
                    if(strcmp(usercell, userList[i].phn) == 0){
                        flag = 1 ;
                        break ;
                    }
                }
                if(flag == 1){
                    if(userList[i].activation == 1){
                        printf("Active user\n") ;
                        printf("Name: %s\n", userList[i].name) ;
                        printf("Cell: %s\n", userList[i].phn) ;
                        printf("Address: %s\n", userList[i].address) ;
                    }
                    else{
                        printf("Inactive user\n") ;
                        printf("Name: %s\n", userList[i].name) ;
                        printf("Cell: %s\n", userList[i].phn) ;
                        printf("Address: %s\n", userList[i].address) ;
                    }
                }
            }

            else if(option == 2){
                printf("Implement this features for search book\n") ;
            }
        }

        else if(choice == 3){
            char bookName[100] ;
            int i, flag = 0 ;
            printf("Enter book name: ") ;
            gets(bookName) ;
            for(i = 0 ; i < numBook ; i++){
                if(strcmp(bookName, bookList[i].name) == 0){
                    flag = 1 ;
                    break ;
                }
                if(flag == 1){
                    if(bookList[i].numCopy == 0){
                        printf("Insufficient copies\n") ;
                    }
                    else{
                        char cell[100] ;
                        printf("Cell: ") ;
                        gets(cell) ;
                        bookList[i].numCopy-- ;
                        strcpy(assignBook[count].bookISBN, bookList[i].ISBN) ;
                        strcpy(assignBook[count].userPhn, cell) ;
                        count++ ;
                    }
                }
                else{
                    printf("Requested book not found\n") ;
                }
            }
        }
        else if(choice == 4){
            printf("To be implemented\n") ;
        }
        else if(choice == 5){
            printf("To be implemented\n") ;
        }
        else if(choice == 6){
                ///Implement this part by taking input from keyboard.

            strcpy(bookList[0].name , "Teach Yourself C") ;
            strcpy(bookList[0].author , "Herbert Schildt") ;
            strcpy(bookList[0].ISBN , "CB100023") ;
            bookList[0].numCopy = 100 ;


            strcpy(bookList[1].name , "Introduction to Algorithm") ;
            strcpy(bookList[1].author , "Thomas H. Cormen") ;
            strcpy(bookList[1].ISBN , "IS2011000") ;
            bookList[1].numCopy = 60 ;

            numBook = 2 ;

            printf("Implement the feature to add book from input\n") ;


        }else if(choice == 7){
            printf("To be implemented\n") ;
        }
        else if(choice == 8){
            printf("To be implemented\n") ;
        }
        else if(choice == 9) return 0;
    }
    return 0;
    
}
