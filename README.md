# Auth Service - Servicio de Autenticación Centralizada

## Descripción
Servicio de autenticación centralizada que utiliza gRPC y LDAP para proporcionar un sistema de inicio de sesión único (SSO) para múltiples plataformas. El servicio valida las credenciales contra un servidor LDAP/Active Directory y devuelve la información del usuario en formato XML.

## Características
- Autenticación centralizada mediante LDAP/Active Directory
- Comunicación segura usando gRPC con TLS
- Gestión de sesiones mediante tokens JWT
- Cliente web para pruebas de integración
- Soporte para múltiples conexiones simultáneas
- Respuestas en formato XML con información detallada del usuario

## Estructura del Proyecto
```
auth-service/
├── proto/               # Definiciones de protobuf
├── server/             # Servidor gRPC
│   ├── auth/           # Lógica de autenticación
│   └── config/         # Configuración del servidor
├── web-client/         # Cliente web de prueba
├── certs/              # Certificados TLS
└── README.md
```

## Requisitos Previos
- Go 1.20 o superior
- Protocol Buffers compiler (protoc)
- Node.js y npm (para el cliente web)
- Servidor LDAP/Active Directory
- Git

## Instalación

1. Clonar el repositorio:
```bash
git clone https://github.com/manzur1990/auth-service.git
cd auth-service
```

2. Instalar dependencias:
```bash
go mod tidy
```

3. Compilar los archivos proto:
```bash
./compile-proto.ps1
```

## Configuración

1. Configurar las credenciales LDAP en `server/config/config.go`
2. Generar certificados TLS para el servidor gRPC
3. Configurar los parámetros del servidor en el archivo de configuración

## Uso

### Iniciar el Servidor
```bash
go run server/main.go
```

### Ejecutar el Cliente Web
1. Navegar al directorio web-client
2. Abrir index.html en un navegador web
3. Ingresar credenciales de usuario

## Seguridad
- Comunicación cifrada mediante TLS
- Tokens JWT para gestión de sesiones
- Validación de credenciales contra LDAP/Active Directory
- Manejo seguro de contraseñas

## Respuesta XML
Ejemplo de respuesta del servicio:
```xml
<user>
    <displayName>Jorge Manzur</displayName>
    <department>IT</department>
    <organizationalUnit>Unidad de Informática</organizationalUnit>
    <groups>
        <group>Administrators</group>
        <group>IT Staff</group>
    </groups>
</user>
```

## Contribuir
1. Fork del repositorio
2. Crear una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit de tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abrir un Pull Request

## Estado del Proyecto
En desarrollo activo - Versión 0.1.0

## Autor
Jorge Manzur - [GitHub](https://github.com/manzur1990)

## Licencia
Este proyecto está licenciado bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.