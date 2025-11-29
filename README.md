#include <stdio.h>
#include <time.h>
#include <unistd.h>   
int main() {
    while (1) {
        time_t now = time(NULL);
        struct tm *t = localtime(&now);
      printf("\033[2J\033[H");
        printf("Digital Clock\n");
        printf("%02d:%02d:%02d\n", t->tm_hour, t->tm_min, t->tm_sec);
        printf("%02d-%02d-%04d\n", t->tm_mday, t->tm_mon + 1, t->tm_year + 1900);
        sleep(1);
    }
    return 0;
}
