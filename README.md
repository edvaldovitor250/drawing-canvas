<body>
  <header>
    <h1>Desenhando usando Canvas</h1>
  </header>
  <main>
    <h2>Índice</h2>
    <ol>
      <li><a href="#visão-geral">Visão Geral ℹ️</a></li>
      <li><a href="#tela-do-dashboard">Tela Inicial 🎮</a></li>
      <li><a href="#business-rules">Funcionalidades ⚙️</a></li>
      <li><a href="#funcionamento-dos-filtros">Instruções de Uso 🛠️</a></li>
      <li><a href="#instruções-de-inicialização-do-projeto">Instruções de Inicialização do Projeto 🚀</a></li>
      <li><a href="#tecnologias-utilizadas">Tecnologias Utilizadas 💻</a></li>
    </ol>
    <section id="visão-geral">
      <h2>Visão Geral</h2>
      <p>Esta aplicação permite desenhar no canvas utilizando JavaScript, aproveitando as capacidades gráficas do navegador.</p>
    </section>
    <section id="tela-do-dashboard">
      <h2>Tela Inicial</h2>
      <img src="https://github.com/edvaldovitor250/drawing-canvas/assets/116117189/1e457cf5-4d85-44ec-8497-4223baefea1c" alt="Tela Inicial">
    </section>
    <section id="business-rules">
      <h2>Funcionalidades</h2>
      <ul>
        <li>Permite ao usuário desenhar livremente no canvas.</li>
        <li>Realiza verificação automática de cores.</li>
        <li>Oferece a funcionalidade de reinicialização do desenho através de um botão dedicado. ♻️</li>
      </ul>
    </section>
    <section id="logic-js">
      <h2>Lógica no JavaScript</h2>
      <p>Essa foi a lógica implementada para esse projeto</p>
        
     let currentColor = 'black';

     let canDraw = false;
      let mouseX = 0;
    let mouseY = 0;

    let screen = document.querySelector('#tela');
    let ctx = screen.getContext('2d');

    document.querySelectorAll('.colorArea .color').forEach(item => {
    item.addEventListener('click', colorClickEvent);
    });

    screen.addEventListener('mousedown', mouseDownEvent);
    screen.addEventListener('mousemove', mouseMoveEvent);
    screen.addEventListener('mouseup', mouseUpEvent);
    document.querySelector('.clear').addEventListener('click', clearScreen);

    function colorClickEvent(e) {
    let color = e.target.getAttribute('data-color');
    currentColor = color;

    document.querySelector('.color.active').classList.remove('active');
    e.target.classList.add('active');
      }

    function mouseDownEvent(e) {
    canDraw = true;
    mouseX = e.pageX - screen.offsetLeft;
    mouseY = e.pageY - screen.offsetTop;
    }

    function mouseMoveEvent(e) {
    if (canDraw) {
        draw(e.pageX, e.pageY);
    }
    }

    function mouseUpEvent() {
    canDraw = false;
    }

      function draw(x, y) {
      let pointX = x - screen.offsetLeft;
          let pointY = y - screen.offsetTop;

    ctx.beginPath();
    ctx.lineWidth = 5;
    ctx.lineJoin = 'round';
    ctx.moveTo(mouseX, mouseY);
    ctx.lineTo(pointX, pointY);
    ctx.closePath();
    ctx.strokeStyle = currentColor;
    ctx.stroke();

    mouseX = pointX;
    mouseY = pointY;
      }

      function clearScreen() {
        ctx.clearRect(0, 0, screen.width, screen.height);
          }
          
      
  </section>
    <section id="funcionamento-dos-filtros">
      <h2>Instruções de Uso</h2>
      <p>Para utilizar a aplicação, é necessário baixar os arquivos do projeto ou clonar o repositório. Em seguida, abra o arquivo index.html em um navegador web compatível.</p>
      <p>Além disso, é possível contribuir com o projeto propondo melhorias, correções de bugs ou adição de novos recursos. Para isso, basta seguir as instruções disponíveis no repositório. ✍️</p>
    </section>
    <section id="instruções-de-inicialização-do-projeto">
      <h2>Instruções de Inicialização do Projeto</h2>
      <ol>
        <li>Abra o arquivo <code>index.html</code> no seu navegador web preferido. 🌐
          <img src="https://github.com/edvaldovitor250/dashbord/assets/116117189/8b9fb383-d9e5-44b8-9e54-dff95d16fb44" alt="Visual Studio Code - index.html">
        </li>
        <li>Recomenda-se a utilização da extensão Live Server no Visual Studio Code. 🚀
          <img src="https://github.com/edvaldovitor250/dashbord/assets/116117189/88c85725-2358-4f13-b6ed-1e9270f87beb" alt="Extensão Live Server">
        </li>
        <li>Após configurar a extensão, basta clicar no botão "Go Live" para iniciar o servidor local e visualizar o projeto. 🚀
          <img src="https://github.com/edvaldovitor250/jogo-da-velha/assets/116117189/abf9458d-1816-43d1-abe0-8693d8d0a462" alt="parte3">
        </li>
      </ol>
    </section>
    <section id="tecnologias-utilizadas">
      <h2>Tecnologias Utilizadas</h2>
      <table>
        <thead>
          <tr>
            <th><img src="https://skillicons.dev/icons?i=html" alt="HTML5"> HTML</th>
            <th><img src="https://skillicons.dev/icons?i=css" alt="CSS"> CSS</th>
            <th><img src="https://skillicons.dev/icons?i=js" alt="JavaScript"> JavaScript</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>🔖 5</td>
            <td>🔖 3</td>
            <td>🔖 ES6</td>
          </tr>
        </tbody>
      </table>
    </section>
    <footer>
      <p>Autor: Este projeto foi desenvolvido por Edvaldo Vitor. 👨‍💻</p>
      <p>Licença: Este projeto está licenciado sob a MIT License. ⚖️</p>
    </footer>
  </main>
</body>
