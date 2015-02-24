# Drupal Code Grading Standards
The idea behind the drupal code grading standards is to determine the quality of a contributed module in a quick way. These standards will be used in the Drupal code grader tool. After every new release of a Drupal version, all core
modules will get analyzed seperately and the outcome of this analysis will become the new standard. Then a developer can analyze his code against these standards to check the overall quality of his/her code.

## How to understand the yaml files

### What's YAML?
YAML Ain't a markup language. YAML is a human friendly data serialization standard for all programming languages.

### One yaml file per Major Drupal version
As a Drupal developer you will understand that there's a huge difference in the way the Drupal core is build in Drupal 8 compared to Drupal 7. Therefore I decided to maintain different standards. If you want to analyze your Drupal 7 module, you will use the drupal-7.yml file. Otherwise, you will use the drupal-8.yml file.

### How the YAML file is build
The main key indicates the main subject of the analysis. E.g. 'checkstyle' contains all standards for analysis done by the checkstyle tool.
Every main subject can contain different child subjects. E.g. 'checkstyle' contains the cshigh and the csnormal metrics that will contain seperate standards for respective High and Normal prioritized issues.
Every metric contains 5 settings;

  - metric : The machine name for the metric
  - title : A short title for administrative purposes
  - description : A full description to make it easy to understand what has been analyzed
  - reverse : This is a boolean value that will indicate wether the A+ grade contains the lowest or the highest value. If reverse is set to 1, the A+ value will contain the highest possible value.
  - grades : A list of all grades (starting with A+ to E) with their starting value.