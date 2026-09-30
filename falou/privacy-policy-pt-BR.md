# Política de Privacidade — Falou

**Última atualização:** 29 de setembro de 2026 (prevenção de abuso)
**Data de vigência:** A partir da criação da conta ou do primeiro uso do app

Esta Política de Privacidade explica como o Falou ("nós", "o serviço") trata dados pessoais, de acordo com a Lei Geral de Proteção de Dados Pessoais (Lei nº 13.709/2018, "LGPD").

O Falou é um aplicativo para macOS que transforma sua fala em texto, com tradução para o inglês, e insere o resultado no aplicativo que você está usando. O serviço é oferecido por Daniel Mori (CNPJ: a ser informado após a constituição da empresa), que é o **controlador** dos dados descritos aqui.

## Resumo

| Dado | Coletamos? | Para quê |
|---|---:|---|
| E-mail | Sim | Login por código e comunicações sobre o serviço |
| Nome e CPF/CNPJ | Só ao assinar | Cobrança e emissão de nota fiscal |
| Áudio da sua voz | Processado, **não armazenado** | Transcrever e traduzir o que você ditou |
| Texto ditado e traduzido | Processado, **não armazenado nos nossos servidores** | Devolver o resultado ao app |
| Histórico de ditados | Só no seu Mac, se você ativar | Consultar e copiar ditados recentes |
| Uso (palavras, duração do áudio, modo, versão do app) | Sim | Aplicar os limites do plano e medir a qualidade do serviço |
| Estatísticas anônimas do app | Sim, com opção de desligar | Entender uso e falhas, sem conteúdo |
| Estatísticas do site | Sim, sem cookies | Saber de onde vêm os visitantes |
| Dados de cartão | Não | Processados diretamente pelo Asaas |
| Localização, contatos, fotos | Não | O app não pede essas permissões |
| Nomes dos apps onde você escreve | Não sai do seu Mac | Usado só localmente para ajustar o tom do texto |

## 1. Dados que tratamos

### 1.1 Conta
Para usar o Falou, você cria uma conta com seu e-mail. Enviamos um código de 6 dígitos para confirmar que o e-mail é seu; não usamos senha.

### 1.2 Áudio e texto
Enquanto você segura a tecla de ditado, o app grava o microfone. Ao soltar a tecla, o áudio é enviado por conexão criptografada (HTTPS) para os nossos servidores, que o repassam aos provedores de inteligência artificial para transcrição e tradução. O resultado volta para o seu Mac e é inserido onde está o cursor.

**Não armazenamos o áudio nem o texto nos nossos servidores.** Eles existem apenas durante o processamento. Os provedores de IA podem manter esses dados por um período curto, para segurança e prevenção de abuso, conforme as políticas deles; não autorizamos o uso dos seus dados para treinar modelos.

O microfone só é usado enquanto você segura a tecla de ditado (ou no modo mãos-livres, que você liga e desliga).

### 1.3 Uso do serviço
A cada ditado registramos: data e hora, número de palavras, duração do áudio, modo usado (por exemplo, "traduzir para inglês"), provedor que processou, tempo de processamento e versão do app. Esses dados são necessários para aplicar os limites do plano (por exemplo, as 1.000 palavras semanais do plano Grátis) e para acompanhar a qualidade do serviço. **Não incluem o conteúdo do que você ditou.**

### 1.3.1 Prevenção de abuso
Para que o período de teste e a cota do plano Grátis valham uma vez por pessoa, cada ditado leva também um **identificador aleatório da instalação do app** no seu Mac, e comparamos contas que usam variações do mesmo e-mail (por exemplo, `nome+teste@gmail.com` e `nome@gmail.com`). Contas ligadas pelo mesmo e-mail ou pelo mesmo Mac compartilham um único período de teste e a mesma cota semanal gratuita. Esse identificador não revela quem você é e é usado mesmo com as estatísticas desligadas, porque é necessário para aplicar os limites dos planos. Também recusamos cadastros com e-mails temporários (descartáveis).

### 1.4 Cobrança
Ao assinar o plano Pro, pedimos seu nome e CPF ou CNPJ, que são enviados ao Asaas para gerar a cobrança e a nota fiscal. Os dados de pagamento (cartão, Pix ou boleto) são informados diretamente na página do Asaas; não temos acesso ao número do cartão.

### 1.5 Estatísticas do app
O app envia estatísticas anônimas, como "app aberto", tipo de erro ocorrido, versão do app e do macOS, e se as permissões necessárias foram concedidas, junto com um identificador aleatório da instalação. **Nunca enviamos áudio, texto ditado ou os nomes dos apps onde você escreve.** Você pode desligar essas estatísticas em Ajustes › Geral.

### 1.6 Estatísticas do site
No site falou.dev registramos a página visitada, o domínio de origem (por exemplo, linkedin.com), parâmetros de campanha (utm) e o tipo de dispositivo, com um identificador aleatório que dura apenas enquanto a aba está aberta. **Não usamos cookies de rastreamento, não guardamos seu endereço IP** e respeitamos o sinal "Do Not Track" do navegador.

### 1.7 No seu Mac
O app guarda localmente suas preferências, o glossário de termos e, se você ativar, o histórico dos últimos 50 ditados. O login fica guardado no Keychain do macOS. Esses dados não são enviados para nós.

## 2. Bases legais (art. 7º da LGPD)

- **Execução de contrato:** conta, processamento dos ditados, aplicação dos limites do plano e cobrança.
- **Cumprimento de obrigação legal:** emissão de nota fiscal e guarda de registros fiscais.
- **Legítimo interesse:** estatísticas do app e do site, segurança e prevenção de abuso (por exemplo, impedir contas criadas só para repetir o período de teste). Você pode se opor a esse tratamento a qualquer momento.

## 3. Com quem compartilhamos

Compartilhamos dados apenas com os fornecedores necessários para prestar o serviço (operadores):

| Fornecedor | País | O que recebe |
|---|---|---|
| Groq, Inc. | EUA | Áudio e texto, para transcrição e tradução |
| OpenAI, L.L.C. | EUA | Áudio e texto, **somente como reserva** quando a Groq está indisponível |
| Supabase, Inc. | EUA (servidores na Virgínia) | Conta, uso e dados de assinatura |
| Asaas Gestão Financeira S.A. | Brasil | Nome, CPF/CNPJ, e-mail e dados de cobrança |
| Cloudflare, Inc. | EUA | Hospedagem do site |
| Resend, Inc. | EUA | Envio do e-mail com o código de login |

**Não vendemos seus dados** e não os usamos para publicidade.

## 4. Transferência internacional

Alguns fornecedores ficam fora do Brasil. Essas transferências se baseiam nas garantias contratuais oferecidas por esses fornecedores, nos termos do art. 33 da LGPD.

## 5. Por quanto tempo guardamos

| Dado | Prazo |
|---|---|
| Áudio e texto ditados | Não são armazenados pelos nossos servidores |
| Conta, uso e assinatura | Enquanto a conta existir |
| Registros de pagamento e notas fiscais | 5 anos, por obrigação fiscal |
| Estatísticas do app e do site | Até 24 meses, sem conteúdo |

## 6. Segurança

Usamos conexão criptografada (HTTPS) em todas as comunicações, as chaves dos provedores de IA ficam somente nos nossos servidores, o login no Mac fica no Keychain do macOS, e o banco de dados aplica regras que impedem uma conta de acessar dados de outra. Nenhum sistema é 100% seguro; se ocorrer um incidente que possa causar risco relevante, avisaremos você e a ANPD, conforme a lei.

## 7. Seus direitos

Pela LGPD (art. 18), você pode pedir: confirmação de que tratamos seus dados, acesso, correção, anonimização, bloqueio ou eliminação de dados desnecessários, portabilidade, informações sobre compartilhamento e revisão de decisões automatizadas, além de se opor a tratamentos baseados em legítimo interesse.

**Exclusão da conta:** você mesmo pode excluir sua conta a qualquer momento em falou.dev › Minha conta › Excluir minha conta (ou pelo app, em Ajustes › Conta). A exclusão cancela a assinatura e apaga a conta, o perfil e o histórico de uso. Registros fiscais são mantidos pelo prazo legal.

Para os demais pedidos, escreva para o contato abaixo. Respondemos em até 15 dias. Você também pode reclamar à Autoridade Nacional de Proteção de Dados (ANPD), em gov.br/anpd.

## 8. Cookies e armazenamento no navegador

O site não usa cookies de rastreamento nem de publicidade. Quando você entra na sua conta pelo site, a sessão de login fica guardada no armazenamento local do navegador, apenas para manter você conectado.

## 9. Menores de idade

O Falou é destinado a pessoas com 18 anos ou mais. Não coletamos intencionalmente dados de menores.

## 10. Alterações

Podemos atualizar esta política. Mudanças relevantes serão avisadas por e-mail ou no app antes de entrarem em vigor.

## 11. Contato

Encarregado pelo tratamento de dados: Daniel Mori
E-mail: [danmoriyt@gmail.com](mailto:danmoriyt@gmail.com)

[Termos de Uso](./terms-of-service-pt-BR.md) · [Suporte](./support.md)
