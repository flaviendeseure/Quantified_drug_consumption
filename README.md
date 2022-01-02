# Quantified drug consumption

![](/src/demo_site_web.gif)

## Getting Started
### Prerequisites
1. Clone the repository
```bash
git clone https://github.com/flaviendeseure/Quantified_drug_consumption.git
```
2. Install python libraries 
```bash
pip install -r requirements.txt
```

### Notebook
Simply launch the notebook on jupyter!

### Website & API
1. Get to the api directory
```bash
cd PATH_TO_API/api 
```
2. Launch the server
```bash
python manage.py runserver
```
**Website**   
Simply browse on the website  
  
**API**  
You can use this python file example (example_api.py)
```python
import requests

age = 18
gender = "Man"
education = "Left school before 16 years"
country = "Australia"
ethnicity = "Asian"
nscore = 12
escore = 16
oscore = 24
ascore = 12
cscore = 17
impulsivity = 1
SS = 1

parameters = [age, gender, education, country, ethnicity, nscore, escore, oscore, ascore, cscore, impulsivity, SS]
parameter_names = ["age", "gender", "education", "country", "ethnicity", "nscore", "escore", "oscore", "ascore", "cscore", "impulsivity", "SS"]

url = 'http://127.0.0.1:8000/api/score/?'

for n, p in zip(parameter_names, parameters):
    url += f"{n}={p}"
    if n != SS:
        url += "&"

r = requests.get(url)

print(r.status_code)
if r.status_code == 200:
    for name, result in r.json().items():
        print(f"{name}: {result}")
else:
    print(r.text)
```
### 


## Contact
!
