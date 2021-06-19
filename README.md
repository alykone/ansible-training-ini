# ansible-training-ini

Pour verifier que le service httpd a bien demarré sur les hotes serveur2 et serveur3
avec la commande systemctl

#systemctl -H serveur2 status htppd

Commande pour voir si les paquets mariadb sont bien installés sur les serveurs:

# ansible serveur2,serveur3 -i machines.ini -m shell -a 'rpm -qa mariadb*'

commande ad hoc pour verifier que le service mariadb est bien demarré:

#ansible serveur2,serveur3 -i machines.ini -m service -a 'name=mariadb state=started'

Verifier que le port est ouvert dans le firewall avec une commande ad hoc:
# ansible all -m shell -a 'firewall-cmd --list-service'
