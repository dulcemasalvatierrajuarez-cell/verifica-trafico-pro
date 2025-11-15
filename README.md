# verifica-trafico-pro
Verificador Anti-Scam con GA4
# verifica_trafico_pro.py
# Salva MX | 7 canciones | 3 juegos | Anti-scam

import requests
from urllib.parse import urlparse, parse_qs

def verificar(url):
    q = parse_qs(urlparse(url).query)
    source = q.get('utm_source', [None])[0]
    medium = q.get('utm_medium', [None])[0]
    
    if source and medium == 'paid':
        print("TRÁFICO REAL → GA4")
    else:
        print("SCAM DETECTADO")

verificar("https://salvaa.mx/?utm_source=instagram&utm_medium=paid")
