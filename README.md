# Plantilla de AWS - Documentación Técnica

## Descripción
Esta plantilla de AWS se utiliza para crear una pila de recursos para un entorno de ejecución de un servidor Ecommerce. A continuación se detallan los recursos y parámetros utilizados en la plantilla.

## Parámetros
- `AmiIdParameter` (Valor por defecto: '/aws/service/canonical/ubuntu/server/jammy/stable/current/amd64/hvm/ebs-gp2/ami-id'): Parámetro que especifica la AMI de Ubuntu Linux a utilizar.
- `InstanceTypeParameter` (Valor por defecto: 't3.micro'): Parámetro que permite seleccionar el tipo de instancia que se desea crear.
- `KeyPairParameter` (Valor por defecto: 'Eshop'): Parámetro que especifica el nombre del par de claves a utilizar.

## Recursos
- `ViandaMarketVPC`: VPC (Virtual Private Cloud) para el entorno de ejecución.
- `InternetGateway`: Puerta de enlace de Internet para la VPC.
- `IGWattachVPC`: Asociación de la puerta de enlace de Internet con la VPC.
- `RouteTable`: Tabla de enrutamiento para la VPC.
- `PublicRouteTable`: Ruta pública en la tabla de enrutamiento.
- `PublicSubnet1` y `PublicSubnet2`: Subredes públicas.
- `PSattachRT1` y `PSattachRT2`: Asociaciones de las subredes públicas con la tabla de enrutamiento.
- `SecurityGroup`: Grupo de seguridad para permitir el tráfico SSH.
- `BackendInstance`: Instancia del servidor de backend para el servidor Ecommerce.
- `MyEIP` y `MyEIPAssociation`: Asignación de una dirección IP elástica (EIP) a la instancia del backend.
- `myDBSecurityGroup`: Grupo de seguridad para la instancia de base de datos RDS.
- `myDBSubnetGroup`: Grupo de subredes para la instancia de base de datos RDS.
- `myDBInstance`: Instancia de base de datos RDS.

## Salidas
- `PublicIp`: Dirección IP pública de la instancia del servidor de backend.
- `RDSInstanceEndpoint`: Endpoint de la instancia de base de datos RDS.

## Uso
Para utilizar esta plantilla, puedes seguir los siguientes pasos:

1. Abre la consola de administración de AWS y navega hasta el servicio CloudFormation.
2. Haz clic en "Create stack" (Crear pila) y selecciona "With new resources (standard)" (Con nuevos recursos estándar).
3. Selecciona "Upload a template file" (Cargar un archivo de plantilla) y carga el archivo de plantilla.
4. Rellena los parámetros necesarios.
5. Haz clic en "Next" (Siguiente) y sigue las instrucciones para completar la creación de la pila.

Una vez que la pila se haya creado correctamente, podrás encontrar la dirección IP pública de la instancia del servidor de backend en la salida "PublicIp". Además, el endpoint de la instancia de base de datos RDS estará disponible en la salida "RDSInstanceEndpoint".

