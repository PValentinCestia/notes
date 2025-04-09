# Installation de Docker dans Debian 12 sous WSL (Windows 11)

https://docs.docker.com/engine/install/debian/

## 1. Supprimer les paquets pouvant causer des conflits

```bash
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

## 2. Ajouter la clé GPG Docker officielle:

```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

## 3. Ajouter le dépôt aux sources apt:

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
```

## 4. Installer les paquets Docker

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## 5. Lancer l'image "hello-world" afin de vérifier que l'installation s'est bien passée

```bash
sudo docker run hello-world
```

## 6. Permettre la gestion de Docker pour les utilisateurs non-administrateurs

```bash
sudo groupadd docker
```

```bash
sudo usermod -aG docker $USER
```

## 7. Se déconnecter et se reconnecter (ou relancer le terminal) ou lancer la commande suivante pour activer les changements

```bash
newgrp docker
```

## 8. Vérifier que cela fonctionne

```bash
docker run hello-world
```

## Pour plus d'informations :

https://docs.docker.com/engine/install/debian/
