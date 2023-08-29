# programacao_linear
### 1.1) A questão apresentada segue Hillier & Lieberman, Introdução à Pesquisa Operacional, 9a ed., capítulo 3, página 41.
    
##### A CONFEDERAÇÃO MERIDIONAL DE KIBUTZIM é um grupo de três kibutzim *(comunidades agrícolas coletivas em Israel)*. O planejamento geral para esses grupos é feito em seu Centro Técnico de Coordenação. Esse escritório está planejando atualmente a produção agrícola para o próximo ano. A produção agrícola de cada kibutz é limitada tanto pela quantidade de área irrigável disponível como pela quantidade de água alocada para a irrigação pelo Comissariado de Recursos Hídricos *(um órgão governamental)*. Esses dados são fornecidos na Tabela 3.8. Entre as plantações adequadas para essa região encontram-se beterraba, algodão e sorgo e são estas que estão sendo consideradas para o próximo período. Essas plantações diferem basicamente nos respectivos retornos líquidos esperados e consumo de água. Além disso, o Ministério de Agricultura tem uma cota máxima para a área total que pode ser dedicada a cada uma dessas plantações pela Confederação Meridional de Kibutzim, conforme ilustrado na Tabela 3.9. Em razão da limitada disponibilidade de água para irrigação, a Confederação Meridional de Kibutzim não será capaz de usar toda sua área irrigável para plantação de culturas na próxima temporada. Para garantir equilíbrio entre os três kibutzim, foi acordado que cada um deles vai plantar a mesma proporção de sua área irrigável. Por exemplo, se o kibutz 1 plantar 200 de seus 400 acres disponíveis, então o kibutz 2 terá de plantar 300 de seus 600 acres, ao passo que o kibutz 3 plantaria 150 de seus 300 acres. Entretanto, qualquer combinação das plantações pode ser cultivada no kibutzim. A tarefa que o Centro Técnico de Coordenação deve enfrentar é planejar quantos acres devem ser dedicados a cada plantação no respectivo kibutzim satisfazendo as dadas restrições. O objetivo é maximizar o retomo líquido total para a Confederação Meridional do Kibutzim como um todo.    
    

##### Tabela 3.8: Dados de Recursos para a Confederação Meridional de Kibutzim

 **Kibutzim** | **Terra Utilizável (acres)** | **Locação de Água (acres pés)** 
:------------:|:----------------------------:|:-------------------------------:
 **1**        | 400                          | 600                             
 **2**        | 600                          | 800                             
 **3**        | 300                          | 375                             
    
    
#### Tabela 3.9: Dados de Plantações para a Confederação Meridional de Kibutzim
    
 **Plantação** | **Cota Máxima (acres)** | **Consumo de Água (acres pés/acres)** | **Retorno Líquido (US$/acre)** 
:-------------:|:-----------------------:|:-------------------------------------:|:------------------------------:
 **Beterraba** | 600                     | 3                                     | 1000                           
 **Algodão**   | 500                     | 2                                     | 750                            
 **Sorgo**     | 325                     | 1                                     | 250                            

### 1.2) Definição Matemática do Problema

##### 1.2.1) Variáveis de Decisão

- $b_{1}$: área plantada com beterraba no kibutz 1 (acres)
- $a_{1}$: área plantada com algodão no kibutz 1 (acres)
- $s_{1}$: área plantada com sorgo no kibutz 1 (acres)
- $b_{2}$: área plantada com beterraba no kibutz 2 (acres)
- $a_{2}$: área plantada com algodão no kibutz 2 (acres)
- $s_{2}$: área plantada com sorgo no kibutz 2 (acres)
- $b_{3}$: área plantada com beterraba no kibutz 3 (acres)
- $a_{3}$: área plantada com algodão no kibutz 3 (acres)
- $s_{3}$: área plantada com sorgo no kibutz 3 (acres)

##### 1.2.2) Função Objetivo

- $\max Z = 1000 \sum^3_1 b_{i} + 750 \sum^3_1 a_{i} + 250 \sum^3_1 s_{i}$

##### 1.2.3) Restrições

Terra utilizável:
- $b_{1} + a_{1} + s_{1} \leq 400$
- $b_{2} + a_{2} + s_{2} \leq 600$
- $b_{3} + a_{3} + s_{3} \leq 300$

Alocação de água:
- $3b_{1} + 2a_{1} + s_{1} \leq 600$
- $3b_{2} + 2a_{2} + s_{2} \leq 800$
- $3b_{3} + 2a_{3} + s_{3} \leq 375$

Área total para cada plantação:
- $b_{1} + b_{2} + b_{3} \leq 600$
- $a_{1} + a_{2} + a_{3} \leq 500$
- $s_{1} + s_{2} + s_{3} \leq 325$

Proporcionalidade entre os kibutzim:     
    
$ \frac{b_{1} + a_{1} + s_{1}}{400} = \frac{b_{2} + a_{2} + s_{2}}{600} = \frac{a_{3} + s_{3} + b_{3}}{300} $
    
As igualdades abaixo tornam-se as três restrições a seguir:

 - $3(b_{1} + a_{1} + s_{1}) - 2(b_{2} + a_{2} + s_{2}) = 0$
 - $4(b_{1} + a_{1} + s_{1}) - 3(b_{3} + a_{3} + s_{3}) = 0$
 - $2(b_{2} + a_{2} + s_{2}) - (b_{3} + a_{3} + s_{3}) = 0$


Não-negatividade:
- $b_{1}, a_{1}, s_{1}, b_{2}, a_{2}, s_{2}, b_{3}, a_{3}, s_{3} \geq 0$
