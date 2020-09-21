# AvalancheGo

## instalación

Avalanche es un protocolo increíblemente ligero, por lo que los requisitos mínimos del equipo son bastante reducidos.

- Hardware: CPU de 2 GHz o más rápido, 4 GB de RAM, disco duro de 2 GB.
- OS: Ubuntu >= 18.04 or Mac OS X >= Catalina.
- Software: [Go](https://golang.org/doc/install) version >= 1.13.X y establecer [`$GOPATH`](https://github.com/golang/go/wiki/SettingGOPATH).
- Network: Conexión de red IPv4 or IPv6, con un puerto público abierto.

### Instalación nativa

Clonar el repositorio AvalancheGo:


```sh
go get -v -d github.com/ava-labs/avalanchego/...
cd $GOPATH/src/github.com/ava-labs/avalanchego
```

#### Construyendo el ejecutable de Avalanche

EL binario de Avalanche, llamado `avalanchego`, se puede encontrar en el directorio `build`.

### Instalación con Docker

- Asegúrate de tener instalado el docker en tu máquina (para que comandos como `docker run`, etc. estén disponibles).

- Construye la imagen de la última rama de avalanchego en `scripts/build_image.sh` 

- Comprueba la imagen construida con `docker image ls`, deberías ver alguna imagen etiquetada como `avalanchego-xxxxxxxx`, donde `xxxxxxxx` es el id del commit de la identificación de la procedencia de Avalanche de la cual fue construida.

- Prueba Avalanche con `docker run -ti -p 9650:9650 -p 9651:9651 avalanchego-xxxxxxxx /avalanchego/build/avalanchego --network-id=local --staking-enabled=false --snow-sample-size=1 --snow-quorum-size=1`. (Para un despliegue en producción tal vez quiera incluir la imagen del docker con las credenciales necesarias para el staking y el TLS.)

## Ejecutando Avalanche

### Conectándose a Everest

Para conectarse a la testnet Everest, ejecute:

```sh
./build/avalanchego
```

Deberías ver un bonito diseño ASCII y mensajes de registro.

Puedes usar `Ctrl + C` para parar el nodo.

### Creando una Testnet Local

Para crear un nodo de testnet simple ejecute:

```sh
./build/avalanchego --network-id=local --staking-enabled=false --snow-sample-size=1 --snow-quorum-size=1
```

Esto lanzará una red Avalanche con un nodo.
