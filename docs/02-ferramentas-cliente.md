# Instalando as Ferramentas Cliente

Nesse lab você irá instalar os utilitários de linha de comando necessários para completar esse tutorial: [cfssl](https://github.com/cloudflare/cfssl), [cfssljson](https://github.com/cloudflare/cfssl), e [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl).

## Instale o CFSSL

Os utilitários de linha de comando `cfssl` e `cfssljson` serão utilizados para provisionar uma [Infraestrutura PKI (Infraestrutura de Chave Pública)](https://en.wikipedia.org/wiki/Public_key_infrastructure) e gerar certificados TLS.

Faça o download e instale o `cfssl` e `cfssljson` a partir do [repositório cfssl](https://pkg.cfssl.org):

### OS X

```
curl -o cfssl https://pkg.cfssl.org/R1.2/cfssl_darwin-amd64
curl -o cfssljson https://pkg.cfssl.org/R1.2/cfssljson_darwin-amd64
```

```
chmod +x cfssl cfssljson
```

```
sudo mv cfssl cfssljson /usr/local/bin/
```

### Linux

```
wget -q --show-progress --https-only --timestamping \
  https://pkg.cfssl.org/R1.2/cfssl_linux-amd64 \
  https://pkg.cfssl.org/R1.2/cfssljson_linux-amd64
```

```
chmod +x cfssl_linux-amd64 cfssljson_linux-amd64
```

```
sudo mv cfssl_linux-amd64 /usr/local/bin/cfssl
```

```
sudo mv cfssljson_linux-amd64 /usr/local/bin/cfssljson
```

### Verificação

Verifique que a versão 1.2.0 ou superior do `cfssl` está instalada:

```
cfssl version
```

> saída

```
Version: 1.2.0
Revision: dev
Runtime: go1.6
```

> O utilitário de linha de comando cfssljson não provê uma maneira de imprimir sua versão.

## Instale o kubectl

O utilitário de linha de comando `kubectl` é utilizado para interagir com o Servidor de API do Kubernetes. Faça o download e instale o `kubectl` a partir dos binários oficiais:

### OS X

```
curl -o kubectl https://storage.googleapis.com/kubernetes-release/release/v1.10.2/bin/darwin/amd64/kubectl
```

```
chmod +x kubectl
```

```
sudo mv kubectl /usr/local/bin/
```

### Linux

```
wget https://storage.googleapis.com/kubernetes-release/release/v1.10.2/bin/linux/amd64/kubectl
```

```
chmod +x kubectl
```

```
sudo mv kubectl /usr/local/bin/
```

### Verificação

Verifique que a versão 1.10.2 ou superior do  `kubectl` está instalada:

```
kubectl version --client
```

> saída

```
Client Version: version.Info{Major:"1", Minor:"10", GitVersion:"v1.10.2", GitCommit:"81753b10df112992bf51bbc2c2f85208aad78335", GitTreeState:"clean", BuildDate:"2018-04-27T09:22:21Z", GoVersion:"go1.9.3", Compiler:"gc", Platform:"linux/amd64"}
```

Próximo: [Provisionando Recursos Computacionais](03-recursos-computacionais.md)
