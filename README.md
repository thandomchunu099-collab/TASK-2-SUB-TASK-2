# TASK-2-SUB-TASK-2// ============================================================
// PAT 2 - Subtask 2: Morse Code Translator
// This program translates an English message into Morse code.
// Each letter is displayed with its Morse code representation,
// followed by the full translated message on a single line.
// ============================================================

#include <iostream>
#include <string>
using namespace std;

int main() {

    // --------------------------------------------------------
    // MORSE CODE ARRAY
    // Stores the Morse code for each letter A to Z
    // Index 0 = A, Index 1 = B, ..., Index 25 = Z
    // Dot represented by ASCII 46 (.)
    // Dash represented by ASCII 45 (-)
    // --------------------------------------------------------
    string morseCode[26] = {
        ".-",    // A
        "-...",  // B
        "-.-.",  // C
        "-..",   // D
        ".",     // E
        "..-.",  // F
        "--.",   // G
        "....",  // H
        "..",    // I
        ".---",  // J
        "-.-",   // K
        ".-..",  // L
        "--",    // M
        "-.",    // N
        "---",   // O
        ".--.",  // P
        "--.-",  // Q
        ".-.",   // R
        "...",   // S
        "-",     // T
        "..-",   // U
        "...-",  // V
        ".--",   // W
        "-..-",  // X
        "-.--",  // Y
        "--.."   // Z
    };

    // --------------------------------------------------------
    // INPUT
    // Prompt the user to enter a message
    // --------------------------------------------------------
    string message;
    cout << "========================================" << endl;
    cout << "       MORSE CODE TRANSLATOR            " << endl;
    cout << "========================================" << endl;
    cout << "Enter a message to translate: ";
    getline(cin, message); // Accept full line including spaces

    cout << "\n--- Morse Code for Each Letter ---\n" << endl;

    // --------------------------------------------------------
    // PROCESSING & OUTPUT PART 1
    // Display each letter with its Morse code on a new line
    // Format: "A: .-"
    // --------------------------------------------------------
    string fullMorse = ""; // Will store the complete Morse message

    for (int i = 0; i < message.length(); i++) {

        char currentChar = message[i]; // Get current character

        // Convert lowercase letters to uppercase
        if (currentChar >= 'a' && currentChar <= 'z') {
            currentChar = toupper(currentChar);
        }

        // Check if character is a valid letter (A-Z)
        if (currentChar >= 'A' && currentChar <= 'Z') {

            // Calculate index in morseCode array (A=0, B=1, etc.)
            int index = currentChar - 'A';

            // Display the letter and its Morse code
            cout << currentChar << ": " << morseCode[index] << endl;

            // Add Morse code to full message string
            // Separate letters with three spaces
            if (fullMorse != "") {
                fullMorse += "   "; // Three spaces between letters
            }
            fullMorse += morseCode[index];
        }
        // Non-alphanumeric characters and numbers are ignored
        // as per program requirements
    }

    // --------------------------------------------------------
    // OUTPUT PART 2
    // Display the complete Morse code message on one line
    // --------------------------------------------------------
    cout << "\n--- Full Morse Code Message ---" << endl;
    cout << fullMorse << endl;
    cout << "\n========================================" << endl;

    return 0;
}
