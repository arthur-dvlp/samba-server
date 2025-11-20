# Passo 1
Atualize o seu sistema e instale o samba com o comando:
sudo apt update && sudo apt install samba -y

Verifique se o serviço está rodando:
sudo systemctl status smbd
Se não estiver, use: 
sudo systemctl start smbd

Para que ele inicie sempre que o servidor ligar, use:
sudo systemctl enable smbd

# Passo 2
Crie a pasta onde serão salvos os arquivos:
sudo mkdir -p /srv/samba/compartilhado
Você pode substituir "compartilhado" pelo nome que achar melhor! Ele só será visível no servidor. O nome que os usuários verão no momento do acesso será definido no arquivo smb.conf mais a frente.
*O parâmetro -p serve para garantir que a pasta seja criada nesse local. Caso as pastas anteriores não existam no seu sistema, elas serão criadas agora.*

Dê permissões para todos acessarem (para um compartilhamento aberto):
sudo chmod 777 /srv/samba/compartilhado
