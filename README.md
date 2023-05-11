# Write-a-Python-program-to-print-a-dictionary-in-table-format

def print_table(data):
 # Get the headers and the maximum width of each column
 headers = data.keys()
 column_widths = [max(len(str(key)), max(len(str(value)) for value in data[key])) for key in 
headers]
 # Print the headers
 print('| ' + ' | '.join(header.ljust(width) for header, width in zip(headers, column_widths)) + ' 
|')
 # Print the separator
 print('|-' + '-|-'.join('-' * width for width in column_widths) + '-|')
 # Print the data
 for row in zip(*data.values()):
 print('| ' + ' | '.join(str(value).ljust(width) for value, width in zip(row, column_widths)) + ' |')
# Example usage
data = {'Name': ['Alice', 'Bob', 'Charlie'], 'Age': [25, 30, 35], 'Occupation': ['Engineer', 
'Manager', 'Developer']}
print_table(data)
