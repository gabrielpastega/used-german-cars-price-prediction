<h2><strong>Sobre o projeto</strong></h2>
<p>O objetivo deste projeto &eacute; construir um modelo de previs&atilde;o de pre&ccedil;os de carros com base em diversas caracter&iacute;sticas dos ve&iacute;culos, como ano de fabrica&ccedil;&atilde;o, tipo de combust&iacute;vel, pot&ecirc;ncia do motor, quilometragem, entre outros e verificar como &eacute; afetado por outliers. O modelo ser&aacute; constru&iacute;do utilizando t&eacute;cnicas de regress&atilde;o e tratamento de outliers.</p>
<h2><strong>Conjunto de Dados</strong></h2>
<p>O conjunto de dados utilizado neste projeto foi obtido a partir do Kaggle (<a href="https://www.kaggle.com/datasets/ander289386/cars-germany">link</a>) e cont&eacute;m informa&ccedil;&otilde;es sobre diversos modelos de carros dispon&iacute;veis no site AutoScout24. Composto por 46.405 linhas e 9 features, o conjunto de dados abrange um per&iacute;odo de 10 anos, de 2011 a 2021, e suas features est&atilde;o divididas em 5 categ&oacute;ricas e 4 num&eacute;ricas.</p>
<h2><strong>An&aacute;lise Explorat&oacute;ria de Dados</strong></h2>
<p>&nbsp;Durante a an&aacute;lise explorat&oacute;ria, foram plotados gr&aacute;ficos de histogramas e boxplots para cada vari&aacute;vel num&eacute;rica do conjunto de dados, a fim de identificar outliers e verificar a distribui&ccedil;&atilde;o dos dados. Tamb&eacute;m foram plotados gr&aacute;ficos de barras para as vari&aacute;veis categ&oacute;ricas, para observar a frequ&ecirc;ncia de cada categoria.</p>
<p>Os dados categ&oacute;ricos demonstram um grande cardinalidade com 77 marcas &uacute;nicas e 841 modelos &uacute;nicos de ve&iacute;culos, j&aacute; a coluna c&acirc;mbio tem apenas 3 tipos de categorias e a tipos de oferta possui 5 op&ccedil;&otilde;es &uacute;nicas. A coluna de combust&iacute;vel possui 11 valores diferentes com predomin&acirc;ncia de Gasolina e Diesel,&nbsp;</p>
<p>Com rela&ccedil;&atilde;o &agrave;s vari&aacute;veis num&eacute;ricas, foram encontrados alguns valores extremos que representam poss&iacute;veis outliers, como pre&ccedil;os de carros, quilometragens e pot&ecirc;ncia do motor muito acima da m&eacute;dia. Verificou-se a presen&ccedil;a de valores duplicados e para trabalhar apenas com observa&ccedil;&otilde;es &uacute;nicas optou-se por remov&ecirc;-los</p>
<p>A an&aacute;lise explorat&oacute;ria tamb&eacute;m mostrou uma correla&ccedil;&atilde;o positiva entre o pre&ccedil;o dos carros e a pot&ecirc;ncia do motor, bem como uma correla&ccedil;&atilde;o negativa com pre&ccedil;o e a quilometragem.&nbsp;</p>
<p>A maior parte pertencendo a marca Volkswagen e a marca Mercedes-Benz com a maior diversidade de modelos e a grande maioria do ve&iacute;culos possuem valor abaixo de 19.940 &euro; (Euros).</p>
<p>Em resumo, a an&aacute;lise explorat&oacute;ria permitiu entender melhor as caracter&iacute;sticas do conjunto de dados e identificar poss&iacute;veis problemas a serem tratados antes da constru&ccedil;&atilde;o do modelo.</p>
<h2><strong>Pr&eacute;-Processamento de Dados</strong></h2>
<p>Durante o pr&eacute;-processamento de dados foi necess&aacute;rio tratar alguns problemas comuns em conjuntos de dados do mundo real, como a presen&ccedil;a de valores faltantes, outliers e alta cardinalidade dos dados.</p>
<p>Os valores faltantes foram preenchidos utilizando o m&eacute;todo de SimpleImputer para categ&oacute;ricas e KNNImputer para num&eacute;ricas. Al&eacute;m disso, as vari&aacute;veis categ&oacute;ricas foram transformadas atrav&eacute;s da t&eacute;cnica de codifica&ccedil;&atilde;o CatBoostEncoder, e as vari&aacute;veis num&eacute;ricas foram normalizadas com RobustScaler, esta t&eacute;cnica &eacute; menos sens&iacute;vel a datasets que possuem outliers.</p>
<h2><strong>Modelagem</strong></h2>
<p>Foram testados diversos algoritmos de regress&atilde;o para construir o modelo de previs&atilde;o de pre&ccedil;os de carros, incluindo regress&atilde;o linear, regress&atilde;o polinomial e gradient boosting. A escolha final foi a gradient boosting, que se mostrou mais adequada para os dados em quest&atilde;o. O algoritmo escolhido em quest&atilde;o foi o XGBRegressor, por ser um modelo eficaz e com diversos par&acirc;metros para melhorar sua precis&atilde;o.</p>
<h2><strong>Avalia&ccedil;&atilde;o do Modelo</strong></h2>
<p>As m&eacute;tricas escolhidas (MAE, MAPE e RMSE) s&atilde;o comuns em projetos de regress&atilde;o e fornecem informa&ccedil;&otilde;es importantes sobre a performance do modelo.&nbsp;</p>
<p>&nbsp;A &ecirc;nfase de performance ser&aacute; o menor valor do RMSE, esta m&eacute;trica &eacute; adequada para avaliar a robustez do modelo em rela&ccedil;&atilde;o a outliers, pois penaliza mais os erros maiores. A sua inten&ccedil;&atilde;o em verificar se mesmo ap&oacute;s o uso de t&eacute;cnicas, modelos e algoritmos resistentes a influ&ecirc;ncia de outliers o modelo ainda &eacute; afetado por eles &eacute; importante para garantir que o modelo seja capaz de fazer previs&otilde;es precisas e confi&aacute;veis em diferentes condi&ccedil;&otilde;es.</p>
<p>Os resultados da avalia&ccedil;&atilde;o indicaram que o modelo final, foi capaz de fazer previs&otilde;es de pre&ccedil;os de carros com boa precis&atilde;o. A m&eacute;trica RMSE apresentou um valor m&eacute;dio de 2.507,62 para o Modelo sem Outliers - IQR, indicando que a diferen&ccedil;a m&eacute;dia entre os pre&ccedil;os previstos e reais foi de 2.507,62 euros.</p>
<h2><strong>Testes dos Modelos</strong></h2>
<table border="1">
<tbody>
<tr>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Modelos de ML&quot;}">Modelos de ML</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Valor M&eacute;dio RMSE&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">Valor M&eacute;dio RMSE</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;BMW 135&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">BMW 135</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Varia&ccedil;&atilde;o do $ (+/-)&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">Varia&ccedil;&atilde;o do $ (+/-)</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Subaru Impreza&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">Subaru Impreza</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Varia&ccedil;&atilde;o do $ (+/-)&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">Varia&ccedil;&atilde;o do $ (+/-)</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Audi A3&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">Audi A3</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Varia&ccedil;&atilde;o do $ (+/-)&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">Varia&ccedil;&atilde;o do $ (+/-)</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Mercedes-Benz E 220&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">Mercedes-Benz E 220</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Varia&ccedil;&atilde;o do $ (+/-)&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">Varia&ccedil;&atilde;o do $ (+/-)</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Jaguar F-Type&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">Jaguar F-Type</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Varia&ccedil;&atilde;o do $ (+/-)&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">Varia&ccedil;&atilde;o do $ (+/-)</td>
</tr>
<tr>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Baseline&quot;}">Baseline</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;-&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">-</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:27990}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">27.990,00</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;-&quot;}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}">-</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:25999}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">25.999,00</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;-&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">-</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:4500}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">4.500,00</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;-&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">-</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:16750}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">16.750,00</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;-&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">-</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:198990}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">198.990,00</td>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;-&quot;}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">-</td>
</tr>
<tr>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Modelo com Outliers&quot;}">Modelo com Outliers</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:8110.20841722206}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">8.110,21</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:28503.611}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">28.503,61</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.018349803501250473}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">1,83%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:30621.117}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">30.621,12</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.17778056848340315}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">17,78%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:7700.662}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">7.700,66</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.7112582222222222}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">71,13%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:12692.144}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">12.692,14</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.24226005970149253}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-24,23%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:161437.92}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">161.437,92</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.18871340268355188}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-18,87%</td>
</tr>
<tr>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Modelo sem Outliers - IQR&quot;}">Modelo sem Outliers - IQR</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:2507.62299415074}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">2.507,62</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:30418.494}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">30.418,49</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.08676291532690242}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">8,68%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:18433.518}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">18.433,52</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.2909912688949575}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-29,10%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:5913.786}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">5.913,79</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.31417466666666666}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">31,42%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:15362.106}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">15.362,11</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.0828593432835821}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-8,29%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:33837.957}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">33.837,96</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.8299514699231118}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-83,00%</td>
</tr>
<tr>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Modelo sem Outliers - Devio-Padr&atilde;o&quot;}">Modelo sem Outliers - Devio-Padr&atilde;o</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:3351.70059878397}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">3.351,70</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:29944.037}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">29.944,04</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.06981196856020008}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">6,98%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:27381.281}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">27.381,28</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.05316669871918147}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">5,32%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:6261.934}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">6.261,93</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.39154088888888894}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">39,15%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:15342.159}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">15.342,16</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.0840502089552239}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-8,41%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:69370.31}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">69.370,31</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.6513879591939293}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-65,14%</td>
</tr>
<tr>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Modelo sem Outliers - Z-Score&quot;}">Modelo sem Outliers - Z-Score</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:3351.70059878397}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">3.351,70</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:29944.037}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">29.944,04</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.06981196856020008}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">6,98%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:27381.281}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">27.381,28</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.05316669871918147}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">5,32%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:6261.934}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">6.261,93</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.39154088888888894}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">39,15%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:15342.159}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">15.342,16</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.0840502089552239}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-8,41%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:69370.31}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">69.370,31</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.6513879591939293}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-65,14%</td>
</tr>
<tr>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Modelo sem Outliers - Isolation Forest&quot;}">Modelo sem Outliers - Isolation Forest</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:2643.26250664305}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">2.643,26</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:31516.283}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">31.516,28</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.12598367274026437}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">12,60%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:22157.656}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">22.157,66</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.1477496826801031}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-14,77%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:5409.309}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">5.409,31</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.2020686666666667}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">20,21%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:16423.943}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">16.423,94</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.019466089552238847}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-1,95%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:41129.29}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">41.129,29</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.7933097643097643}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-79,33%</td>
</tr>
<tr>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Modelo sem Outliers - DBSCAN&quot;}">Modelo sem Outliers - DBSCAN</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:3873.41191545385}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">3.873,41</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:30282.51}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">30.282,51</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.08190460878885311}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">8,19%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:32369.787}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">32.369,79</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.24503969383437826}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">24,50%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:6568.65}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">6.568,65</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.45969999999999994}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">45,97%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:13692.887}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">13.692,89</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.18251420895522386}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-18,25%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:109246.99}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">109.246,99</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.4509925624403236}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-45,10%</td>
</tr>
<tr>
<td data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Modelo sem Outliers - Local Outlier Factor&quot;}">Modelo sem Outliers - Local Outlier Factor</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:8004.27959620521}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">8.004,28</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:27745.283}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">27.745,28</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.00874301536262953}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-0,87%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:23969.154}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">23.969,15</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.07807400284626337}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-7,81%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:7576.81}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">7.576,81</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.6837355555555557}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">68,37%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:13106.637}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">13.106,64</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:-0.21751420895522383}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">-21,75%</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:215392.39}" data-sheets-numberformat="{&quot;1&quot;:2,&quot;2&quot;:&quot;#,##0.00&quot;,&quot;3&quot;:1}">215.392,39</td>
<td data-sheets-value="{&quot;1&quot;:3,&quot;3&quot;:0.08242821247298866}" data-sheets-numberformat="{&quot;1&quot;:3,&quot;2&quot;:&quot;0.00%&quot;,&quot;3&quot;:1}" data-sheets-formula="=(R[0]C[-1]-R3C[-1])/R3C[-1]">8,24%</td>
</tr>
</tbody>
</table>
<p>Na tabela apresentada, &eacute; poss&iacute;vel verificar os valores obtidos de previs&atilde;o de cada modelo e sua varia&ccedil;&atilde;o em rela&ccedil;&atilde;o ao valor real do ve&iacute;culo, al&eacute;m de seus valores de RMSE. Observa-se que quatro dos modelos sem outliers (IQR, Desvio-Padr&atilde;o, Z-Score e Isolation Forest) possuem uma boa previs&atilde;o para valores mais baixos, mas apresentam uma previs&atilde;o menos precisa para valores altos. J&aacute; o modelo DBSCAN tem uma boa previs&atilde;o para valores baixos e um desempenho mediano para valores altos.</p>
<p>&Eacute; interessante notar que o modelo com outliers e o melhor de forma geral modelo sem outliers (Local Outlier Factor) apresentaram desempenho semelhante nas vari&aacute;veis testadas. O que sugere a possibilidade de os outliers presentes n&atilde;o afetarem tanto o poder de predi&ccedil;&atilde;o do modelo. Isto pode ser examinado com novas abordagens na an&aacute;lise explorat&oacute;ria de dados e no feature engineering, bem como ajustar os par&acirc;metros do modelo e a etapa de pr&eacute;-processamento dos dados para aprimorar sua performance.</p>
<h2><strong>Considera&ccedil;&otilde;es Finais</strong></h2>
<p>O presente projeto tinha como objetivo criar um modelo de machine learning para predi&ccedil;&atilde;o de pre&ccedil;os, verificar o impacto de outliers e qual a melhor maneira de lidar. Pretende-se atualizar o projeto e melhorar seu poder de predi&ccedil;&atilde;o com um conjunto de dados maior para predi&ccedil;&atilde;o.</p>
<h2><strong>Pr&oacute;ximos passos</strong></h2>
<ul>
<li>Expandir o feature engineering</li>
<li>Explorar os dados considerados outliers com outras abordagens</li>
<li>Testar outros par&acirc;metros nas etapas de modelagem e pr&eacute;-processamento</li>
</ul>
