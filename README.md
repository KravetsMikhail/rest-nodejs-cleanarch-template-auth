# rest-nodejs-cleanarch-template-auth

Сервис аутентификации на Keycloak

### Проверка работоспособности Keycloak

```bash
curl --location --request POST "http://localhost:8282/realms/rest-nodejs-cleanarch-template/protocol/openid-connect/token" --header "Content-Type: application/x-www-form-urlencoded" --data-urlencode "client_id=rest-nodejs-cleanarch-template-backend" --data-urlencode "client_secret=Vz7BrCxdX4gy0boeNZ3PhxHXWVQLD8Dg" --data-urlencode "grant_type=client_credentials"
```

#### Секрет для тестирования (не для прода!)

Для удобства локальной разработки и тестирования (В ПРОДЕ НИКОГДА ТАК НЕ ДЕЛАЙТЕ !!!), мы можем прописать secret нашего клиента в файл импорта, и тогда он не будет генерироваться заново каждый раз. Для этого в нашем JSON файле realm-export.json находим следующее поле:

```json
{
      "id": "6aec450f-de3f-4a03-a5e8-52ef510ef922",
      "clientId": "rest-nodejs-cleanarch-template-backend",
      "name": "backend",
      "description": "backend client",
      "rootUrl": "",
      "adminUrl": "",
      "baseUrl": "",
      "surrogateAuthRequired": false,
      "enabled": true,
      "alwaysDisplayInConsole": false,
      "clientAuthenticatorType": "client-secret",
      "secret": "**********", --> ЗДЕСЬ МЫ МОЖЕМ ПРОПИСАТЬ НАШ СЕКРЕТ
```
