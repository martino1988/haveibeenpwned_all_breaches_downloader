import requests

# handle request
URL = "https://haveibeenpwned.com/api/v3/breaches"
r = requests.get(url = URL)
data = r.json()

# define filename and type
name = "all_breaches"
extension = "txt"
filename = name + "." + extension

# define seperator
sep = "|"

# write columns
columns = ["Title", "BreachDate", "AddedDate", "DataClasses", "IsMalware", "IsSensitive","Domain","IsFabricated", "IsVerified", "ModifiedDate", "Name", "PwnCount", "Description"]
with open(filename, 'w') as file:
  for col in columns:
    file.write(col + sep)
  file.write("\n")


#get all breaches
for d in data:
  data = ""
  for col in columns:
    if col == columns[3]:
      dataclass = d[col]
      str_of_dataclass = ""
      for i in dataclass:
        str_of_dataclass += i + ","
      data += str_of_dataclass + sep
    else:
      data += str(d[col]) + sep
  with open(filename, 'a') as file:
    file.write(str(data)+ "\n")
