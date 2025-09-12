<div style="font-family: Arial, sans-serif; line-height: 1.6; color: #333; max-width: 800px;">

  <h2 style="color:#2E86C1;">Chatbot WhatsApp com Upload de Arquivos</h2>

  <h3 style="color:#1ABC9C;">Fluxo de interação</h3>
  <ul>
    <li><strong>Usuário/Cliente:</strong> Interage com o chatbot via WhatsApp.</li>
    <li><strong>WhatsApp Cloud API:</strong> Recebe mensagens e envia respostas oficialmente.</li>
    <li><strong>IBM Watson:</strong> Processa linguagem natural das mensagens.</li>
  </ul>

  <h3 style="color:#F39C12;">Backend AWS</h3>
  <ul>
    <li><strong>Amazon API Gateway:</strong> Ponto de entrada HTTP, serverless e escalável.</li>
    <li><strong>Application Load Balancer:</strong> Distribui tráfego entre containers do Fargate.</li>
    <li><strong>ECS Fargate Cluster:</strong> Executa containers gerenciados, sem necessidade de servidores.
      <ul>
        <li><strong>router-app:</strong> Direciona requisições para outros serviços.</li>
        <li><strong>chatbot-app:</strong> Lógica principal do chatbot.</li>
        <li><strong>cache-manager-app:</strong> Gerencia cache com Redis.</li>
        <li><strong>notification-app:</strong> Envia notificações via SNS.</li>
        <li><strong>file-storage-app:</strong> Faz upload/download de arquivos para S3.</li>
        <li><strong>data-storage-app:</strong> Manipula dados estruturados no DynamoDB.</li>
      </ul>
    </li>
  </ul>

  <h3 style="color:#9B59B6;">Serviços auxiliares</h3>
  <ul>
    <li><strong>Amazon Redis (ElastiCache):</strong> Cache rápido e gerenciado para reduzir latência.</li>
    <li><strong>DynamoDB:</strong> Banco NoSQL, totalmente gerenciado, escalável e barato.</li>
    <li><strong>Amazon SNS:</strong> Sistema de notificação pub/sub desacoplado.</li>
    <li><strong>Amazon S3:</strong> Armazenamento de arquivos grande e durável.</li>
  </ul>

  <h3 style="color:#16A085;">Resumo do fluxo</h3>
  <p>Usuário envia mensagem → WhatsApp Cloud API → API Gateway → Load Balancer → router-app → serviços internos (chatbot, cache, storage, notificações) → respostas processadas pelo IBM Watson.</p>

  <br>
  <h3 style="color:#9B59B6;">Diagrama</h3>
  <img src="https://github.com/vanemart/desafio-aleks/blob/main/diagram/diagram.svg">

</div>
