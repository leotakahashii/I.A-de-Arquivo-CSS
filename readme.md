# ⚡ CSS Gerador com IA

Esse é um projeto que retomei recentemente: um gerador de código HTML e CSS que usa inteligência artificial pra transformar uma descrição em texto (tipo "bolinha azul pingando") em código funcional, com preview em tempo real.

Foi meu primeiro contato consumindo uma API de IA generativa, e voltei nele há pouco tempo pra corrigir alguns problemas que eu não tinha percebido quando construí originalmente — principalmente relacionados à segurança e ao tratamento de erros.

![Status](./assets/Layout%20gerador%20css.png)

## ✨ O que o projeto faz

A ideia é simples na superfície: o usuário escreve o que imagina num campo de texto, clica em "Gerar Código", e a IA retorna o HTML e CSS correspondente, que é exibido tanto como código quanto renderizado ao vivo num preview.

Por trás disso, envio a descrição do usuário pra API da Groq, usando o modelo Llama 3.3, com um prompt de sistema que instrui a IA a responder só com código puro, sem explicações nem markdown. O resultado vem em dois lugares: um bloco de texto mostrando o código gerado, e um `iframe` renderizando esse mesmo código ao vivo, como preview.

Ao revisitar o projeto, adicionei tratamento de erro pra quando a API falha ou demora, um indicador de carregamento enquanto a resposta não chega, e uma validação pra impedir que o botão dispare uma chamada vazia, sem nenhum texto digitado.

## 🛠️ Tecnologias que usei

- HTML5
- CSS3 (Flexbox, hover states, animações)
- JavaScript (ES6+, `async/await`, `fetch`)
- [Groq API](https://groq.com/) com modelo Llama 3.3

## 📁 Estrutura do projeto

```
I.A-de-Arquivo-CSS/
├── index.html
├── styles.css
├── scripts.js
├── config.example.js
└── README.md
```

## 🚀 Como rodar na sua máquina

1. Clone o repositório:
   ```bash
   git clone https://github.com/leotakahashii/I.A-de-Arquivo-CSS
   cd I.A-de-Arquivo-CSS
   ```

2. Crie uma conta gratuita em [console.groq.com](https://console.groq.com/) e gere sua própria API key.

3. Renomeie o arquivo `config.example.js` para `config.js` e insira sua chave:
   ```javascript
   let apiKey = 'sua_key_aqui';
   ```

4. Abra o `index.html` no navegador (recomendo a extensão *Live Server* do VS Code).

## 🎯 O que eu aprendi revisando esse projeto

Voltar num projeto antigo acabou sendo tão valioso quanto construir um novo. Reencontrei minha própria API key exposta direto no código, o que me fez entender na prática por que separar credenciais do controle de versão é tão importante — não é só teoria, é algo que evita um problema real.

Também percebi que tinha construído o projeto sem nenhum tratamento de erro, então adicionar isso me fez pensar em cenários que não passavam pela minha cabeça antes: e se a API estiver fora do ar? E se o usuário clicar sem escrever nada? Esses casos de borda fazem parte de qualquer aplicação de verdade, e passei a olhar pra eles com mais atenção.

Foi um exercício de revisitar meu próprio código com um olhar mais crítico, aplicando conceitos que fui aprendendo em projetos mais recentes de volta num projeto mais antigo.

## 👨‍💻 Sobre mim

Sou o Leo, desenvolvedor em transição de carreira da gastronomia pra tecnologia. Esse projeto faz parte do meu portfólio enquanto sigo estudando Ciência da Computação e Full Stack.

[LinkedIn](https://www.linkedin.com/in/leonardotakahashii/) · [GitHub](https://github.com/leotakahashii)

---

Feito com 💛 e muito café.