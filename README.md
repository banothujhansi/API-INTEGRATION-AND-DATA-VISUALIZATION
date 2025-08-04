# API-INTEGRATION-AND-DATA-VISUALIZATIONimport requests
import matplotlib.pyplot as plt

url = "https://disease.sh/v3/covid-19/all"
response = requests.get(url)
data = response.json()

labels = ['Active', 'Recovered', 'Deaths']
sizes = [data['active'], data['recovered'], data['deaths']]

# Plot
plt.pie(sizes, labels=labels, autopct='%1.1f%%', startangle=90)
plt.title('Global COVID-19 Case Distribution')
plt.show()
