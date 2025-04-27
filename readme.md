# Adicionar "Prompt de Comando (Admin)" no Menu de Contexto (Windows 10)

Este repositório contém um arquivo `.reg` que adiciona a opção **"Prompt de Comando (Admin)"** ao clicar com o botão direito em áreas vazias do **Explorador de Arquivos** no **Windows 10**.

### O que o script faz?

- Adiciona a opção **Prompt de Comando (Admin)** no menu de contexto.
- Abre o **CMD** já como **Administrador** (elevado).
- Já inicia o CMD na **pasta onde você clicou**.
- Adiciona um **ícone de escudo azul** para indicar permissão elevada.

### Como usar?

1. Baixe o arquivo [`prompt_admin.reg`](./prompt_admin.reg).

2. Dê **dois cliques** no arquivo.

3. Confirme a mensagem do Windows perguntando se deseja adicionar as entradas no Registro.

4. Pronto! Agora basta clicar com o botão direito em qualquer área vazia de uma pasta no Explorador para ver a nova opção.

### Exemplo de funcionamento:

- Clique com o botão direito ➔ **Prompt de Comando (Admin)**
- O terminal será aberto já na pasta selecionada, com privilégios administrativos.

### Código do arquivo `.reg`

```reg
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\Prompt de Comando (Admin)]
@="Prompt de Comando (Admin)"
"Icon"="%SystemRoot%\\System32\\imageres.dll,-78"

[HKEY_CLASSES_ROOT\Directory\Background\shell\Prompt de Comando (Admin)\command]
@="powershell.exe -Command \"Start-Process cmd.exe -ArgumentList '/s,/k,pushd,%V' -Verb RunAs\""
```

---

### Observação

- Este script é compatível com **Windows 10**.
- Pode funcionar no **Windows 11**, mas o Windows 11 já tem a opção de Terminal nativamente.

---

### Licença

Este projeto está sob a licença [MIT](LICENSE).
Sinta-se livre para usar, modificar e compartilhar!

---

🚀 Criado com ❤️ para facilitar a vida de quem usa o Windows!
```
