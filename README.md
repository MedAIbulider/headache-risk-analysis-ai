patient_name = "suresh"
age = 50
bp = 140
sugar = 180

print("Patient:",patient_name)
print("Age:", age)
print("Bp:", bp)
print("Sugar:", sugar)

if bp >= 140:
    print("BP status: High BP")
    else:
    print("BP status: Normal BP")

if sugar >=180:
    print("Sugar status: High super")
else:
    print("Sugar Status: Normal sugar")

if bp >= 140 and sugar >= 180:
    print("Final Risk: High Risk Patient")
else:
    print("Final Risk: Low/Moderate Risk Patient")


Patients = [
    {"name": "suresh", "age" : 50, "bp": 140, "sugar": 180},
    {"name": "ramesh", "age" : 45, "bp": 120, "sugar": 150},
    {"name": "mahesh", "age" : 60, "bp": 160, "sugar": 220},
]

for patient in Patients:
    print("Patient Name:", patient["name"])
    print("Age:", patient["age"])
    print("Bp:", patient["bp"])
    print("Sugar:", patient["sugar"])

    if patient["bp"] >= 140 and patient["sugar"] >= 180:
        print("Final Risk: High Risk Patient")
    else:
        print("Final Risk: Low/Moderate Risk Patient")

    print("---------------------")

import pandas as pd

patients =[
    {"name": "suresh", "age" :50, "bp": 140, "sugar": 180},
    {"name": "ramesh", "age" :45, "bp": 120, "sugar": 150},
    {"name": "mahesh", "age" :60, "bp": 160, "sugar": 220},
]

df= pd.DataFrame(patients)

df["risk_status"] = df.apply(
    lambda row: "High Risk" if row["bp"] >=140 and row["sugar"] >= 180 else "Low/Moderate Risk", axis=1
)

print(df)
high_risk_patients = df[df["risk_status"] == "High Risk"]

print(high_risk_patients)
high_risk_count = len(high_risk_patients)

print("Total of High Risk Patients:", high_risk_count)

total_patients = len(df)
print("Total Patients:", total_patients)

high_risk_percentage = (high_risk_count / total_patients) * 100

print("Total Patients:", total_patients)
print("High Risk Patients:",high_risk_count)
print("Percentage of High Risk Patients:", high_risk_percentage)
import matplotlib.pyplot as plt

risk_counts = df["risk_status"].value_counts()

print(risk_counts)

plt.figure(figsize=(6,4))
risk_counts.plot(kind="bar")

plt.xlabel("Risk Status")
plt.ylabel("Count")
plt.title("Patient Risk Status")

plt.show()
df.to_csv("patients_data.csv", index=False)
print("CSV file saved suceessful")
plt.figure(figsize=(6,4))

plt.title("Patient Risk Status")
plt.xlabel("Risk Status")
plt.ylabel("Number of patients")

plt.savefig("risk_status_chart.png")
plt.show()

print("chart image saved successfully")
