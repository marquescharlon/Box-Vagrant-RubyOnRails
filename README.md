# Box Vagrant com Ruby On Rails configurado
Ambiente de desenvolvimento já configurado para quem gosta de se aventurar com Ruby On Rails. <br>
Para conferir a Box acesse https://app.vagrantup.com/marquescharlon/boxes/rails

Vagrant é um software de código aberto que possibilita criar ambientes de desenvolvimento virtuais como:
- **VirtualBox**
- VMWare
- KVM
- Hyper-V
- Docker containers
- AWS

> A box desse repositório utiliza o VirtualBox
<br>

Dessa forma se sua máquina der algum problema você não precisará configurar todo o ambiente, basta acessar o repositório do Vagrant Cloud e baixar a box desejada. Para ajudá-los compartilho o ambiente que criei, nele como já mencionado, possui softwares já instalados e configurados, são eles:

- [Ubuntu](https://ubuntu.com/download/desktop) 18.04.4 LTS
- [Git](https://gitforwindows.org/) 2.17.1
- [Yarn](https://yarnpkg.com/) 1.22.4
- [NodeJS](https://nodejs.org/en/) v8.10.0
- Ruby 2.5.8p224
- [Rails](https://rubyonrails.org/) 5.2.4.3
- [RVM](https://rvm.io/) 1.29.10
- MySQL 14.14 Distrib 5.7.30
- PostgreSQL 10.12

# Por onde começo?

## 1. Baixar e instalar o [Vagrant](https://developer.hashicorp.com/vagrant/downloads)
## 2. Criar e Configurar o arquivo Vagrantfile

Ao executá-lo irá baixar e iniciar uma VM (Máquina Virtual) do Vagrant Cloud que são conhecidas como Boxes.
Agora, vamos configurar o Vagrantfile, para isso, basta criar um arquivo chamado Vagrantfile na raiz do seu projeto com o conteúdo abaixo:

```
Vagrant.configure("2") do |config|
  config.vm.box = "marquescharlon/rails"
  config.vm.box_version = "1.0.0"
end
```

Você pode estar se perguntado: Que arquivo é esse? Para que serve? Vou te explicar: É através dele que você especifica qual a box será instalada na VM. 

Agora, se tiver preguiça de configurar isso manualmente você pode acessar a pasta do seu projeto via prompt e executar o seguinte comando: 

```
vagrant init marquescharlon/rails
```

Ele vai criar o arquivo Vagrantfile já configurado, a vantagem de realizar dessa forma é que ele irá trazer demais comando comentados e para quem está ainda se familiarizando pode ser muito útil. Então, fica a seu crtério.

## 3. Configurar client SSH

O Windows não possui um cliente SSH nativo, por isso, a necessidade de você instalar programas alternativos como o [Putty](https://www.putty.org/). Porém, temos duas alternativas. Configurar o client SSH utilizando o Putty ou o próprio Git. 

Ao instalar o [GiForWindows](https://gitforwindows.org/) você já configura o client SSH, permitindo que os comandos no Linux possa também funcionar no prompt de comando do Windows. Para isso, na hora que for instalar só deixar marcado a opção: *Use Git and optional Unix tools from the Windows Command Prompt* conforme a figura abaixo:

![image](https://user-images.githubusercontent.com/22162514/201496794-1fd5905e-84e3-434d-bb87-4d39dcd0fa81.png)

## 4. Acessar o ambiente

Basta abrir o prompt de comando "cmd" e executar o comando:

```
vagrant ssh
```

E para acessar as pastas de sua máquina virtual basta apenas navegar através do prompt usando cd /vagrant.

## 5. Atualizar o ambiente

Após ter configurado e acessado o ambiente basta apenas atualizar os programas e o sistema operacional, para isso, só executar os comandos:

```
$ sudo apt-get update  
$ sudo apt-get upgrade 
```

> Lembre que essa máquina virtual (box) possui 924MB, dependendo da velocidade da sua internet é normal demorar um pouco sua configuração. 

Você pode conferir também o repositório [Check-In_RubyOnRails](https://github.com/marquescharlon/Check-In_RubyOnRails).<br>
Um sistema simples desenvolvido em Ruby On Rails, com foco na aplicação da metodologia ágil eXtreme Programming (XP).
