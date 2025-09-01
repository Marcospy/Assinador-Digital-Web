# Assinador Digital Web

## 📖 Sobre o Projeto

Aplicação web de página única (Single Page Application) que implementa um sistema completo de assinatura e verificação de assinaturas digitais.

Toda a lógica de criptografia (geração de chaves, assinatura e verificação) é executada no lado do cliente (navegador) utilizando a **Web Crypto API**. O `localStorage` do navegador é utilizado para simular o banco de dados.

## ✨ Funcionalidades

* **Cadastro de Usuário:** Criação de um novo usuário com a geração automática de um par de chaves (pública e privada) **RSA-PSS**.
* **Assinatura de Mensagens:** Usuários autenticados podem digitar um texto e assiná-lo digitalmente com sua chave privada.
* **Verificação de Assinatura:** Uma rota pública permite que qualquer pessoa verifique a validade de uma assinatura usando seu ID.
* **Log de Verificações:** Cada tentativa de verificação (bem-sucedida ou não) é registrada.
* **Ferramenta de Teste:** Uma aba dedicada permite invalidar e restaurar assinaturas intencionalmente para demonstrar os casos de teste negativo e positivo.

## 🛠️ Tecnologias Utilizadas

* **HTML5**
* **Tailwind CSS** para estilização.
* **JavaScript (ES6+)** para toda a lógica da aplicação.
* **Web Crypto API** para todas as operações criptográficas.

## 🚀 Como Executar

1.  Baixe o arquivo `assinador-digital.html`.
2.  Abra o arquivo em qualquer navegador web moderno (Google Chrome, Firefox, Microsoft Edge, etc.).
3.  A aplicação é totalmente funcional e autocontida, não necessitando de um servidor.

## ✅ Casos de Teste

Para realizar os testes de validação positiva e negativa:

1.  **Cadastro e Assinatura:**
    * Vá para a aba **Início**, cadastre um usuário e faça o login.
    * Vá para a aba **Assinar**, digite uma mensagem e clique em "Gerar Assinatura Digital".
    * Copie o **ID da Assinatura** gerado.

2.  **Teste de Validação Positiva:**
    * Vá para a aba **Verificar**.
    * Cole o ID da assinatura e clique em "Verificar Autenticidade".
    * O resultado esperado é: **ASSINATURA VÁLIDA**.

3.  **Teste de Validação Negativa (Assinatura Alterada):**
    * Vá para a nova aba **Invalidar**.
    * Cole o mesmo ID da assinatura e clique em "Buscar Assinatura".
    * Clique no botão vermelho **"Invalidar Assinatura"**. Isso irá corromper a assinatura salva.
    * Volte para a aba **Verificar**, cole o ID novamente e verifique.
    * O resultado esperado é: **ASSINATURA INVÁLIDA**.

4.  **Restauração (Opcional):**
    * Volte para a aba **Invalidar** e clique em **"Restaurar Original"** para testar novamente a validação positiva.
