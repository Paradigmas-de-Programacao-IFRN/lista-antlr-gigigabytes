# Defina uma gramática que seja válida para o código abaixo:

````
h1 "Olá Mundo"
p "Preencha o formulário abaixo"
form {
  title = "Inserir Usuario"
  action = "/inserir"
  method = "post"
  input "nome"
  input "cpf"
}
````