## **Date Table** = ADDCOLUMNS(CALENDAR(MIN(Table1\[Date]),MAX(Table1\[Date])),"Year", YEAR(\[Date]),"Month", FORMAT(\[Date],"MMM"),"Month No", MONTH(\[Date]))

## **Total Salary Expense** = SUM(Table1\[Salary])

## **Total Items** = COUNTA(Table1\[Item])

## **Total Employees** = DISTINCTCOUNT(Table1\[Emp\_ID])

## **Total Bonus Paid** = SUM(Table1\[Bonus])

## **PY Salary** = CALCULATE(\[Total Salary Expense],SAMEPERIODLASTYEAR('Date Table'\[Date]))

## **PY Low Stock Items** = CALCULATE(\[Low Stock Items],SAMEPERIODLASTYEAR('Date Table'\[Date]))

## **PY Employee** = CALCULATE(\[Total Employees],SAMEPERIODLASTYEAR('Date Table'\[Date]))

## **PY Bonus** = CALCULATE(\[Total Bonus Paid],SAMEPERIODLASTYEAR('Date Table'\[Date]))

## **PY AVG Salary** = CALCULATE(\[AVG Salary],SAMEPERIODLASTYEAR('Date Table'\[Date]))

## **PY AVG Bonus** = CALCULATE(\[AVG Bonus],SAMEPERIODLASTYEAR('Date Table'\[Date]))

## **Salary Growth** = DIVIDE(\[Total Salary Expense]-\[PY Salary],\[PY Salary])

## **Salary Growth %** = VAR growthval =\[Salary Growth] VAR arrow =IF(\[Salary Growth]>=0,"▲","▼")RETURN arrow\& " "\& FORMAT(\[Salary Growth],"0.0%")

## **Low Stock Items** = CALCULATE(COUNTROWS('Table1'),Table1\[Status]="LOW")

## **Low Stock Item Growth %** = VAR growthval =\[Low Stock Item Growth] VAR arrow=IF(\[Low Stock Item Growth]>=0,"▲","▼")RETURN arrow\& " "\&FORMAT(\[Low Stock Item Growth],"0.0%")

## **Low Stock Item Growth** = DIVIDE(\[Low Stock Items]-\[PY Low Stock Items],\[PY Low Stock Items])

## **Employee Growth %** = VAR growthval =\[Employee Growth] VAR arrow=IF(\[Employee Growth]>=0,"▲","▼")RETURN arrow\& " "\& FORMAT(\[Employee Growth],"0.0%")

## **Employee Growth** = DIVIDE(\[Total Employees]-\[PY Employee],\[PY Employee])

## **Bonus Growth %** = VAR growthval =\[Bonus Growth] VAR arrow=IF(\[Bonus Growth]>=0,"▲","▼")RETURN arrow\& " "\&FORMAT(\[Bonus Growth],"0.0%")

## **Bonus Growth** = DIVIDE(\[Total Bonus Paid]-\[PY Bonus],\[PY Bonus])

## **AVG Salary Growth %** = VAR growthval=\[AVG Salary Growth] VAR arrow=IF(\[AVG Salary Growth]>=0,"▲","▼")RETURN arrow\& " " \&FORMAT(\[AVG Salary Growth],"0.0%")

## **AVG Salary Growth** = DIVIDE(\[AVG Salary]-\[PY AVG Salary],\[PY AVG Salary])

## **AVG Salary** = AVERAGE(Table1\[Salary])

## **AVG Bonus Growth %** = VAR growthval =\[AVG Bonus Growth] VAR arrow =IF(\[AVG Bonus Growth]>=0,"▲","▼")RETURN arrow\& " "\&FORMAT(\[AVG Bonus Growth],"0.0%")

## **AVG Bonus Growth** = DIVIDE(\[AVG Bonus]-\[PY AVG Bonus],\[PY AVG Bonus])

## **AVG Bonus** = AVERAGE(Table1\[Bonus])

