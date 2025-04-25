# duplicates
duplicate_rows = df_arnd[df_arnd.duplicated(keep=False)]
duplicate_rows

# Step 1: Get only the duplicated rows, but drop exact repeats (keep just one of each)
duplicate_rows_unique = df_arnd[df_arnd.duplicated()].drop_duplicates()

# Step 2: Extract just the 'NAME' column from these rows
duplicate_names_column = duplicate_rows_unique[['NAME']]

# Step 3: Display the result
print("Unique duplicated rows - showing only NAME column:")
display(duplicate_names_column)

**#save in to a new csv file****
duplicate_names_column.to_csv('duplicate_names_column', index=False)
print("duplicate_names_column_541.csv")

#To check where it is saved
import os
print(os.getcwd())

#To cross check the values
duplicate_rows_unique.head(10)
