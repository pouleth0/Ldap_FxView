# Ldap_FxView
"LDAP_FXview é um pacote que integra o framework JavaFX com LDAP utilizando as tecnologias Spring Boot >=2.2.0 e Java >=11.

Breve descrição:
Com esse pacote, é possível realizar operações de autenticação e gerenciamento de usuários em um servidor LDAP de forma simples e eficiente, utilizando uma interface gráfica moderna e intuitiva. O LDAP_FXview permite que você crie, modifique, exclua e busque usuários no servidor LDAP de maneira fácil e organizada. Experimente agora mesmo e simplifique a integração do seu sistema com servidores LDAP!"

*Classe [LdapServer]*

É responsável por estabelecer a conexão com o servidor LDAP e realizar a autenticação e gerenciamento de usuários.
Métodos:

[getLdapEnv()]: retorna um objeto de contexto LDAP para realizar operações no servidor.
[authenticate(String, String)]: realiza a autenticação de um usuário no servidor LDAP, recebendo como parâmetros o nome de usuário e a senha.
[createUser(User)]: cria um novo usuário no servidor LDAP, recebendo um objeto User como parâmetro.
[modifyUser(User)]: modifica um usuário existente no servidor LDAP, recebendo um objeto User como parâmetro.
[deleteUser(String)]: exclui um usuário do servidor LDAP, recebendo o nome de usuário como parâmetro.
[addUserToGroup(String, String)]: adiciona um usuário a um grupo existente no servidor LDAP, recebendo o nome de usuário e o nome do grupo como parâmetros.
[removeUserFromGroup(String, String)]: remove um usuário de um grupo existente no servidor LDAP, recebendo o nome de usuário e o nome do grupo como parâmetros.
[getAllUsers()]: retorna uma lista com todos os usuários cadastrados no servidor LDAP.

*Classe [User]*

Representa um usuário no servidor LDAP.
Atributos:

[objectClass]: lista de classes do objeto, contendo "user" e "organizationalPerson".
[cn]: nome completo do usuário.
[givenName]: primeiro nome do usuário.
[sn]: sobrenome do usuário.
[userPrincipalName]: nome de usuário seguido do nome de domínio (ex: usuario@dominio.com).
[sAMAccountName]: nome de usuário usado em sistemas Windows.
[unicodePwd]: senha do usuário em formato Unicode.

*Classe [LdapUtils]*

Contém métodos utilitários para manipulação de objetos LDAP.
Métodos:

[getSearchControls()]: retorna um objeto SearchControls para realizar buscas no servidor LDAP.
[getObjectAttributes(String, DirContext)]: retorna um objeto Attributes contendo os atributos de um objeto LDAP, recebendo o nome do objeto e o contexto LDAP como parâmetros.
[getObjectAttribute(String, String, DirContext)]: retorna o valor de um atributo de um objeto LDAP, recebendo o nome do objeto, o nome do atributo e o contexto LDAP como parâmetros.
[createAttribute(String, Object)]: cria um objeto Attribute com um nome e um valor especificados.
[createModification(int, Attribute)]: cria um objeto ModificationItem com um tipo de modificação (adicionar, remover ou substituir) e um objeto Attribute.

*Classe [LdapConfig]*

Contém as configurações de conexão com o servidor LDAP.
Atributos:

[INITIAL_CTX]: nome da classe do objeto de contexto LDAP.
[LOGGER]: objeto Logger para registro de logs.
[URL]: endereço do servidor LDAP.
[DN]: nome do diretório base do servidor LDAP.
[SECURITY_PRINCIPAL]: nome do atributo que contém o nome de usuário no servidor LDAP.
Métodos:

[getContextSource()]: retorna um objeto LdapContextSource configurado com as informações de conexão com o servidor LDAP.
[ldapTemplate()]: retorna um objeto LdapTemplate para realizar operações no servidor LDAP.
