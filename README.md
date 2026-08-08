Here’s a beginner-friendly **AI Resume Analyzer** in Java. This version analyzes resume text using keyword matching and gives a simple skill score.

### `AIResumeAnalyzer.java`

```java
import java.util.*;

public class AIResumeAnalyzer {

    static Scanner sc = new Scanner(System.in);

    static String[] skills = {
        "java", "python", "c++", "javascript",
        "html", "css", "sql", "spring boot",
        "mysql", "git", "github", "docker",
        "machine learning", "data structures"
    };

    public static void main(String[] args) {

        System.out.println("===== AI RESUME ANALYZER =====");
        System.out.println("Paste your resume text below.");
        System.out.println("Type END when finished:\n");

        StringBuilder resume = new StringBuilder();

        while (true) {
            String line = sc.nextLine();

            if (line.equalsIgnoreCase("END")) {
                break;
            }

            resume.append(line).append(" ");
        }

        String text = resume.toString().toLowerCase();

        System.out.println("\n===== RESUME ANALYSIS =====");

        int foundSkills = 0;

        System.out.println("\nDetected Skills:");

        for (String skill : skills) {
            if (text.contains(skill.toLowerCase())) {
                System.out.println("✓ " + skill);
                foundSkills++;
            }
        }

        int score = (foundSkills * 100) / skills.length;

        System.out.println("\nSkill Score: " + score + "%");

        if (score >= 70) {
            System.out.println("Excellent technical skill coverage!");
        } else if (score >= 40) {
            System.out.println("Good skill coverage. Consider adding more relevant skills.");
        } else {
            System.out.println("Improve your resume by adding relevant technical skills.");
        }

        System.out.println("\n===== Suggestions =====");

        if (!text.contains("project")) {
            System.out.println("- Add your projects.");
        }

        if (!text.contains("education")) {
            System.out.println("- Add an Education section.");
        }

        if (!text.contains("experience")) {
            System.out.println("- Add your work or internship experience.");
        }

        if (!text.contains("github")) {
            System.out.println("- Add your GitHub profile.");
        }

        System.out.println("\nAnalysis completed!");
    }
}
```

### `README.md`

# AI Resume Analyzer

A Java-based resume analysis tool that identifies technical skills and provides a basic resume score and improvement suggestions.

## Features

* Analyze resume text
* Detect technical skills
* Calculate skill score
* Identify missing resume sections
* Provide improvement suggestions

## Technologies

* Java
* String Processing
* ArrayList
* Scanner
* Object-Oriented Programming

## How to Run

1. Clone the repository.
2. Make sure Java JDK is installed.
3. Open the project in a Java IDE.
4. Compile `AIResumeAnalyzer.java`.
5. Run the program.
6. Paste your resume text and type `END`.

## Project Structure

```text
AI-Resume-Analyzer/
│
├── AIResumeAnalyzer.java
└── README.md
```

## Example

```text
===== AI RESUME ANALYZER =====

Detected Skills:

✓ java
✓ sql
✓ spring boot
✓ mysql
✓ git
✓ github

Skill Score: 42%

Good skill coverage. Consider adding more relevant skills.

===== Suggestions =====
- Add your projects.
- Add your work or internship experience.

Analysis completed!
```

## Future Improvements

* PDF/DOCX resume upload
* AI-powered resume analysis
* Job description matching
* ATS score calculation
* Skill recommendations
* Resume improvement suggestions
* Spring Boot web interface

## Note

This is an educational project. The current version uses keyword matching rather than a real AI/ML model.

## Author
Keerthi
