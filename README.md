 ```
# Excel_Automation

This Python script automates the process of updating prices in an Excel spreadsheet. 

## Step-by-Step Explanation

###  1. Import the necessary libraries

The first step is to import the necessary libraries. In this case, we need the `openpyxl` library to load and manipulate the Excel spreadsheet, and the `matplotlib` library to create the bar chart.

```python
import openpyxl as xl
from openpyxl.chart import BarChart, Reference
```

### 2. Load the Excel workbook

Next, we need to load the Excel workbook that we want to update. We do this using the `load_workbook()` function from the `openpyxl` library.

You can easily perform operations by simply replacing 'test1.xlsx' with the name of your own file, allowing you to work seamlessly with your customized Excel files.


```python
filename = "test1.xlsx"

wb = xl.load_workbook(filename)
```

### 3. Get the worksheet that we want to update

Once we have loaded the workbook, we need to get the worksheet that we want to update. In this case, we want to update the worksheet named "Sayfa1", so we use the `get_sheet_by_name()` function to get it.

```python
sheet = wb["Sayfa1"]
```

### 4. Update the prices in the worksheet

Next, we need to update the prices in the worksheet. We do this by looping through the rows in the worksheet and updating the value of the cell in column 5 with the corrected price. The corrected price is calculated by multiplying the original price by 0.9.

```python
for row in range(2, sheet.max_row + 1):
    cell = sheet.cell(row, 4)
    
    corrected_price = cell.value * 0.9
    corrected_price_cell = sheet.cell(row, 5)
    corrected_price_cell.value = corrected_price
```

### 5. Create a bar chart of the updated prices

Finally, we want to create a bar chart of the updated prices. We do this using the `BarChart` class from the `matplotlib` library. We add the data to the chart using the `add_data()` function, and then we add the chart to the worksheet using the `add_chart()` function.

```python
values = Reference(sheet, min_row=2, max_row=sheet.max

Generated by [BlackboxAI](https://www.useblackbox.ai)