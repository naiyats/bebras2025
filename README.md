import pandas as pd

# Load cleaned Excel file
df = pd.read_excel("hasil_filter.xlsx")

# Group data by school
grouped = df.groupby("Sekolah")

# Export each school into a separate Excel file
for name, group in grouped:
    filename = f"{name.replace(' ', '_')}.xlsx"
    group.to_excel(filename, index=False)
    print(f"File dibuat: {filename}")
