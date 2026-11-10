# SnappzGo no Google Stitch — prompts tela por tela

## Como usar
1. Em **"Paste existing DESIGN.md"** cole o conteúdo de [`stitch/DESIGN.md`](DESIGN.md).
2. Em **"Public GitHub repository"** cole: `https://github.com/Maiconsmendonca/snappzgo-prints`
3. Em **"Additional instructions"** cole o bloco **Instruções adicionais** abaixo (uma vez só).
4. Depois mande **um prompt por tela** (as seções numeradas). Para cada tela, **anexe/aponte o print de referência indicado** (arquivo em `full/…`; link cru em "Referência"). Peça para ficar **igual em estrutura** ao print, só com o acabamento do DESIGN.md.

> Base dos links crus: `https://raw.githubusercontent.com/Maiconsmendonca/snappzgo-prints/main/full/`

---

## Instruções adicionais (colar uma vez)

```
Estou recriando as telas do app mobile SnappzGo (Android, pt-BR), um app de gestão financeira e semáforo de corridas para motoristas de app. Siga ESTRITAMENTE o DESIGN.md que colei.

Regras globais para TODAS as telas:
- Formato: tela de celular (não site). Sem "hero", sem textos de marketing, sem "scroll to explore".
- Idioma: português do Brasil. Dinheiro no formato R$ 1.234,56 (vírgula decimal). Use os valores e textos EXATOS do print de referência de cada tela — não invente dados nem nomes.
- Fonte Manrope em tudo. Fundo das telas em creme #F2F3EF (nunca branco puro). Cards brancos arredondados com sombra suave.
- Hubs (Hoje, Ganhos, Finanças, Carro, Você) têm cabeçalho escuro teal com degradê + corpo claro rolável. Itens de menu = card com chip de ícone colorido à esquerda + título + subtítulo + chevron.
- Traga COR na estrutura (teal + âmbar + chips de categoria do DESIGN.md), mas sem "salada de frutas": botão primário é sempre teal; cores de categoria só nos chips de ícone.
- FAB sempre SÓ ÍCONE (circular, teal, "+"), nunca escrito, e nunca tapando o último item da lista (padding inferior).
- Barra inferior de 5 abas (Hoje/Ganhos/Finanças/Carro/Você) PERSISTENTE, inclusive em subtelas; some só em Lançar, mapa e onboarding do leitor.
- Semáforo = vermelho #EF4444 / amarelo real #F2C200 (não laranja) / verde #10B981.
- Para cada tela que eu enviar, recrie a MESMA estrutura e os MESMOS blocos do print de referência, na mesma ordem. Não adicione nem remova seções.
```

---

# INÍCIO

## 1. Hoje (tela principal)
**Referência:** `full/01_hoje.png`
```
Tela "Hoje" do SnappzGo (hub principal). Cabeçalho claro com saudação "Boa tarde, Maic…" + "terça, 10 de novembro", e à direita 4 ícones: engrenagem, mapa, megafone e um botão redondo vermelho "SOS". Corpo rolável, de cima para baixo:
1) Card teal escuro "O semáforo está desligado" com texto "Deseja ativar? Leva 2 minutos…" e botão branco "Ativar agora".
2) Card teal escuro grande "META DE HOJE · LÍQUIDO": à esquerda um anel de progresso com "falta R$ 79,99" dentro; à direita "Já fiz" + "R$ 12,27" (grande) + "de R$ 92,26". Abaixo, mini-stats em 3 colunas: Combustível = "abastecer" (em âmbar), Contas cobertas = "não", Seu dia típico = "R$ 76,27". Abaixo, aviso com bolinha vermelha: "As contas pedem R$ 3.135,15/dia, acima do seu ritmo…" e "Pela sua média, faltam ≈ 106 km ou ≈ 7h59…".
3) Card branco "TURNO EM ANDAMENTO": "Desde 09/11 seg 23:47 · KM 111.130", "Começou com ~108 km de autonomia (17,8 L)", "Ganhos R$ 12,27 · Combustível R$ 0,00", botão teal "Encerrar turno", dois botões contorno "Abasteci" e "Ganho", e link "Terminei por hoje: fechar o dia".
4) Card âmbar claro "Abasteça antes de rodar": texto "Você tem ~108 km até a reserva…" e link "Ver o posto mais barato perto de mim".
5) Card branco "PRÓXIMAS CONTAS": "Na ordem abaixo, você fica em dia em 30/04 sex." e lista com data/etiqueta "hoje" + nome + prazo + valor (cartão credito R$ 2.000,00; condominio R$ 450,00; prestação apto R$ 1.300,00) + "+ 10 conta(s) nos próximos 90 dias".
FAB circular "+" no canto inferior direito. Barra inferior com Hoje ativo.
```

## 2. Meta — "Por que esse valor?" (modal do ⓘ)
**Referência:** `full/50_meta_porque.png`
```
Tela de detalhe da meta "Por que esse valor?" (abre pelo ⓘ do card de meta). É uma folha rolável, só texto e números, sem cabeçalho de hub. Blocos:
1) "Por que esse valor?" + tabela: "Contas e saídas dos próximos 90 dias R$ 19.450,00", "(–) Dinheiro disponível R$ 614,85" (caixa até ontem R$ 671,89; menos o fundo do carro R$ 44,77).
2) "A data mais apertada: prestação apto, 10/11 ter" + "Juntar até lá R$ 3.135,15" + "÷ dias de trabalho até a véspera 1" + "= O que as contas pedem por dia R$ 3.135,15".
3) "Sua média: R$ 15,25/h líquidos…", "Seu dia completo típico R$ 76,27", "Meta mais alta possível R$ 92,26", "= Meta de hoje R$ 92,26" (destaque).
4) Parágrafo explicativo da meta.
5) "O que resolve" + parágrafo.
6) "Plano de saída" + lista de pagamentos por data (10/11 cartão credito R$ 707,11; 11/11 cartão credito (1 dia de atraso) R$ 92,26; … 27/11 Financiamento Carro 1/47 R$ 922,60; 28/11 …) + "Em dia em 30/04 sex".
7) Card claro "HOJE: PARA ONDE VAI O QUE VOCÊ GANHOU": Ganhos R$ 12,27, barra, "SEPARE" → Reserva R$ 32,99, "Livre para as contas e para você −R$ 20,72".
Sem barra inferior (é subtela modal).
```

---

# GANHOS

## 3. Ganhos (hub)
**Referência:** `full/02_ganhos.png`
```
Hub "Ganhos". Cabeçalho teal escuro: título "Ganhos" + 3 colunas (Ganho · 7 dias R$ 594,05; Lucro · 7 dias R$ 568,17 em verde claro; Turnos 3) + linha "Melhor horário hoje: 00h–03h · R$ 1,26/km". Corpo:
Seção "No volante" (card com itens, cada um com chip de ícone colorido): "Leitor e semáforo / Balão sobre o Uber e 99" (ícone olho teal); "Metas da corrida / R$/km, R$/h e nota mínima" (bandeira verde); "Vale a pena a corrida?" (calculadora âmbar); "Corrida particular / Quanto cobrar" (documento âmbar); "Sons, voz e permissões" (alto-falante azul).
Seção "Histórico e análise" (outro card): "Meus turnos / 7 dias: 3 turnos · R$ 594,05" (carro teal); "Histórico de ofertas" (relógio-histórico roxo); "Raio-X das corridas" (gráfico roxo); "Melhores horários" (relógio teal); "Zonas quentes" (pin vermelho).
FAB "+" e barra inferior com Ganhos ativo.
```

## 4. Leitor e semáforo
**Referência:** `full/10_leitor.png`
```
Subtela "Leitor de corridas" (barra de topo com seta voltar + título). Tela longa, rolável. Blocos na ordem:
1) Card teal escuro "Configure o leitor — 3 de 4 passos concluídos" com barra de progresso e botão desabilitado "Conclua os passos abaixo".
2) Botão teal "Configurar passo a passo".
3) "Passos para funcionar": card "Custo do seu carro — OK ✓ (verde)"; card passo "2 Ativar o leitor na acessibilidade" com instruções e botões "Abrir acessibilidade" e "Liberar no app"; card "Permitir rodar em segundo plano — OK"; card "Teste do balão — OK".
4) "Suas metas": linha "R$ 1,50/km · R$ 50,00/h · mínimo R$ 10,00 · nota ≥ 4,90 · toque para ajustar".
5) Toggle "Lançar o ganho de cada corrida automaticamente" (ligado).
6) Item "Corridas oferecidas (histórico)".
7) Toggle "Anunciar a oferta por voz" (desligado).
8) Toggle "Botões de mapa no balão" (desligado).
9) "Modelo do balão": segmented Completo/Compacto/Mínimo (Completo ativo).
10) "Campos do balão": chips R$/hora, Nota, Lucro e meta.
11) "Transparência do balão": slider "Mais transparente · 96%".
12) Toggle "Gravar o percurso das corridas" (desligado).
13) "Bairros de embarque a evitar": campo "Separe por vírgula".
14) "Ajuste fino": item expansível "Calibração e teste de leitura".
Sem barra inferior.
```

## 5. Metas da corrida / Faixas do semáforo
**Referência:** `full/11_metas_faixas.png`
```
Subtela "Metas de corrida". Tela longa. Blocos:
1) Card teal escuro "SUAS METAS POR CORRIDA" com 3 blocos: Por km R$ 1,50, Por hora R$ 50,00, Valor mínimo R$ 10,00 — cada um com etiqueta "manual" (pílula âmbar). Legenda "Toque numa meta para ajustar à mão…".
2) Card "FAIXAS DO SEMÁFORO": texto explicando os marcadores, e 4 linhas, cada uma com rótulo + dois chips (vermelho "< X" e verde "≥ Y") + um SLIDER de trilho tricolor vermelho→amarelo→verde com dois marcadores:
   - R$/km: "< R$ 1,20" / "≥ R$ 1,50"
   - R$/hora: "< R$ 40,00" / "≥ R$ 50,00"
   - Valor da corrida: "< R$ 6,00" / "≥ R$ 10,00"
   - Nota do passageiro: "< ★4,89" / "≥ ★4,90"
   Legenda "Deixe o limite vermelho vazio para desligar…".
3) Card "SUA ROTINA": slider "Dias por semana 7 dias"; slider "Horas por dia 5 h"; "Meta fixa (opcional)" com segmented "Por mês / Por dia" (Por mês ativo); campo "Quanto quer ganhar livre por mês"; botão "Recalcular"; linha "≈ R$ 242,49/dia de trabalho · R$ 1.697,46/semana"; aviso verde "Sua meta (R$ 7.350,00/mês) cobre as contas, a reserva e as atrasadas do mês".
4) "Quando o que faço for diferente do planejado": chips Perguntar / Ajustar sozinho / Seguir o planejado (Perguntar ativo) + parágrafo.
Sem barra inferior.
```

## 6. Vale a pena a corrida?
**Referência:** `full/12_vale_a_pena.png`
```
Subtela "Vale a pena a corrida?" (calculadora curta, cabe numa tela). Campos empilhados num card: "Valor oferecido" (R$ 0,00, em foco teal), "Km até o passageiro", "Km da corrida", "Minutos no total (opcional)". Abaixo, texto "Custo do seu carro: R$ 0,85/km (combustível R$ 0,40 + desgaste R$ 0,06 + fixos R$ 0,39). Ajuste em Mais > Carro." e, embaixo, "Preencha o valor e os km para ver se compensa." Sem barra inferior.
```

## 7. Corrida particular
**Referência:** `full/13_corrida_particular.png`
```
Subtela "Corrida particular" (cabe numa tela). Card com campos: "Embarque (endereço)", "Destino (endereço)", botão destacado "⇅ Calcular pela rota (da sua posição)", "Km até o passageiro", "Km da corrida", "Minutos no total (opcional)", "Pedágio (ida e volta, se tiver)". Abaixo, "Quanto quero ganhar pelo meu serviço" com segmented de 4: Minhas metas / Por km / Por hora / Valor fixo (Minhas metas ativo). Rodapé "Preencha os km para ver o preço." Sem barra inferior.
```

## 8. Sons e avisos
**Referência:** `full/14_sons.png`
```
Subtela "Sons e avisos". Blocos em cards:
1) "MENSAGENS DO MAPA AO VIVO" (chip azul): "Som" com chips Plim/Sino/Buzina/Moeda/Sem som (Plim ativo); toggle "Ler a mensagem em voz alta" (ligado) com exemplo "Carlos: aqui tá bombando, vem pra cá"; seletor "Voz: Padrão do celular" + botão play.
2) "OFERTAS DE CORRIDA": toggle "Anunciar a oferta por voz" (desligado); "Volume da voz 100%" com slider; legenda "Vale para a oferta e as mensagens do mapa.".
3) "BOLHA FLUTUANTE": toggle "Mostrar a bolha com o app minimizado" (ligado) + descrição.
4) "OUTROS AVISOS": lista com ícone de som à direita: Alertas na via (Ligado), Pedidos de ajuda (Ligado), Meta em risco (Ligado), Manutenção do carro (Ligado), Promoções e avisos (Ligado).
5) "PERMISSÕES": Notificações (Liberado ✓ verde), Leitor (acessibilidade) com botão "Liberar", Localização o tempo todo com botão "Liberar", Bateria sem restrição (Liberado ✓).
Sem barra inferior.
```

## 9. Meus turnos
**Referência:** `full/15_meus_turnos.png`
```
Subtela "Turnos", mês "Novembro de 2026" com setas ‹ ›. Card "RESUMO DO MÊS": "Lucro real do mês R$ 590,34" (grande, verde) + "Bruto R$ 635,11 / R$ 0,81/km (vermelho)". Grade de métricas: Combustível R$ 0,00, Desgaste R$ 44,77, KM rodados 782, Horas 58h58, Lucro/km R$ 0,75, Lucro/hora R$ 10,01, Corridas 44, Ganho/corrida R$ 14,43, KM sem passageiro 446 (57%) em vermelho, Custo sem passageiro R$ 377,43 em vermelho. Depois "LUCRO REAL POR DIA" como LISTA DE BARRAS HORIZONTAIS (dia · barra proporcional teal · valor) — não um gráfico de barras finas. Depois card "PARA ONDE FOI O DINHEIRO DO MÊS" (Ganhos 782 km · 58h58 + barra colorida). Lista de turnos do mês abaixo. FAB circular "+" (era "Turno passado"). Sem barra inferior.
```

## 10. Histórico de ofertas
**Referência:** `full/16_historico_ofertas.png`
```
Subtela "Histórico de ofertas": lista de ofertas lidas pelo leitor, cada item com badge de plataforma (wordmark Uber/99 com borda colorida de qualidade), valor, horário/endereço e R$/hora. Recrie a estrutura exata do print de referência. Sem barra inferior.
```

## 11. Raio-X das corridas
**Referência:** `full/17_raiox.png`
```
Subtela "Raio-X das corridas". Topo: segmented "7 dias / 30 dias" (30 dias ativo). Card teal escuro "CORRIDAS CONCLUÍDAS · 43 DE 45 ACEITAS" com 6 números: Por hora real R$ 47,01, Meta por hora R$ 50,00, Por km R$ 1,51, Tempo médio real 19 min, Tempo estimado 16 min, Com passageiro 23% do turno. Seção "O que o raio-X mostra" com 3 cards de insight (ícone de atenção âmbar): "47% das corridas aceitas estavam abaixo da meta por km…", "Muito tempo sem passageiro…", "No ritmo atual: 29,1 h por dia…". Depois título "Corridas concluídas" e LISTA de corridas: cada item com badge wordmark "Uber" com BORDA colorida (vermelha/amarela/verde = qualidade), duração + valor, data/endereço, e "R$ X por hora". Rodapé link "Ajustar minhas metas". Sem barra inferior.
```

## 12. Melhores horários
**Referência:** `full/18_melhores_horarios.png`
```
Subtela "Melhores horários": recrie a mesma estrutura do print (análise de melhores faixas de horário/retorno). Use os mesmos blocos e números do print de referência. Sem barra inferior.
```

## 13. Zonas quentes
**Referência:** `full/19_zonas_quentes.png`
```
Subtela "Zonas quentes". Topo: um mapa estático (mapa real cinza-claro, estilo Google Maps, mostrando Ribeirão Preto) dentro de um card arredondado. Abaixo, card teal escuro "ONDE AS CORRIDAS PAGAM MAIS": "Ribeirão Preto: R$ 1,50/km · 17% verdes" e "Serrana: R$ 1,20/km · 0% verdes". Abaixo, cards brancos de bairro: "Ribeirão Preto / 132 ofertas · 17% verdes — R$ 1,50/km" e "Serrana / 3 ofertas · 0% verdes — R$ 1,20/km". Rodapé: texto "Agrupado pelo bairro do endereço de embarque das ofertas dos últimos 30 dias…". Sem barra inferior.
```

---

# FINANÇAS

## 14. Finanças (hub)
**Referência:** `full/03_financas.png`
```
Hub "Finanças". Cabeçalho teal: "Finanças" + 3 colunas (Falta pra fechar R$ 5.862,08 em vermelho claro; A cobrir R$ 7.350,00; Disponível R$ 614,85). Corpo:
Seção "Contas e cartões" (card): "Calendário de contas / O que vence e quando" (calendário teal); "Carteiras e cartões" (carteira verde); "Contas a pagar / Cadastro" (lista roxo).
Seção "Relatórios" (card): "Contas atrasadas e plano / Nenhuma atrasada" (atenção vermelho); "Extrato e relatório (PDF)" (recibo cinza); "Previsão do mês" (gráfico roxo); "Simulador 'e se'" (controles âmbar).
FAB "+" e barra inferior com Finanças ativo.
```

## 15. Calendário de contas
**Referência:** `full/20_calendario_contas.png`
```
Subtela "Calendário de contas": recrie a mesma estrutura do print (o que vence e quando, por data). Mesmos blocos e valores do print de referência. Sem barra inferior.
```

## 16. Carteiras e cartões
**Referência:** `full/21_carteiras.png`
```
Subtela "Contas e cartões". Blocos:
1) Card teal escuro "ONDE ESTÁ O SEU DINHEIRO": "R$ 671,89" grande, "somando as 4 conta(s)", e lista com ícone de banco: Asas R$ 0,00, uber R$ 647,38, Neon R$ 0,00, caixa R$ 24,51.
2) Card "CONTAS" com botão "+ Conta" e lista (Asas / Banco R$ 0,00; uber / Banco R$ 647,38; Neon / Banco R$ 0,00; caixa / Banco R$ 24,51).
3) Card "CARTÕES DE CRÉDITO" com "+ Cartão" e texto "Cadastre seus cartões para lançar compras no crédito…".
4) Card "RESERVA": "Guardado: R$ 0,00 · 0% da meta" + barra; campos "Guardar por mês R$ 1.000,00" e "Meta total R$ 5.000,00"; botão "Salvar reserva"; dica.
5) Card "PARA ONDE VÃO OS GANHOS": linhas Uber→uber, 99→uber, inDrive→uber (dropdowns).
FAB circular "⇄" (Transferir) — SÓ ícone. Sem barra inferior.
```

## 17. Contas a pagar (cadastro)
**Referência:** `full/22_contas_pagar.png`
```
Subtela "Contas cadastradas": lista de cards de conta, cada um com nome + descrição (tipo · dia · recorrência · desde) + valor à direita: condominio R$ 450,00; prestação apto R$ 1.300,00; cartão credito R$ 2.000,00; cartão de credito R$ 3.000,00; Financiamento Carro R$ 1.300,00; prestação carro R$ 1.300,00. FAB circular "+" no canto. Sem barra inferior.
```

## 18. Contas atrasadas e plano
**Referência:** `full/23_contas_atrasadas.png`
```
Subtela "Contas atrasadas e plano": recrie a estrutura do print. No estado atual mostra que não há contas atrasadas / plano. Mesmos blocos do print de referência. Sem barra inferior.
```

## 19. Extrato e relatório
**Referência:** `full/24_extrato.png`
```
Subtela "Extrato". Navegação de mês no topo. Card "RESUMO DO PERÍODO": Entrou/Saiu/Sobra + "PARA ONDE FOI O DINHEIRO" com gráfico de pizza (paleta de categorias) + legenda por categoria. Abaixo, lista de lançamentos do mês (cada linha: categoria ou badge de plataforma + data/descrição/conta + valor em verde (+) ou vermelho (−)). Botão de PDF na barra de topo. Sem barra inferior.
```

## 20. Previsão do mês
**Referência:** `full/25_previsao.png`
```
Subtela "Previsão do mês" (cabe numa tela). Card "PREVISÃO DO MÊS": título vermelho "Faltam R$ 5.862,08 no fim do mês" + "No ritmo atual (R$ 43,04 líquidos por dia) não fecha. Precisa de mais R$ 293,11 por dia." + 4 números (Tenho agora R$ 614,85; A pagar no mês R$ 7.350,00 em âmbar; Ganho por dia R$ 43,04; Dias restantes 20). Card "COMO CALCULEI": linhas (Dinheiro disponível R$ 614,85; Feito hoje R$ 12,27; Média líquida por dia R$ 43,04; × dias que faltam 20; (−) Contas, reserva e atrasadas R$ 7.350,00) e "Saldo no fim do mês −R$ 5.862,08" em vermelho. Sem barra inferior.
```

## 21. Simulador "e se"
**Referência:** `full/26_simulador.png`
```
Subtela "Simulador 'e se'": recrie a estrutura do print (controles para simular cenários financeiros). Mesmos blocos do print de referência. Sem barra inferior.
```

---

# CARRO

## 22. Carro (hub)
**Referência:** `full/04_carro.png`
```
Hub "Carro". Cabeçalho teal: "Carro" + "Custo por km R$ 0,06" + "Próxima manutenção em 5.870 km" + linha "🔧 Alinhamento e balanceamento". Corpo:
Seção "Veículo": item "Carro, custo por km e manutenção" (chip carro teal).
Seção "Combustível": "Postos perto / Preços no mapa" (mapa verde); "Meus postos / Preço que paguei" (bomba âmbar).
FAB "+" e barra inferior com Carro ativo. (A tela tem bastante espaço vazio abaixo — mantenha assim.)
```

## 23. Carro — custo por km e manutenção
**Referência:** `full/30_carro_detalhe.png`
```
Subtela "Carro" (detalhe). Blocos:
1) Card "CUSTO POR KM RODADO": "R$ 0,85/km" grande + linhas com chip: Combustível R$ 0,40 (R$ 3,99/L ÷ 10,0 km/l), Manutenção R$ 0,00 (não calculada), Custos anuais R$ 0,06 (IPVA, licenciamento, seguro ÷ km do ano), Fixos do mês R$ 0,39 (financiamento, rastreador…). Rodapé "Combustível real gasto por km (60 dias): R$ 0,00.".
2) Card teal escuro "CORRIDA MÍNIMA POR KM": "R$ 0,85/km" + parágrafo "Conta todos os km da oferta…" + "KM atual 111.130" e "Fundo do carro R$ 44,77".
3) Card "COMBUSTÍVEL E USO": campo "Consumo (km/l) 10,0"; toggle "Tem kit GNV" (desligado); toggle "Carro flex (etanol e gasolina)" (desligado); campos "Tanque (litros) 50,0", "Reserva (litros) 7,0" (COM espaçamento entre eles), "Preço do litro R$ 3,99", "KM rodados por ano 40000", "KM atual do painel 111130".
4) Card "CUSTOS FIXOS" (continua abaixo).
Barra de topo tem um ícone de calculadora à direita. Sem barra inferior.
```

## 24. Postos perto (mapa)
**Referência:** `full/31_postos_perto.png`
```
Subtela "Postos perto": mapa em tela cheia (mapa real cinza-claro) com pinos de preço, chips de combustível e filtros flutuantes, e uma folha arrastável embaixo com a lista de postos. No emulador aparece a tela de permissão de localização — recrie a versão COM mapa e lista (estado normal). Sem barra inferior (tela de foco/mapa).
```

## 25. Meus postos
**Referência:** `full/32_meus_postos.png`
```
Subtela "Meus postos / Preço que paguei": recrie a estrutura do print (lista de postos e preços lançados). Mesmos blocos do print de referência. Sem barra inferior.
```

---

# VOCÊ

## 26. Você (hub)
**Referência:** `full/05_voce.png`
```
Hub "Você". Cabeçalho teal: avatar circular com inicial "M" + "Você" + "maicon.mendonca@hotmail.com" + chevron. Corpo:
Card teal escuro "Indique e ganhe — Convide motoristas com seu código e receba por Pix quando eles assinarem" (ícone presente).
Seção "Comunidade": "Alertas, promoções e ajuda" (chip pessoas roxo); "Aprovar preços dos postos / Nenhum aguardando" (checklist verde).
Seção "Aplicativo": "Ajustes, backup e segurança" (engrenagem cinza); "Sobre e atualizações" (info cinza).
Link "Falar com o suporte". SEM FAB. Barra inferior com Você ativo.
```

## 27. Indique e ganhe
**Referência:** `full/40_indique.png`
```
Subtela "Indique e ganhe". Card "SEU CÓDIGO": "JJ4Z2V" grande + "https://financas.snappz.com.br/i/JJ4Z2V" + botão teal "Compartilhar convite" + link "Copiar link". Parágrafo "Quem se cadastrar com seu código e pagar a primeira mensalidade gera para você 50% do valor do primeiro mês…". Dois cards: "A receber R$ 0,00" (âmbar) e "Recebido R$ 0,00" (verde). Card "CHAVE PIX PARA RECEBER" com link "Cadastrar" + "Cadastre sua chave Pix para receber as comissões.". Card "SUAS INDICAÇÕES (0)" + "Ninguém se cadastrou com seu código ainda. Compartilhe com outros motoristas!". Sem barra inferior.
```

## 28. Alertas, promoções e ajuda
**Referência:** `full/41_alertas.png`
```
Subtela "Comunidade" com abas no topo: Promoções / Alertas / SOS Ajuda. Recrie a estrutura do print (lista de avisos/promoções). Mesmos blocos do print de referência. Sem barra inferior.
```

## 29. Aprovar preços dos postos
**Referência:** `full/42_aprovar_precos.png`
```
Subtela "Aprovar preços dos postos": fila de preços de combustível enviados pela comunidade para aprovar. No estado atual está vazia ("Nenhum aguardando"). Recrie a estrutura/estado vazio do print. Sem barra inferior.
```

## 30. Ajustes, backup e segurança
**Referência:** `full/43_ajustes_backup.png`
```
Subtela "Ajustes, backup e segurança": recrie a mesma estrutura do print (opções de backup, bloqueio por senha/biometria, preferências do app). Use os mesmos blocos e toggles do print de referência. Sem barra inferior.
```

## 31. Sobre e atualizações
**Referência:** `full/44_sobre.png`
```
Subtela "Sobre e atualizações": recrie a estrutura do print (versão do app, atualizações, links). Mesmos blocos do print de referência. Sem barra inferior.
```

---

# LANÇAR E MODAIS

## 32. Lançar (gasto)
**Referência:** `full/50_lancar_gasto.png`
```
Tela "Lançar" (abre pelo FAB). Topo: segmented "Gasto / Ganho" (Gasto ativo, teal). Valor grande "0,00" num card. Campos: "Categoria: Combustível" (dropdown), "Forma de pagamento: Dinheiro" (dropdown com ícone), "Pago com a conta: uber" (dropdown com ícone de banco), "Litros", "Posto" (com ícone de bomba), link "⌖ Escolher posto perto de mim", "Combustível: Etanol" (dropdown), "Descrição", toggle "Faz parte do turno aberto — Turno desde 09/11 seg 23:47" (ligado). Botão inferior fixo teal "Salvar gasto". SEM barra inferior (tela modal de foco).
```

## 33. Configurações (menu da engrenagem ⚙️)
**Referência:** `full/60_config_menu.png`
```
Folha inferior (bottom sheet) "Configurações" que sobe de baixo sobre a tela Hoje (o fundo fica escurecido). Lista com chip de ícone: "Leitor e semáforo / Balão, modelo e campos exibidos" (olho teal); "Metas e Faixas / R$/km, R$/hora, nota e as cores" (bandeira verde); "Sons e voz / Volume da voz, bolha e avisos" (alto-falante azul); "Carro / Custo por km, combustível e manutenção" (carro âmbar). Puxador (handle) no topo da folha.
```

## 34. SOS / Ajuda (Comunidade)
**Referência:** `full/61_sos_ajuda.png`
```
Tela "Comunidade" na aba "SOS / Ajuda" (abas Promoções / Alertas / SOS Ajuda no topo, SOS ativa). Recrie a estrutura do print — é a aba de ajuda/suporte da comunidade. Barra de topo com seta voltar + sino à direita.
```

## 35. Mapa — Motoristas ao vivo
**Referência:** `full/62_mapa_vivo.png`
```
Tela "Motoristas ao vivo". No print aparece o pedido de permissão de localização: ícone de localização teal, título "Permita a localização o tempo todo", texto explicando o uso (mostrar posição no mapa de motoristas ao vivo só para quem você escolher; gravar o percurso das corridas; não usada para anúncios), e botão teal "Permitir". Barra de topo com seta voltar + estrela à direita. Recrie essa tela de permissão. (A versão com o mapa de motoristas ao vivo viria depois da permissão.)
```
