#include <stdio.h>
#include <stdlib.h>
#include <string.h>
	
int main()
{    
	int i, string_length=0;    
	int num, Crypt_key=0, Encrypt_key=0;    
	char string[80]="";
    
    printf("Enter the sentence (cipher text): ");   
	gets(string);
	
	printf("Select way: Crypt (1), Encrypt (0): ");    
    scanf("%d",&num);
    
    string_length=strlen(string);
    
    if(num==1)    
    {        
        printf("Enter the crypt key number(1 ~ 25): ");        
        scanf("%d",&Crypt_key);
        
        for(i=0;i<string_length;i++)        
        {           
            if(string[i]>='A'&&string[i]<='Z')           
            {                
                string[i]-='A';
                
                if((string[i]+Crypt_key)<0)                
                {                    
                    string[i]+=26;                
                }
                
                string[i]=(string[i]+Crypt_key)%26;
                string[i]+='A';           
            }        
        }
        
        printf("Key number is %d\n",Crypt_key);        
        puts("[Crypt Result] \n");        
        puts(string);    
    }
    
    else if(num==0)    
    {        
        printf("Enter the Encrypt key number(-1 ~ -25): ");        
        scanf("%d",&Encrypt_key);
        
        for(i=0;i<string_length;i++)        
        {            
            if(string[i]>='A'&&string[i]<='Z')            
            {                
                string[i]-='A';
                
                if((string[i]+Encrypt_key)<0)
                {                    
                    string[i]+=26;                
                }
                
                string[i]=(string[i]+Encrypt_key)%26;                
                string[i]+='A';            
                }        
            }
            
        printf("Key number is %d\n",Encrypt_key);        
        puts("[Encrypt Result]");        
        puts(string);    
        }
        
    else    
    {        
        printf("Try again");    
    }
    
    return 0;
}
