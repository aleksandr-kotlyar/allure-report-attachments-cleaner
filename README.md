# allure-report-attachments-cleaner
![views](https://raw.githubusercontent.com/aleksandr-kotlyar/allure-report-attachments-cleaner/traffic-2021/traffic-allure-report-attachments-cleaner/views.svg)
![views](https://raw.githubusercontent.com/aleksandr-kotlyar/allure-report-attachments-cleaner/traffic-2021/traffic-allure-report-attachments-cleaner/views_per_week.svg)
![clones](https://raw.githubusercontent.com/aleksandr-kotlyar/allure-report-attachments-cleaner/traffic-2021/traffic-allure-report-attachments-cleaner/clones.svg)
![clones](https://raw.githubusercontent.com/aleksandr-kotlyar/allure-report-attachments-cleaner/traffic-2021/traffic-allure-report-attachments-cleaner/clones_per_week.svg)

Script to free space from unnecessary AllureReport attachments.

### Usage example
Execute python script file with python and send it AllureReport path and status to filter attachments you want to remove.
```python
python clean_allure_attachments.py allure-report passed
```

### Algorithm
1. From `allure-report/data/test-cases/` files collect all `*.json` files with some "status". As example: "passed".
2. From each collected "passed" test-case jsonFile get all "attachments.source" from "beforeStage" "testStage" "afterStage" steps and sub-steps.
3. Go to `allure-report/data/attachments/` and clean each "attachment.source" one by one.
4. Rewrite all necessary test-cases with empty `"attachments": [ ]`.
