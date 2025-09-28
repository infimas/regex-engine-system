# Regex Engine System



This repository implements a **regex engine in C++** using **Thompson's NFA algorithm**.  
Unlike most traditional regex implementations, this avoids pathological backtracking and provides efficient matching.  
The project is provided as a **header-only library** for easy integration.

Modified and maintained by **Md Irfan Mansoori**: [regex-engine-system](https://github.com/infimas/regex-engine-system)

---

## About

The regex engine is designed to be lightweight, fast, and safe from exponential-time backtracking issues.  
It supports essential regex syntax and can be used directly by including the header file.

---

## Supported Regex Syntax

| Syntax | Description |
|--------|-------------|
| `*` | Zero or more of the preceding expression |
| `+` | One or more of the preceding expression |
| `?` | Zero or one of the preceding expression |
| `|` | Alternation |
| `()` | Grouping |
| `a`, `b`, `c`, ... | Any single character |

---

## Usage

To use the regex engine in your project, simply include the header file:

```c++
// Optionally enable caching for performance
#define CACHING

#include "regex.hpp"

int main() {
    // Compile a regex pattern
    Regex r("((ab)*|c)+");

    // Print compiled NFA
    std::cout << r << std::endl;

    // Content to check
    std::string content = "abc";

    if (r.match(content)) {
        std::cout << "Matched!" << std::endl;
    } else {
        std::cout << "Not matched!" << std::endl;
    }

    return 0;
}
