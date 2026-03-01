# unipds-exemplo-00

Exemplo 00 - Engenharia de IA

Este repositório contém o código usado na aula do Curso UNIPDS, Módulo 02.
A lição focou em instalar e usar o pacote `@tensorflow/tfjs-node` e lidar com
problemas comuns de compatibilidade no Windows.

## Tópicos abordados

1. **Instalação de dependências**
   ```bash
   npm install @tensorflow/tfjs-node@4.22
   ```
2. **Erro `ERR_DLOPEN_FAILED`** ao carregar o módulo nativo:
   - Acontece quando o Node tenta abrir `tfjs_binding.node` e falta uma
     dependência de tempo de execução (por exemplo, redistribuível VC++).
   - Mensagem típica:
     ```text
     Error: The specified module could not be found.
     …\tfjs_binding.node
     code: 'ERR_DLOPEN_FAILED'
     ```
3. **Soluções**
   - Use uma versão suportada do Node (16, 18 ou 20). Exemplo com nvm:
     ```powershell
     nvm install 20
     nvm use 20
     npm ci
     ```
   - Instale o Microsoft Visual C++ 2015–2022 Redistributable (x64).
   - Reinstale ou reconstrua o pacote:
     ```bash
     npm rebuild @tensorflow/tfjs-node
     ```
4. **Teste rápido**:
   ```bash
   node -e "require('@tensorflow/tfjs-node'); console.log('loaded');"
   ```

## Estrutura do projeto

- `index.js` – script principal (ainda vazio na aula de exemplo).
- `package.json` – especifica `@tensorflow/tfjs-node` como dependência.

## Observações futuras

- Verificar atualizações do `tfjs-node` para suporte a Node >=22.
- Revisitar instalação de versões do Node para projetos de IA.

---

Mantenha este README como referência para a aula e para troubleshooting
bibliotecas nativas em Node.js no Windows.
