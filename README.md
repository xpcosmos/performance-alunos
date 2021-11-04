# Análise estatística de performance de alunos:

# 1 - Entendendo os dados

## 1.1 - Verificando as colunas 

Temos uma tabela que nos mostra as notas de testes de alguns alunos. Cada aluno dispõe de características com: gênero, raça, nível de educação dos responsáveis, se fez curso preparatório e se levou lanche para se alimentar durante o teste. Analisaremos as seguintes notas das seguintes matérias:

* Matemática
* Leitura/Interpretação
* Escrita/Redação

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gender</th>
      <th>race/ethnicity</th>
      <th>parental level of education</th>
      <th>lunch</th>
      <th>test preparation course</th>
      <th>math score</th>
      <th>reading score</th>
      <th>writing score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>female</td>
      <td>group B</td>
      <td>bachelor's degree</td>
      <td>standard</td>
      <td>none</td>
      <td>72</td>
      <td>72</td>
      <td>74</td>
    </tr>
    <tr>
      <th>1</th>
      <td>female</td>
      <td>group C</td>
      <td>some college</td>
      <td>standard</td>
      <td>completed</td>
      <td>69</td>
      <td>90</td>
      <td>88</td>
    </tr>
    <tr>
      <th>2</th>
      <td>female</td>
      <td>group B</td>
      <td>master's degree</td>
      <td>standard</td>
      <td>none</td>
      <td>90</td>
      <td>95</td>
      <td>93</td>
    </tr>
    <tr>
      <th>3</th>
      <td>male</td>
      <td>group A</td>
      <td>associate's degree</td>
      <td>free/reduced</td>
      <td>none</td>
      <td>47</td>
      <td>57</td>
      <td>44</td>
    </tr>
    <tr>
      <th>4</th>
      <td>male</td>
      <td>group C</td>
      <td>some college</td>
      <td>standard</td>
      <td>none</td>
      <td>76</td>
      <td>78</td>
      <td>75</td>
    </tr>
    <tr>
      <th>5</th>
      <td>female</td>
      <td>group B</td>
      <td>associate's degree</td>
      <td>standard</td>
      <td>none</td>
      <td>71</td>
      <td>83</td>
      <td>78</td>
    </tr>
    <tr>
      <th>6</th>
      <td>female</td>
      <td>group B</td>
      <td>some college</td>
      <td>standard</td>
      <td>completed</td>
      <td>88</td>
      <td>95</td>
      <td>92</td>
    </tr>
    <tr>
      <th>7</th>
      <td>male</td>
      <td>group B</td>
      <td>some college</td>
      <td>free/reduced</td>
      <td>none</td>
      <td>40</td>
      <td>43</td>
      <td>39</td>
    </tr>
    <tr>
      <th>8</th>
      <td>male</td>
      <td>group D</td>
      <td>high school</td>
      <td>free/reduced</td>
      <td>completed</td>
      <td>64</td>
      <td>64</td>
      <td>67</td>
    </tr>
    <tr>
      <th>9</th>
      <td>female</td>
      <td>group B</td>
      <td>high school</td>
      <td>free/reduced</td>
      <td>none</td>
      <td>38</td>
      <td>60</td>
      <td>50</td>
    </tr>
  </tbody>
</table>

## 1.2 - Encontrando dados faltantes:

<pre>&lt;class 'pandas.core.frame.DataFrame'&gt;
RangeIndex: 1000 entries, 0 to 999
Data columns (total 8 columns):
 #   Column                       Non-Null Count  Dtype 
---  ------                       --------------  ----- 
 0   gender                       1000 non-null   object
 1   race/ethnicity               1000 non-null   object
 2   parental level of education  1000 non-null   object
 3   lunch                        1000 non-null   object
 4   test preparation course      1000 non-null   object
 5   math score                   1000 non-null   int64 
 6   reading score                1000 non-null   int64 
 7   writing score                1000 non-null   int64 
dtypes: int64(3), object(5)
memory usage: 62.6+ KB
</pre>
 
 Verificando nosso dataset, não há dados faltantes, além de estarem corretamente tipados.
 
 # 2 Medidas de tendências 
 
 # 2.1 - Médias
 
 Vamos primeiro verficar as médias das notas e entender temos algum insight com isso!
 
 <pre>A média geral das notas é: 

math score       66.08
reading score    69.16
writing score    68.05

</pre>

Vamos verificar se há alguma diferença das notas entre gêneros:

<pre>
A média das notas entre homens é: 

math score       68.72
reading score    65.47
writing score    63.31

A média das notas entre mulheres é: 

math score       63.63
reading score    72.60
writing score    72.46

</pre>

Percebemos que temos uma maior média entre homens em matemática, mas em matérias como leitura e escrita, as mulheres tendem a se sair melhor. Vamos visualizar isso graficamente:

![grafico-1](https://github.com/xpcosmos/performance-alunos/blob/main/assets/grafico-1.png)
 
 Vamos analisar também a diferença das médias de quem consumiu lanches durante a prova e quem não consumiu:
 
 <pre>A média das notas de quem consumiu lanche é: 

math score       70.034109
reading score    71.654264
writing score    70.823256


A média das notas de quem não consumiu lanche é: 

math score       58.921127
reading score    64.653521
writing score    63.022535

</pre>

Visulizando isso graficamente:

![grafico-2](https://github.com/xpcosmos/performance-alunos/blob/main/assets/grafico-2.png)

Vamos agora visualizar a relação de nível de escolaridade dos pais dos alunos com suas notas:

<pre>A média das notas do pais com bacharelado é: 

math score       69.389831
reading score    73.000000
writing score    73.381356
media_geral      71.923729

A média das notas dos pais com superior incompleto é: 

math score       67.128319
reading score    69.460177
writing score    68.840708
media_geral      68.476401

A média das notas dos pais com mestrado é: 

math score       69.745763
reading score    75.372881
writing score    75.677966
media_geral      73.598870

A média das notas dos pais com técnico é: 

math score       67.882883
reading score    70.927928
writing score    69.896396
media_geral      69.569069

A média das notas dos pais com ensino médio é: 

math score       62.137755
reading score    64.704082
writing score    62.448980
media_geral      63.096939

A média das notas dos pais com ensino médio incompleto é: 

math score       63.497207
reading score    66.938547
writing score    64.888268
media_geral      65.108007

</pre>

Visualizando isso gráficamente:

![grafico3](https://github.com/xpcosmos/performance-alunos/blob/main/assets/grafico-3.png)
