# AI-POWERED-HEALTH-TRACKER
from datetime import datetime

# Defining class
class healthPredictor:
def __init__(self):
self.entries=[]

# Adding Entries
def add_entry(self,condition,symptoms,medications)
entry={
'id':len(self.entries)+1,
'date':datetime.now().strftime('%Y-%m-%d %H:%m:%S'),
'condition':condition,
'symptoms':symptoma,
'medications':medications
}
self.entries.append(entry)
print("Entry added successfully")

# Viewing Entries
def view_entries(self):
if not self.entries:
print("No Health records found")
return
print("All health entries:")
for entry in self.entries:

# Display Entries
self.display_entry(entry)
def display_entry(self,entry):
print(f"""
ID:{entry['id']}
Date:{entry['date']}
Condition:{entry['condition']}
Symptoms:{entry['symptoms']}
Medications:{entry['symptoms']}
----------------------------------
""")

# Search Entries
def search_entries(self,keyword):
results=[
e for e in self.entries
if keyword.lower() in e['condition'].lower() or keyword in e['date']
]
if not results:
print("No matching entries found")
return
print("f"Found {len(results)} result(s):")
for entry in results:
self.display_entry(entry)

# Edit Entries
def edit_entry(self,entry_id):
for entry in self.entries:
if entry['id']==entry_id:
print("Leave field blank to keep current value")
condition=input(f"New condition [{entry['condition']}]: ") or entry['condition']
symptoms=input(f"New symptoms [{entry['symptoms']}]: ") or entry['symptoms']
medications=input(f"New medications [{entry['medications']}]: ") or entry['medications']
entry.update({
'condition':condition,
'symptoms':symptoms,
'medications':medications,
'date':datetime.now().strftime('%Y-%m-%d %H:%M:%S')
})
print("Entry updated")
return
print("Entry ID not found")

# Delete Entries
def delete_entry(self,entry_id):
for entry in self.entries:
if entry['id']==entry_id:
self.entries.remove(entry)
print("Entry deleted")
return
print("Entry ID not found")

# Create object for Predictor
predictor=HealthPredictor()

# Displaying Menu details
menu="""
============ HealthPredictor ==============
1.Add New Entry
2.View All Entries
3.Search Entries
4.Edit Entry
5.Delete Entry
6.Exit
==========================================
"""
# Main Loop
while True:
try:
print(menu)
choice=input("Select an option (1-6): ").strip()
if choice=='1':
condition=input("Condition: ")
symptoms=input("Symptoms: ")
medications=input("Medications: ")
predictor.add_entry(condition,symptoms,medications)
elif choice=='2':
predictor.view_entries()
elif choice=='3':
keyword=input("Search by date(YYYY-MM-DD): ")
predictor.search_entries(keyword)
elif choice=='4':
try:
entry_id=int(input("Enter Entry ID to edit: "))
predictor.edit_entry(entry_id)
except ValueError:
print("Please enter a valid numeric ID")
elif choice=='5':
try:
entry_id=int(input("Enter Entry ID to delete: "))
predictor.delete_entry(entry_id)
except ValuError:
print("Please enter a valid numeric ID")
elif choice=='6':
print("Exiting. Stay healthy")
break
else:
print("Invalid option. Please select between 1 and 6")
except keyboardInterrupt:
print("Program interrupted by user. Exiting")
break
