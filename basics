import pandas as pd
import pyodbc as odbc
import matplotlib as plt

sql_conn = odbc.connect('DRIVER={SQL Server Native Client 11.0};\
    SERVER=NCIGICSQL02;\
    DATABASE=BNSCoverage;\
    Trusted_Connection=yes') 
query = "SELECT * FROM dbo.TIndicator"
df = pd.read_sql(query, sql_conn)

'''Selecting specific rows and columns'''
Col1_values = ['a','d','g']
Col2_values = ['b','e','h']
Col3_values = ['c','f','i']

df = pd.DataFrame[{"Col1":Col1_values, "Col2":Col2_values, "Col3":Col3_values}]

	Col1, Col2, Col3
0	a	b	c
1	d	e	f
2	g	h	i

# Type your code here:
a_int = np.arange(0,6,1)
b_int = np.arange(0,6,1)

matrix = []
for i in a_int: 
    row_op = []
    for j in b_int:
        row_op.append((i,j))
    matrix.append(row_op)
print(matrix)

[[(0, 0), (0, 1), (0, 2), (0, 3), (0, 4), (0, 5)], 
[(1, 0), (1, 1), (1, 2), (1, 3), (1, 4), (1, 5)], 
[(2, 0), (2, 1), (2, 2), (2, 3), (2, 4), (2, 5)], 
[(3, 0), (3, 1), (3, 2), (3, 3), (3, 4), (3, 5)], 
[(4, 0), (4, 1), (4, 2), (4, 3), (4, 4), (4, 5)], 
[(5, 0), (5, 1), (5, 2), (5, 3), (5, 4), (5, 5)]]


##Explicitly choose rows and columns
df.loc[1:6,["Segment","Priority"]]

##Slice rows by default
df["Row1":"Row3"]
df.head(100)
df.tail()

##Select columns by default
df[["Col1","Col2"]]

'''Table Overall Stats'''

##Data Dictionary with datatype breakdown and memory use
df.info()

##All Stats
df.describe(include = 'all')

##Numeric Stats
df.describe(include = ['O'])

##Set percentiles
df.describe(percentiles = [.25,.5,.75]) 

##Get unique counts for all variables
df.apply(pd.Series.value_counts)

##List of unique values
df["Col3"].unique()

'''Data Conversions'''
##DateTime variables
df['DateVar'] = pd.to_datetime(df['DateVar'])


'''Plotting Data'''
x_values = df['Col1']
y_values = df['Col2']
y2_values = df['Col2'] * 3 - 200

plt.plot(x_values,y_values, c = 'color', label = 'line name')
plt.plot(x_values,y2_values, c = 'color', label = 'line name')
plt.xticks(rotation = 90)
plt.xlabel("X Axis")
plt.ylabel("Y Axis")
plt.set_xlim(xlow, xhigh)
plt.set_ylim(ylow,yhigh)
plt.legend(loc='upper right')
plt.title("Chart Title")
plt.tick_params(bottom="off", top="off", left="off", right="off")
plt.show()


plt.show()
