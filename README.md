# 📚 String Control & Manipulation Library (`clsString`)

A comprehensive, production-ready C++ custom utility class (`clsString`) created during the advanced studies with **ProgrammingAdvices (Dr. Mohammed Abu-Hadhoud)**. This library delivers a full suite of highly optimized text-processing operations, including tokenization, string cleaning, memory-efficient analysis, and formatting.

---

## 📌 Project Overview
The standard C++ `std::string` provides basic capabilities, but building high-performance systems and parsing text templates often requires complex wrappers. This project consolidates advanced string operations into an object-oriented capsule, enabling safe mutations, static utility access, and complex chain-processing algorithms.

### ⚡ Key Features & Sub-Systems
* **Advanced Case Formatting:** Methods for lower/upper transforms, single character inversions, and word-by-word title-case conversions (`UpperFirstLetterOfEachWord`).
* **Statistical Metrics & Counting:** Seamless classification counters to filter vowels, uppercase letters, lowercase letters, and specific occurrences (case-insensitive option).
* **Text Tokenization & Parsing:** Complete `Split` engine that extracts substrings into modern `std::vector<string>` collections based on dynamic delimiters.
* **Whitespace Sanitization (Trimming):** Industrial-grade string sanitation implementing `TrimLeft`, `TrimRight`, and full `Trim` structures.
* **Collection Joining Engine:** Overloaded static mechanics to seamlessly stitch data structures (`std::vector` and raw arrays) into delimited, unified text blocks.
* **Structure Inversion & Replacement:** Word-boundary reversing logic and semantic substring replacements (`ReplaceWord`).
* **Data Cleansing:** Automated pipeline to remove punctuation layout and specialized formatting structures (`RemovePunctuations`).

---

## 🏗️ Method Index & Interface
Here are the core functional components integrated inside the `clsString` structure implemented in this library:

| Categorization | Member/Static Function | Objective |
| :--- | :--- | :--- |
| **Properties** | `Length()` | Returns the actual layout count of characters. |
| **Formatting** | `UpperFirstLetterOfEachWord()` / `LowerFirstLetterOfEachWord()` | Toggles capitalization for sentence boundaries. |
| **Case Control** | `UpperAllString()` / `LowerAllString()` / `InvertAllLettersCase()` | Performs character-wide bitwise/case shifts. |
| **Metrics** | `CountCapitalLetters()` / `CountSmallLetters()` / `CountVowels()` | Counts targeted classification groups inside text. |
| **Searching** | `CountSpecificLetter(char, bool matchCase)` | Scans dynamically for specific occurrences. |
| **Sanitation**| `TrimLeft()` / `TrimRight()` / `Trim()` | Removes heavy runtime padding and leading/trailing tabs/spaces. |
| **Splitting** | `Split(string delimiter)` | Breaks continuous arrays into a standard vector token system. |
| **Joining** | `JoinString(vector<string>, string)` / `JoinString(array[], size, string)` | Merges continuous sequences with dynamic spacing. |
| **Data Cleaning**| `RemovePunctuations()` | Strip layouts off terminal control punctuation characters. |

---

## 💻 Technical Usage & Implementation Examples
Below is an end-to-end simulation mapping out how the system handles runtime operations within `main.cpp`:

```cpp
#include <iostream>
#include <vector>
#include "clstring.h"

using namespace std;

int main() {
    // 1. Initializing Custom Wrapper Objects
    clsString String3("hi how are you?");
    cout << "Initial Length = " << String3.Length() << endl; // Output: 15

    // 2. Formatting Boundaries 
    String3.UpperFirstLetterOfEachWord();
    cout << "Formatted Title Case: " << String3.Value << endl; // Output: "Hi How Are You?"

    // 3. String Splitting & Token Collection
    String3.Value = "Welcome to Jordan";
    vector<string> vString = String3.Split(" ");
    cout << "Total Tokens Extracted: " << vString.size() << endl; // Output: 3

    // 4. Advanced Micro-Sanitation (Trimming Mechanics)
    String3.Value = "    Mohammed Abu-Hahdoud     ";
    String3.Trim();
    cout << "Cleaned String: '" << String3.Value << "'" << endl; // Output: "Mohammed Abu-Hahdoud"

    // 5. Array/Vector Structural Stitching (Joining Engine)
    vector<string> vNames = { "Mohammed", "Faid", "Ali", "Maher" };
    cout << "Joined Block: " << clsString::JoinString(vNames, " | ") << endl;

    // 6. Sentence Word Reversal
    String3.Value = "Mohammed Saqer Abu-Hahdoud";
    String3.ReverseWordsInString();
    cout << "Reversed Boundaries: " << String3.Value << endl; // Output: "Abu-Hahdoud Saqer Mohammed"

    return 0;
}
