## Preparação
Dentro da pasta `task` você irá encontrar um playbook do Ansible para provisionar um novo servidor
Esta tarefa foi preparada para ser executada usando o VirtualBox ou o Parallels

### Base server image
- Debian 8

### Serviços que serão lançados
- nginx
- PHP7.0
- MySQL5.6

### Pré-requisitos
- Vagrant
- Ansible
- VirtualBox

### Como iniciar
1. cd devops-assignment/tasks
2. `vagrant up --provision`

Para executar o provisioner novament,e execute `vagrant provision`
Acesse a instancia via http(s) em `http://myplay.local`

## Tarefas
### Parte 1: Ansible e conceitos de Linux
01. Existe um ou mais erros no playbook do ansible. É necessário corrigir os erros para que o playbook rode por completo
02. Crie uma role que bloqueie as portas TCP da máquina para serem permitidas apenas as portas 80, 443 e 22 de qualquer origem
03. Configure o nginx para que a página http faça redirect para a página https
04. O Nginx não pode retornar nos headers a versão do Nginx. Configure o servidor para que este campo não seja preenchido no response header
05. Crie uma nova role que cria usuários no servidor. Esta role deverá criar os usuários `dev1` e `dev2`, sendo que os usuários não deverão ter senha, mas sim autenticação por chave publica. As chaves publicas dos usuários pode ser encontrada no diretório `pubkeys`.

### Parte 2: Terraform
06. Crie um diretorio chamado `terraform`
07. Migre infraestrutura criada no Ansible para ser criado via Terraform

### Parte 3: Kubernetes
08. Crie um diretório chamado `kubernetes`
09. Migre o serviço que roda na máquina Virtual para que rode em Kubernetes com Helm, deve conter deployment, hpa, service. Fique a vontade para adicionar outros recursos.
10. Indique qual o processo para iniciar o ambiente Kubernetes criado no item anterior

### Parte 4: Questões
11. O que está faltando para este sistema poder ser considerado como de produção? Quais pontos deveriam ser revistos?

12. Suponha que a aplicação web já está rodando a um tempo e começou a receber um grande volume de tráfego. Que técnicas você aplicaria para garantir a performance do site?

13. O que seria necessário fazer caso quisesse configurar mais de um vhost neste servidor nginx?

14. Explique brevemente: Como você faria para promover o código do ambiente de DEV até produção? Quantos ambientes você acha necessário e qual processo faria para a promoção entre os ambientes?

15. O que é Auto Scaling? Como implementar? É possível ter Auto Scaling no Kubernetes?

16. O que é CI? O que é CD? Quais ferramentas você conhece?

17. Descreva o que seria o ideal em sua opnião referente a monitoramento do site que acabamos de subir. O que devemos monitorar e quais ferramentas poderiam ser utilizadas?

18. Com quais Nuvens publicas você já trabalhou?

19. Com quais Saas Kubernetes você já trabalhou?
