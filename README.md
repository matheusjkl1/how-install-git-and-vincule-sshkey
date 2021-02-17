# how-install-git-and-vincule-sshkey
Install git and vincule ssh key tutorial

sudo apt-get install git-all

git config --global user.name "Seu nome"
git config --global user.email seuemail@exemplo.br

git config --global core.editor "code --wait"

Esse comando define o editor do .gitconfig como o VS Code , que é o editor que você usará ao longo curso. 
Caso queira abrir o arquivo de configuração no VS Code basta executar em seu terminal o comando abaixo. 
Para isso certifique-se que você se encontra no diretório onde o arquivo .gitconfig está localizado.

code .gitconfig

git version

Digite git config --list
Seu terminal deve conter algo similar a isso:  
user.email=seuemail@gmail.com
user.name=seunome

ssh-keygen -t rsa -b 4096 -C "seuemail@gmail.com"

Durante o processo irá aparecer escrito no terminal Enter a file in which to save the key, 
quando isso acontecer pressione Enter para aceitar a localização padrão /home/you/.ssh/id_rsa .
Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]
Agora você deve digitar uma senha segura.
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]

Primeiro você deve iniciar o ssh-agent em background:

eval "$(ssh-agent -s)"

Agora você deve adicionar sua chave privada SSH ao ssh-agent . Para isso execute o comando abaixo no terminal:

ssh-add ~/.ssh/id_rsa

 Como o xclip não vem instalado por padrão na maioria das distribuições,
 precisaremos instalá-lo usando o comando a seguir:
sudo apt-get install xclip

 Agora utilize o comando abaixo para copiar o conteúdo da sua chave id_rsa.pub
 Para garantir que o conteúdo foi copiado dê Ctrl + V em um editor de texto
xclip -sel clip < ~/.ssh/id_rsa.pub

Caso o xclip não funcione, execute o comando abaixo e copie manualmente a saída do terminal.
cat ~/.ssh/id_rsa.pub

cat ~/.ssh/id_rsa.pub
