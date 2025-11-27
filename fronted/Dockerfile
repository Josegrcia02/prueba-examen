FROM php:8.2-apache

# Instala extensiones necesarias de PHP para MySQL
RUN docker-php-ext-install mysqli pdo pdo_mysql

# --- CAMBIO IMPORTANTE ---
# Copiamos SOLO el contenido de la carpeta 'fronted' a la raíz del servidor Apache.
# Esto pondrá tu index.php directamente donde Apache lo busca.
COPY fronted/ /var/www/html/
# -------------------------

# Habilita mod_rewrite para URLs amigables
RUN a2enmod rewrite

# Ajustamos permisos para que Apache (www-data) sea el dueño de los archivos
RUN chown -R www-data:www-data /var/www/html

EXPOSE 80