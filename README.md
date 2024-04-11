# APIM-AzureADB2C-ValidateJWT
Exemplo com configuracões para validar o Access Token de uma aplicação utilizando a policy &lt;Calidate-jwt> do Azure API Management e uma App Registration do Azure AD B2C. Inclui script .http para testes com a extensão REST Client do VS Code.

Inclui script .http para testes com a extensão REST Client do VS Code.

Exemplo de uso da policy **&lt;validate-jwt>** (**inbound**):

```xml
    <inbound>
        <base />
        <validate-jwt header-name="Authorization" failed-validation-httpcode="401" failed-validation-error-message="Unauthorized. Access token faltando ou invalido.">
            <openid-config url="url_open_id_config_userflow" />
            <audiences>
                <audience>id_appregistration</audience>
            </audiences>
        </validate-jwt>
    </inbound>
```

Para saber mais sobre a policy **&lt;validate-jwt>** acesse:

**https://learn.microsoft.com/en-us/azure/api-management/validate-jwt-policy**