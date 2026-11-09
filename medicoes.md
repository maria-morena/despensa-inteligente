# Medição: registro manual x bot

## Método
- Mesmas 5 compras de 10 itens nos dois métodos (50 produtos).
- Manual: planilha com item, categoria, quantidade e validade; tempo de digitação, sem consulta da validade real (o tempo real seria maior).
- Bot: mensagem digitada na hora no Telegram (sem colar texto pronto); cronômetro do início da digitação até a confirmação do bot.
- Na compra 4, um item esquecido foi enviado em uma segunda mensagem e o tempo foi somado.

## Tempo
| Compra | Manual | Bot | Redução |
|---|---|---|---|
| 1 | 8min30s | 3min05s | 64% |
| 2 | 9min00s | 2min27s | 73% |
| 3 | 8min00s | 2min06s | 74% |
| 4 | 7min20s | 2min55s | 60% |
| 5 | 10min00s | 2min35s | 74% |
| **Média** | **8min34s** | **2min38s** | **69%** |
| Por produto | 51,4 s | 15,8 s | |

## Qualidade
- Itens corretos: 47/50 (94%). Erros de digitação ("intergal", "cabola 1jg", "detrgente") foram interpretados corretamente.
- Categorias: 24 sobrepostas no manual x 7 padronizadas com IA.
- Erros: validade de carnes cruas superestimada (frango 5 dias, carne moída 3, tilápia 3; o seguro é cerca de 1 a 2 dias).
- Simplificações intencionais não foram contadas como erro (ex.: "feijão carioca" virou "feijão", conforme a regra de nome genérico do prompt).

## Correção após a medição
O prompt não foi alterado durante a medição, para as 5 compras serem comparáveis. Depois dela, acrescentei uma regra para carnes cruas e testei de novo:

| Item | Na medição | Depois da correção |
|---|---|---|
| Peito de frango | 5 dias | 2 dias |
| Carne moída | 3 dias | 2 dias |
| Tilápia congelada | 3 dias | 90 dias |

Regra adicionada ao prompt: *"Para carnes, aves e peixes crus refrigerados, use no máximo 2 dias. Se o texto disser 'congelado', considere a validade no congelador."*
