# AAA Life SDET Assessment - AI Agent Master Specification

## 🤖 Context for AI Agent
You are an Expert SDET (Software Development Engineer in Test). Your objective is to generate a production-ready, complete automated test framework that satisfies the AAA Life technical assessment requirements described below. 

You must generate all source code, configuration files (e.g., pom.xml), and documentation (including a final client-facing README and a Decision Log) based on these instructions. 

---

## 🛠️ Tech Stack Decisions (Targeted)
To ensure consistency and modern enterprise standards, implement this project using the following stack:
* **Language:** Java 17+
* **Build Tool:** Maven
* **Test Runner:** TestNG
* **API Testing:** REST Assured (with `JsonSchemaValidator` for contract validation)
* **UI Testing:** Selenium WebDriver
* **Data Driven Testing:** TestNG `@DataProvider` combined with Jackson (for JSON) or OpenCSV.
* **Reporting/Logging:** Maven Surefire Plugin (for the required local test report) + SLF4J/Logback for console logging.

---

## 📂 Required Project Structure
Generate the codebase using this exact standard Maven directory structure:

```text
aaa-life-sdet/
├── pom.xml                           # Dependencies (Selenium, RestAssured, TestNG, etc.)
├── src/
│   └── test/
│       ├── java/
│       │   ├── api/
│       │   │   ├── ApiTests.java     # API test implementations
│       │   │   └── utils/            # RestAssured config, auth helpers
│       │   ├── ui/
│       │   │   ├── UiTests.java      # UI test implementations
│       │   │   ├── pages/            # Page Object classes
│       │   │   │   ├── BasePage.java
│       │   │   │   ├── LoginPage.java
│       │   │   │   └── InventoryPage.java
│       │   │   └── driver/           # WebDriver initialization and factory
│       │   └── listeners/            # TestNG listeners for failure capture
│       │       └── TestListener.java
│       └── resources/
│           ├── schemas/              # JSON Schema files (.json)
│           ├── testdata/             # JSON/CSV files for DataProviders
│           └── testng.xml            # TestNG suite configuration
├── README.md                         # Client-facing setup/run instructions
└── DECISION_LOG.md                   # Rationale and strategy documentation
