Playbook de healthcheck do OCP (Openshift Container Platform)

## Instalar os pacotes de depedências do [Python](https://www.python.org/).

Os pacotes são gerenciados via [Poetry](https://python-poetry.org/). O mesmo pode ser instalado via [pip](https://pip.pypa.io/en/stable/).

```
pip install poetry
```

Outras formas de instalação também pode ser visualizadas na [documentação](https://python-poetry.org/docs/#installation).

Instalando os pacotes via poetry

```
poetry install
```

## Fazer a instação das collections:

Realizando a instalação das collections do [Ansible](https://docs.ansible.com/ansible/latest/index.html)
```
ansible-galaxy collection install -r requirements.yml -p ./collections
```

Instalação das depedências do modulo do VMware

```
pip install -r collections/ansible_collections/community/vmware/requirements.txt
```
## Exportando as credenciais do vsphere

Copie o arquivo de exemplo, e altere para as suas credênciais.

```
cp .envrc.exemple .envrc
vim .envrc
source .envrc
```

## Requisitos do playbook

O arquivo de config padrão é 'config' no diretório local

```
ansible-playbook check.yml
```

Por padrão ele realiza a checagem em todos os contextos, mas pode passar o parâmetro `contextos` com as lista separada por virgula  
```
ansible-playbook check.yml -e contextos=ctx1,ctx2
```