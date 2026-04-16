# On choisit l'image officielle d'Apache sur Alpine (très légère)
FROM httpd:2.4-alpine

# On copie notre config modifiée par-dessus celle de base
COPY httpd.conf /usr/local/apache2/conf/httpd.conf
COPY index.html /usr/local/apache2/htdocs/

