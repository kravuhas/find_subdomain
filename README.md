# find_subdomain
import dns.resolver

def find_subdomains(domain):
subdomains = ['www', 'mail', 'ftp', 'dev', 'org ,''http']
for sub in subdomains:
try:
full_domain = f"{sub}.{domain}"
result = dns.resolver.resolve(full_domain, 'A')
print(f"dominio encontrado: {full_domain} -> {result[0].address}")
except dns.resolver.NoAnswer:
print(f"nao encontramos nada mane{full_domain}")
except Exception as e:
print(f"o erro esta com a bunda sentada {full_domain}: {str(e)}")

domain = '[exemplo.com](http://exemplo.com/)'
find_subdomains(domain)

import requests

def check_headers(url):
try:
response = requests.get(url)
print(f"Status code: {response.status_code}")
print("Cabeçalhos HTTP:")
for header, value in response.headers.items():
print(f"{header}: {value}")
except requests.exceptions.RequestException as e:
print(f"boa sorte na proxuma mano {url}: {e}")

url = '[http://exemplo.com](http://exemplo.com/)'
check_headers(url)
