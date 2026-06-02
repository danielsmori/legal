# Política de Privacidade — Orlando Smart Concierge

**Última atualização:** 2 de junho de 2026
**Data de vigência:** A partir da instalação

Esta Política de Privacidade explica como o Orlando Smart Concierge ("nós", "o app"), publicado por Daniel Mori, coleta, usa e protege informações sobre você ao usar o aplicativo iOS Orlando Smart Concierge (o "App").

Nós deliberadamente mantemos a coleta de dados mínima. O resumo abaixo é a história completa; o resto do documento descreve cada item em mais detalhes.

## Resumo

| Dado | Por que coletamos | Para onde vai | Por quanto tempo guardamos |
|---|---|---|---|
| Sua localização aproximada (com o app aberto) | Detectar em qual parque você está, avisar sobre áreas de estacionamento sinalizadas | Seu dispositivo + nosso backend (Supabase, região US-East) apenas durante a requisição | Não é armazenado |
| Chave anônima do dispositivo (App Attest) | Verificar que as requisições vêm de uma cópia legítima do app | Nosso backend (Supabase) | Até você desinstalar o app |
| Fotos e quadros da câmera que você escolhe (Tax & Price Hunter, Lightning Lane) | OCR local no seu dispositivo | Permanecem no seu dispositivo. Nunca enviamos imagens. | Não é armazenado |
| Texto OCR de screenshots do Lightning Lane | Traduzido e explicado por um modelo de IA | Enviado ao Google Gemini para processamento. Não armazenado por nós. Sujeito aos [termos do Google](https://ai.google.dev/terms). | Não armazenado por nós |
| Mensagens enviadas ao Park Butler | Gerar uma resposta | Enviadas ao Google Gemini para processamento. Não armazenadas por nós. | Não armazenado por nós |
| Eventos de compra do Trip Pass | Desbloquear funcionalidades pagas | Apple (App Store) + RevenueCat. Nunca vemos seus dados de pagamento. | Pelo tempo que Apple/RevenueCat mantiverem o recibo |
| Endereço IP | Apenas para rate limiting por IP | Nosso backend (Supabase) | Janela móvel ≤ 24 horas |

Nós **não** coletamos, armazenamos ou vendemos:
- Seu nome, e-mail, telefone ou endereço
- Localização precisa em segundo plano
- Histórico de navegação
- Contatos, agendas, gravações de microfone ou dados de saúde
- Qualquer identificador de publicidade (IDFA)

---

## 1. Informações que Coletamos

### 1.1 Localização

O App solicita autorização de localização "Durante o uso". A localização é usada de duas formas:

- **Detecção de parque.** Quando o Park Butler ou SafeStop estão abertos, sua localização aproximada é usada no dispositivo para determinar qual parque de Orlando (Magic Kingdom, EPCOT, etc.) está mais próximo. O identificador do parque — não suas coordenadas — é então anexado às requisições do Park Butler para que o assistente possa dar respostas específicas do parque.
- **Proximidade do SafeStop.** Quando a aba SafeStop está aberta, sua localização é enviada ao nosso backend com um parâmetro de raio para buscar uma lista de áreas próximas. Suas coordenadas são usadas para calcular a resposta e descartadas imediatamente — não são armazenadas em nenhum banco de dados.

O App nunca solicita autorização de localização "Sempre" e nunca rastreia em segundo plano. O rastreador de estacionamento armazena a localização do seu carro apenas quando você toca explicitamente em "Estacionei aqui", e armazena apenas no seu dispositivo.

### 1.2 Chave de dispositivo do App Attest

Na primeira vez que o App se comunica com nosso backend em um dispositivo real, ele gera uma chave criptográfica no Secure Enclave (usando o framework App Attest da Apple) e envia a parte pública para nosso backend. Armazenamos a chave pública e um identificador de cliente gerado aleatoriamente. Usamos isso para verificar que requisições subsequentes vêm de uma cópia real e não modificada do App. Nós **não** recebemos seu Apple ID, nome ou qualquer identificador de dispositivo pelo qual você pudesse ser reidentificado.

### 1.3 Fotos e câmera

O App usa sua câmera (para o Tax & Price Hunter) e biblioteca de fotos (para o Lightning Lane Assistant) somente quando você explicitamente inicia uma dessas funcionalidades. O Reconhecimento Óptico de Caracteres (OCR) é executado inteiramente no seu dispositivo usando o framework Vision da Apple. **As imagens em si nunca são enviadas ao nosso backend ou a qualquer terceiro.**

Para o Lightning Lane Assistant, o texto extraído (não a imagem) é enviado ao Google Gemini para tradução e explicação.

### 1.4 Mensagens de chat

Quando você envia uma mensagem ao Park Butler, o texto da mensagem mais um pouco de contexto (o parque detectado, a dica de idioma atual) é enviado à API Gemini do Google. A resposta é transmitida de volta a você. Não armazenamos seu histórico de chat no nosso backend. O Google pode reter a requisição conforme descrito nos [termos da API Gemini](https://ai.google.dev/terms).

### 1.5 Informações de compra

Compras do Trip Pass são processadas pelo StoreKit da Apple e rastreadas pelo RevenueCat. Vemos o estado da assinatura (ativa / inativa / expirada) e um identificador opaco de usuário do RevenueCat. **Nunca vemos os dados do seu cartão de crédito, seu Apple ID, ou seu endereço de cobrança.** Questões de reembolso ou cobrança são tratadas diretamente pela Apple.

### 1.6 Endereço IP

Quando o App faz uma requisição ao nosso backend, seu endereço IP é brevemente usado para fins de rate limiting (prevenir abuso de APIs gratuitas). Ele é convertido em hash dentro de uma janela móvel de 24 horas e nunca associado a qualquer outro dado seu.

---

## 2. Como Usamos as Informações

Usamos as informações descritas acima para:

- Fornecer as funcionalidades que você usa explicitamente (assistente de parque, calculadora de preços, mapa de segurança, analisador de Lightning Lane)
- Verificar que as requisições vêm do App genuíno e não de abuso automatizado
- Aplicar limites de uso razoáveis em APIs de IA e câmbio de terceiros
- Processar e validar sua compra do Trip Pass
- Diagnosticar e corrigir bugs

Nós **não**:

- Usamos seus dados para publicidade
- Vendemos, alugamos ou compartilhamos seus dados com anunciantes terceiros ou data brokers
- Construímos perfis de publicidade ou comportamentais
- Treinamos qualquer modelo de IA com seus dados (a política de uso de dados do Google se aplica a mensagens enviadas pela API deles; ver [termos do Google](https://ai.google.dev/terms))

---

## 3. Compartilhamento de Informações

Compartilhamos informações apenas com os seguintes provedores de serviço, cada um usado estritamente para operar o App:

| Provedor | Finalidade | Dados compartilhados |
|---|---|---|
| Supabase (banco de dados + edge functions) | Hospedagem do backend | Chave anônima do dispositivo, IP para rate limiting, consultas de câmbio e tempo de fila |
| Google Gemini | Respostas de IA para o Park Butler e Lightning Lane | Texto da sua mensagem + contexto (identificador de parque, dica de idioma) + texto OCR do Lightning Lane |
| ExchangeRate-API | Taxas USD↔BRL e outras moedas | Nenhum dado seu — apenas consultamos o endpoint público de câmbio |
| themeparks.wiki | Tempos de fila dos parques | Nenhum dado seu — consultamos a API pública deles em um cronograma, independente de você |
| Apple App Store / StoreKit | Compra do Trip Pass | Seu Apple ID processa a transação; recebemos apenas um identificador opaco |
| RevenueCat | Rastreamento de assinatura do Trip Pass | Identificador opaco do usuário, eventos de compra |

Divulgamos informações quando exigido por lei (intimação, ordem judicial, etc.), mas a estrutura do App é projetada para que os dados que temos sobre você sejam intencionalmente mínimos.

---

## 4. Privacidade de Crianças

O App não é direcionado a crianças menores de 13 anos. Não coletamos conscientemente informações pessoais de crianças menores de 13 anos. Se você acredita que uma criança nos forneceu informações pessoais, entre em contato em [support@orlandosmartconcierge.app](mailto:support@orlandosmartconcierge.app).

---

## 5. Seus Direitos

Você pode:

- **Apagar seus dados.** Desinstale o App. Todos os dados no dispositivo (rastreador de estacionamento, chave do App Attest) são removidos automaticamente. Mande um e-mail para [support@orlandosmartconcierge.app](mailto:support@orlandosmartconcierge.app) se quiser que removamos também o registro anônimo da chave do dispositivo no nosso backend.
- **Gerenciar sua compra.** Cancele ou solicite reembolso do Trip Pass através do seu Apple ID (Ajustes → Apple ID → Assinaturas ou [reportaproblem.apple.com](https://reportaproblem.apple.com)).
- **Revogar permissões.** Localização, câmera, fotos, notificações: Ajustes do iOS → Apps → Orlando Smart Concierge.

Conforme a Lei Geral de Proteção de Dados (LGPD) brasileira, você tem direitos adicionais de acesso, correção, anonimização, eliminação e portabilidade de dados pessoais. Como coletamos pouquíssimas informações pessoalmente identificáveis em primeiro lugar, solicitações sob a LGPD tipicamente se resumem a "apague meu registro anônimo de dispositivo" — o que faremos sob demanda.

---

## 6. Retenção de Dados

| Dado | Retenção |
|---|---|
| Localização | Não armazenada. Usada apenas em trânsito. |
| Chave anônima do dispositivo | Armazenada até você pedir para apagarmos ou desinstalar o App |
| Imagens OCR | Não armazenadas. Permanecem no seu dispositivo. |
| Texto de chat/OCR enviado ao Google Gemini | Não armazenamos. Sujeito à política de retenção do Google. |
| Metadados de compra do Trip Pass | Pelo tempo que Apple e RevenueCat retiverem recibos (tipicamente a vida do seu Apple ID) |
| IP para rate limiting | ≤ 24 horas |

---

## 7. Segurança

- Todas as requisições entre o App e nosso backend usam HTTPS / TLS 1.3.
- Linhas do backend que tocam qualquer estado de usuário (`attested_clients`, etc.) são protegidas por Row-Level Security e acessíveis apenas pelo service role do backend.
- Assinaturas do App Attest verificam criptograficamente que requisições vêm de uma cópia legítima do App.
- Nunca recebemos os dados do seu cartão de pagamento — a Apple processa a transação.

Nenhum sistema é perfeitamente seguro. Se você descobrir um problema de segurança, envie um e-mail para [support@orlandosmartconcierge.app](mailto:support@orlandosmartconcierge.app).

---

## 8. Transferências Internacionais

O App é operado a partir dos Estados Unidos. A infraestrutura de backend é hospedada na região US-East do Supabase. Se você usar o App de fora dos Estados Unidos, seus dados serão transferidos e processados nos Estados Unidos.

---

## 9. Alterações nesta Política

Podemos atualizar esta Política de Privacidade de tempos em tempos. Mudanças materiais serão refletidas atualizando a data de "Última atualização" no topo. O uso continuado do App após uma mudança indica aceitação da política atualizada.

O histórico completo de alterações pode ser visto publicamente no [histórico Git deste documento](https://github.com/danielsmori/legal/commits/main/orlando-smart-concierge/privacy-policy-pt-BR.md).

---

## 10. Contato

Dúvidas, reclamações ou solicitações de exclusão de dados:

**Daniel Mori**
E-mail: [support@orlandosmartconcierge.app](mailto:support@orlandosmartconcierge.app)
