# Serviço de criação de VMs no oVirt
#

#
PASSOS INICIAIS

Edite o arquivo defaults/login.yml e coloque seus dados de acesso ao seu OVirt.

Edite o arquivo defaults/main.yml e coloque suas variáveis.





### :computer: PRÉ-REQUISITO FEDORA

```bash
sudo dnf install http://resources.ovirt.org/pub/yum-repo/ovirt-release44.rpm
dnf install python-ovirt-engine-sdk4
```



### Comando para execução direta

```bash
ansible-playbook -i hosts provisioning.yml --extra-vars "RUN=dev"
```

#### Variáveis

SNAP_NAME: zerado = Nome do SNAPSHOT que será criado ou restaurado no gerenciamento da VM.
RESTORE_SNAP: false
DELETE_VM: Somente deletar VM caso ela já exista

CREATE_VM: Somente criar VM caso ela não exista

RUN: Vai filtrar o arquivo ovirt_vms e identificar as vm's que possuem a mesma tag para interagir.

Utilize a tag n ovirt_vms para chamar nesse playbook para criação, esse playbook irá interagir somente com as vm's que tem a mesma tag chamada pela variável RUN.
