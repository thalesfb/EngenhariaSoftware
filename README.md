# Sistema de Voos (S.V.) - Documentação de Modelagem

## Introdução
Este documento oferece uma visão geral dos diagramas de Casos de Uso e Modelo Entidade-Relacionamento (MER) para o Sistema de Voos de uma companhia aérea. Os diagramas foram desenvolvidos para facilitar o entendimento e a implementação das funcionalidades do sistema que apoia a venda de passagens aéreas via Internet.

## Tabela de Requisitos

| ID  | Nome                         | Descrição                                                                                       | Prioridade | Pré-condição                        | Pós-condição                     |
|-----|------------------------------|-------------------------------------------------------------------------------------------------|------------|-------------------------------------|-----------------------------------|
| F1  | Criar Conta                  | Permite ao passageiro criar uma conta, informando dados pessoais e informações de login.       | Alta       | Nenhuma                             | A conta é criada com sucesso.     |
| F2  | Interface Diferenciada       | O sistema deve oferecer uma interface diferenciada para o mantenedor e para os passageiros.    | Média      | Nenhuma                             | A interface adequada é exibida.   |
| F3  | Gerenciar Tipos de Voo       | Permite ao mantenedor gerenciar tipos de voo, incluindo/alterando/excluindo informações.        | Média      | Mantenedor autenticado              | Tipos de voo são gerenciados.     |
| F4  | Gerenciar Tipos de Aeronaves | Permite ao mantenedor gerenciar tipos de aeronaves, incluindo/alterando/excluindo informações.  | Média      | Mantenedor autenticado              | Tipos de aeronaves são gerenciados.|
| F5  | Gerenciar Aeronaves          | Permite ao mantenedor gerenciar aeronaves, incluindo/alterando/excluindo informações.           | Média      | Mantenedor autenticado              | Aeronaves são gerenciadas.        |
| F6  | Gerenciar Funcionários       | Permite ao mantenedor gerenciar funcionários, incluindo/alterando/excluindo informações.        | Média      | Mantenedor autenticado              | Funcionários são gerenciados.     |
| F7  | Gerenciar Aeroportos         | Permite ao mantenedor gerenciar aeroportos, incluindo/alterando/excluindo informações.          | Média      | Mantenedor autenticado              | Aeroportos são gerenciados.       |
| F8  | Gerenciar Voos               | Permite ao mantenedor gerenciar voos, incluindo/alterando/excluindo informações.                | Alta       | Mantenedor autenticado              | Voos são gerenciados.             |
| F9  | Comprar Passagem             | Permite ao passageiro comprar uma ou mais passagens aéreas, indicando voos e assentos desejados.| Alta       | Passageiro autenticado              | Passagem comprada com sucesso.    |
| F10 | Confirmar Pagamento          | Permite ao passageiro confirmar o pagamento, escolhendo o método de pagamento.                 | Alta       | Passageiro autenticado              | Pagamento confirmado ou ficha emitida.|
| F11 | Limitar Compra por Ficha     | Limita a compra de passagens por ficha de compensação para voos a mais de 3 dias úteis da data de compra. | Média | Passageiro autenticado          | Restrição aplicada corretamente. |
| F12 | Confirmar Compra             | Confirma a compra de passagens via cartão de crédito ou ficha de compensação.                  | Alta       | Passageiro autenticado, banco ou empresa de cartão validando | Passagem confirmada ou invalidada.|
| F13 | Cancelar Reservas Inválidas  | Cancela reservas de passagens não pagas 24 horas antes do voo e notifica o passageiro por e-mail. | Alta | Passageiro autenticado           | Reservas inválidas canceladas.    |
| F14 | Cancelar Compra              | Permite ao passageiro cancelar uma compra de passagem se feito com antecedência mínima de 24 horas antes do voo. | Alta | Passageiro autenticado | Compra cancelada, estorno processado.|
| F15 | Gerar Relatórios             | Permite ao mantenedor gerar relatórios sobre diversos aspectos do sistema, como ocupação de voos e receitas. | Média | Mantenedor autenticado         | Relatórios gerados corretamente. |
| F16 | Consultar Voos Programados   | Permite ao passageiro consultar voos programados para um determinado dia.                       | Média      | Passageiro autenticado              | Voos listados corretamente.       |

## Diagramas

### Diagrama de Casos de Uso (DCU)

O Diagrama de Casos de Uso abaixo descreve as interações entre os atores (Passageiro e Mantenedor) e o sistema, abrangendo funcionalidades como criação de conta, compra e cancelamento de passagens, gestão de voos, e emissão de relatórios.

![Diagrama de Casos de Uso](https://www.plantuml.com/plantuml/png/RT9HRjim30RWTv-2wDFwq1rWA89sGzUN5UYMOU-4pBX2PDAWg6B1iCFi33j2BZOhCkQ6o9j1Vg8X_hhBXcfbJ5sYdO49Q1nU3Fge52mATtaVUKB54IOCUnneQuT4KDl8GwAkms2Yy8mvpzseiXIUa8sOUj6k-w_XQXkpqOZG4_mGoLVmgmDuzqaZAWHXmsl0N0k4HlSXI66xFX4P9vtHr7uqDlUn7Bx7iATcjfGeHE6PpOhOfAgbRbl2PHHoe5H_U9hPJ2i-5mqlcAavuLoIpV1L93VsjP0UFgUwfNn2NsI8t7hjSobAiLPTlclvaPGunBE1JyWuq3BHAIGLnbSwe_THW-Bk8fv4JRokHOztXUkYZdyqdlk7SKfo86e77iPeKK4feHt_hlQHc1IDlj4oVCRh2u2Rcysw3TzO5-8xFdKFNDokwLBsNP-l5pxQ6QnFsDt8DTOR-OvFrmENwMNYW_J2HtUHN4ZixJhX_Va2uGFStaOEgVIqsNZhrqdDqqyZxYjtKROZwmGt_NTtDvyhO_e7)

#### Funcionalidades Principais

- **Criar Conta**: Permite que passageiros se registrem no sistema.
- **Comprar Passagem**: Passageiros podem comprar passagens aéreas.
- **Selecionar Assento**: Durante a compra, passageiros escolhem seus assentos.
- **Consultar Voos**: Permite que passageiros consultem detalhes e disponibilidade de voos.
- **Gerenciar Voos/Aeronaves/Aeroportos/Funcionários**: Funcionalidades exclusivas do mantenedor para administrar diferentes aspectos do sistema.

### Modelo Entidade-Relacionamento (MER)

O MER fornece uma representação estrutural do banco de dados subjacente, detalhando como as entidades como Passageiros, Voos, Aeronaves, e Aeroportos estão inter-relacionadas.

![Modelo Entidade-Relacionamento](https://www.plantuml.com/plantuml/png/dLR1Rjim3BtdAunSiWxp3-pKO6k7xLGKnQu1ApCE0KaqABbOr_HZTXhs7VsnILPgowxXhTrbDldy7aazAZrt7iItHg_GUlBtnVeAdMDO5-2AAnJ7jdXO5U7V-q8r--9ZuRoGhRjGMNR_MJOuJbJWOMV1AJA1baCoH73rk1fKm3ceaOIJKdX5MwFqObI5hyZwN2Wl82UxRAqYja-_X1BTXMaqtoF-DriAWCUQXI24qRRctUQAD7lUV2WsdzYGSvr2VDrwj5MGnyrPNiYDm2teGohY6zykwbErQ_efP6dD2lJEdwZ69KPLGSKxnGP54UZPWLoK1aYdKSIdVzRHdNcMGWCqJts36lTiCHtR8JozcZoC5cNIcAU6vrlfEdxwdMQwhIe9TA-Mb1O6zg663A4uU0QJNKV8Mo2PLgkeWWh7CNGUgYaEczcchhzqtLpNVIFJcIptanOCeoMXtwuOPwc1Ku9bLlexfqbUQgeFVgh_OfW75X3Yu5JnLCKIF1aSfTG1QnYdgbP0mK2NphTVgyzidluuJwhRfQ_MerY86mmw1Yu5uoWtPuaBdH9gV4X72VoH204buEzmDx802zLeibWYy6Hv26RJsA9mm-9FxYA9BulkSbJhgPVOuDlyqG2vsLFQdhfxBai9xFEw8cvFAX3AjCJfBWqpLC1fWlaQxhgRrxFBU0mqCCHd3OmEvGwIYzDpFA0ttNSXViSyDRSarjpSUnO3WQE6wPeEtGoV3KKFFox7OrdoGxoP0s3Ti7CjhL_aqvsvX4WNtmAWlwYMCDVrVFgHo_8X7sk42OAcdx1UfSNjE8x7mHi1qdgQXoHN1qHQZmN0QLVMgrpzaJjO-YZLiaV1qc4HnFhVsjHL1WFDAbg-0GcuqnyJ9rJVxIJ-pBOwHrkrHly5)

#### Entidades Principais

- **Pessoa/Passageiro/Funcionário**: Representam os usuários e operadores do sistema.
- **Voo/Aeronave/Aeroporto**: Core do sistema de reservas, descrevendo a logística e detalhes dos voos.
- **Reserva**: Relaciona passageiros a voos específicos e detalhes de pagamento.

## Visualização dos Diagramas

Para visualizar os diagramas incluídos neste README, você pode utilizar qualquer visualizador de imagens compatível com o formato dos arquivos de diagrama. Alternativamente, plataformas como PlantUML ou qualquer ferramenta UML compatível podem ser utilizadas para abrir e editar os arquivos de diagrama.

## Contribuições

Contribuições para o desenvolvimento ou aprimoramento do Sistema de Voos são bem-vindas. Por favor, envie suas sugestões ou pull requests através do nosso sistema de gerenciamento de versões.