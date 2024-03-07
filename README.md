# HomeLab
<h2 aligh="center">
 Este espaço é onde documento todo o processo de criação do meu HomeLab em um ambiente de homologação.
</h2>





## 📚 Sumário

- [🚀 Diagrama Inicial](#Diagrama)
- [🚀 Escolha do Firewall](#Firewall)
- [🚀 Switch](#Switch)
- [🚀 KVM Hypervisor](#Hypervisor)

## 🚀 Diagrama Inicial do Homelab Homologação<a id="Diagrama"></a>

![Homelab](https://github.com/sanderethx/homelab/blob/main/Homelab.svg)

## 🚀 Escolha do Firewall<a id="Firewall"></a>

A fim de testar algo novo, resolvi migrar do **PFSENSE** para o **SOPHOS HOME EDITION**, que podemos adquirir gratuitamente através do endereço abaixo, onde realizamos um pequeno cadastro para recebermos a chave de licença gratuíta.
Realize o cadastro e faça o download da opção que se enquadra no seu ambiente.
```linux
https://www.sophos.com/pt-br/free-tools/sophos-xg-firewall-home-edition
```

- 💎 No PNETLAB, para realizar a importação da imagem original do site da Sophos, baixe a versão **[KVM AQUI](https://www.sophos.com/en-us/support/downloads/firewall-installers)** e descompacte na pasta:
```linux
/opt/unetlab/addons/qemu/sophos-fw-VERSAO-DA-IMAGEM
```

Exemplo:
```linux
/opt/unetlab/addons/qemu/sophos-fw-20.0.0-GA
```

Renomear os discos dentro da pasta criada conforme abaixo:

Para o disco **PRIMARY-DISK.QCOW2**, utilizar o nome:
```linux
virtioa.qcow2
```
Para o disco **AUXILIARY-DISK.QCOW2**, utilizar o nome:
```linux
virtiob.qcow2
```
Após realizar os ajustes, corrigir as permissões dos diretórios e arquivos do PNETLAB utilizando o comando:
```linux
unl_wrapper -a fixpermissions
```
Criar um nó com o Sophos e testar no laboratório se tudo está funcionando corretamente.

## 🚀 Escolha do Switch<a id="Switch"></a>

Neste passo, é muito importante a escolha de um switch que seja gerenciado e que possa trabalhar com VLANS.
No meu caso, utilizo um Catalyst C2960S PoE da linha Cisco, que é um equipamento obsoleto e que pode ser adquirido por um valor bem em conta no Mercado Livre.
Dentro do [PNETLAB](https://www.youtube.com/watch?v=6XcsoaGveW4), meu ambiente de homologação,  irei utilizar a imagem L2-ADVENTENTERPRISEK9-M-15.2-20150703.bin para representar esse equipamento, que pode ser adquirida utilizando o [ISHARE2](https://www.youtube.com/watch?v=6XcsoaGveW4).

- **Aqui ainda definirei VLANs para segregar a rede conforme forem surgindo de acordo com a necessidade.**

## 🚀 KVM Hypervisor<a id="Hypervisor"></a>

Minha escolha de Hypervisor foi o [Proxmox](https://www.proxmox.com/en/downloads), devido ser um sistema muito leve e me dá várias possibilidades como: Contêiners LXC (Linux Contêiners), HA (High Availability) e Clusterização.
O vídeo para instalação Bare Metal pode ser [ACESSADO AQUI!](https://www.youtube.com/watch?v=QJTG2Tl2QtU)
