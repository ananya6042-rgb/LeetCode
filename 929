#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char* normalizeEmail(const char* email) {
    char* result = (char*)malloc(105 * sizeof(char)); 
    int i = 0, j = 0;

    // Process local part
    while (email[i] != '\0' && email[i] != '@') {
        if (email[i] == '+') {
            // Skip all characters until '@'
            while (email[i] != '\0' && email[i] != '@') {
                i++;
            }
            break;
        }
        if (email[i] != '.') {   // Ignore dots
            result[j++] = email[i];
        }
        i++;
    }

    // Copy domain part (from '@' onwards)
    while (email[i] != '\0') {
        result[j++] = email[i++];
    }

    result[j] = '\0';
    return result;
}

int numUniqueEmails(char** emails, int emailsSize) {
    char* unique[emailsSize];
    int uniqueCount = 0;

    for (int i = 0; i < emailsSize; i++) {
        char* norm = normalizeEmail(emails[i]);

        int exists = 0;
        for (int k = 0; k < uniqueCount; k++) {
            if (strcmp(unique[k], norm) == 0) {
                exists = 1;
                break;
            }
        }

        if (!exists) {
            unique[uniqueCount++] = norm; // keep it
        } else {
            free(norm); // avoid leak
        }
    }

    // Free all unique emails
    for (int i = 0; i < uniqueCount; i++) {
        free(unique[i]);
    }

    return uniqueCount;
}
f5vgr
