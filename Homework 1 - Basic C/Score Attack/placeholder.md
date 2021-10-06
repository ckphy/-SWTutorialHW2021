# Upload your Homework here
 
### Please upload your code here

#include <stdio.h>
#include <string.h>
#include <stdbool.h>

int count(char letters[],char letter){
  int count = 0;
  for(int i=0; i<strlen(letters); i++){
    if(letter == letters[i]) count++;
  }
  return count;
}

bool exist(char exist_letters[], char letter){
  for (int i=0; i<strlen(exist_letters); i++){
    if(letter == exist_letters[i]) return true;
  }
  return false;
}

void create_exist_letters_list(char* exist_letters, char letters[],int *num_of_exist_letter){
  for(int i=0; i<strlen(letters); i++){
    if (*num_of_exist_letter == 0) {
      exist_letters[*num_of_exist_letter] = letters[i]; (*num_of_exist_letter)++;}
    else if (exist(exist_letters, letters[i])) {continue;}
    else {
      exist_letters[*num_of_exist_letter] = letters[i]; (*num_of_exist_letter)++;}
  }
}

int count_existence(char letters[],char letter){
  int count = 0;
  for(int i=0; i<strlen(letters); i++){if(letter == letters[i])  count++;}
  return count;
}

void create_existence_counts(char letters[],int existence_counts[],char exist_letters[], int num_of_exist_letter){
  for(int i=0; i<num_of_exist_letter; i++){
    existence_counts[i] = count_existence(letters, exist_letters[i]);
  }
}

void sort_by_ascending(int existence_counts[], char exist_letters[], int num_of_exist_letter){
  for(int i=0; i<num_of_exist_letter; i++){
    int exchange_i =0;
    for(int j=0; j<num_of_exist_letter; j++){
      if(existence_counts[j] < existence_counts[i]) exchange_i=j;
    }
    
  }
}

int main() {
  char letters[256] = {0};
  char temp_letters[256] = {0};
  char type_list[256] = {0};
  printf("Enter a list of letter\n");
  scanf("%s", letters);

  char exist_letters[256]={0}; int num_of_exist_letter=0;
  create_exist_letters_list(exist_letters,letters,&num_of_exist_letter);
  int existence_counts[256]={0};
  create_existence_counts(letters, existence_counts, exist_letters, num_of_exist_letter);

  int max_count =0;

  

  strcpy(temp_letters,letters);
}
