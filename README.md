# 🖥️ Projeto Semana 07


## 📜 Descrição
Projeto com o objetivo de melhorar a performance das páginas.

## 🖱️ Para rodar o projeto localmente

      npm install  
      npm run dev

## ✍️ Processo

> **ListKeys** : Notei que todas as vezes que era adicionado um input na tela, era renderizado todos os inputs novamente, para melhorar o desempenho, usei o memo no componente input. Quando se envolve um componente de função com memo, o React "memoriza" o resultado da renderização desse componente. Isso significa que, se as props do componente não mudarem, o React reutilizará o resultado memorizado em vez de re-renderizar o componente.

> **ContadorComError** : Nesta página notei que os erros estavam sendo renderizados a cada vez que eram chamados, entao usei o useCallback para otimizar o desempenho do componente e evitar que os callbacks sejam recriados em cada renderização. Também usei um único conjunto de erros, achei que poderia aparecer somente uma vez  cada erro, economizando o consumo de memória e renderizações desnecessárias.

> **ColorResponsive** : Foi usado na função alteraCor o useCallback para evitar a recriação da função a cada renderização do componente. Além disso eu retirei o console.log pois também estava causando re-renderizações desnecessárias.

> **CampoDeBusca** : Nessa página percebi que o que causava um erro de performance era que toda vez que eu digitava um caractere era feito a chamada da funcão. Para resolver isso criei um hook chamado useDebounce para que a solicitação não fosse feita a cada caractere digitado, ela será enviada somente após um curto período de inatividade.

> **Market** : Essa página achei bastante coisa que pudesse ser melhorada, então comecei pelo componente **relógio**, todas as vezes que mudava os segundos, a página inteira renderizava, entao criei um useState para que o estado do relógio ficasse dentro do próprio componente de relógio e usei o useMemo para que fosse memorizado o formato da data, evitando que seja recalculado a cada renderização, a menos que a data mude. No componente **ListaProdutos** usei na const registraCompras o useMemo com o propósito de evitar renderizações desnecessárias, como a função não precisaria ser recriada, achei que poderia servir. No componente **CardProdutos** o memo é aplicado ao componente para garantir que ele seja renderizado novamente apenas se as props produto ou onClick forem alteradas. Com todas essas alterações a performance da página Market foi melhorada.


## 👩‍💻 Dev
<table align="center">
  <tr>
    <td align="center">
      <div>
        <img src="https://avatars.githubusercontent.com/u/114251625?v=4" width="120px;" alt="Foto de Karine no GitHub"/><br>
          <b> Karine Pereira </b><br>
            <a href="https://www.linkedin.com/in/devkarine/" alt="Linkedin"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/ height="20"></a>
            <a href="https://github.com/devkarine" alt="Linkedin"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" height="20"></a>
      </div>
    </td>

  </tr>
</table>