# How install Git and vincule SSH KEY

<b>sudo apt-get install git-all</b>

<b><i>git config --global user.name "Seu nome"</b>

<b>git config --global user.email seuemail@exemplo.br</i></b>

<b><i>git config --global core.editor "code --wait"</i></b>

Esse comando define o editor do .gitconfig como o VS Code , que é o editor que você usará ao longo curso. 
Caso queira abrir o arquivo de configuração no VS Code basta executar em seu terminal o comando abaixo. 
Para isso certifique-se que você se encontra no diretório onde o arquivo .gitconfig está localizado.

<b><i>code .gitconfig</i></b>

<b><i>git version</i></b>

Digite 
<b><i>git config --list</i></b>
 
<b>Seu terminal deve conter algo similar a isso:  
user.email=seuemail@gmail.com
user.name=seunome</b>

<b><i>ssh-keygen -t rsa -b 4096 -C "seuemail@gmail.com"</i></b>

Durante o processo irá aparecer escrito no terminal Enter a file in which to save the key, 
quando isso acontecer pressione Enter para aceitar a localização padrão /home/you/.ssh/id_rsa .
Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]
Agora você deve digitar uma senha segura.
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]

Primeiro você deve iniciar o ssh-agent em background:

<b><i>eval "$(ssh-agent -s)"</i></b>

Agora você deve adicionar sua chave privada SSH ao ssh-agent . Para isso execute o comando abaixo no terminal:

<b><i>ssh-add ~/.ssh/id_rsa</i></b>

Como o xclip não vem instalado por padrão na maioria das distribuições,
precisaremos instalá-lo usando o comando a seguir:

<b><i>sudo apt-get install xclip</i></b>

 Agora utilize o comando abaixo para copiar o conteúdo da sua chave id_rsa.pub
 Para garantir que o conteúdo foi copiado dê Ctrl + V em um editor de texto
 
<b><i>xclip -sel clip < ~/.ssh/id_rsa.pub</i></b>

Caso o xclip não funcione, execute o comando abaixo e copie manualmente a saída do terminal.

 <b><i>cat ~/.ssh/id_rsa.pub</i></b>
