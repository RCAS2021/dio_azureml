# dio_azureml
## Implantação do modelo
1. Tendo utilizado o aprendizado de máquina automatizado do Azure para treinar os modelos, selecionei o job realizado.
2. Em overview, selecionei o nome do algoritmo em Best Model Summary.
3. Em seguida, selecionei a aba de métricas e selecionei os gráficos residuals e pedicted_true e revisei-os.
4. Retornando para a aba do Best Model Summary, selecionei a opção de implantar o modelo.
5. Selecionei a opção de Web Service e coloquei as seguintes configurações:
  *Name: predict-rentals
  *Description: Predict cycle rentals
  *Compute type: Azure Container Instance
  *Enable authentication: Selected
6. Esperei a implantação do modelo.

## Testando o serviço implantado
1. No menu lateral esquerdo, selecionei a aba de Pontos de Extremidade.
2. Abri o ponto de extremidade predict-rentals.
3. No ponto de extremidade predict-rentals, selecionei a aba "Testar".
4. Em "Inserir dados para teste de ponto de extremidade", mudei o json de template por esse:
```JSON
{
   "Inputs": { 
     "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]    
   },   
   "GlobalParameters": 1.0
}
```
5. Cliquei no botão "Testar".
6. Visualizei o resultado do teste.

## Limpando os dados
### Limpando os pontos de extremidade
1. No Azure Machine Learning Studio, selecionei a aba "Pontos de Extremidade".
2. Selecionei o ponto de extremidade "predict-rentals".
3. Selecionei a opção "Excluir" e confirmei.
### Limpando o workspace
1. Entrei no portal Azure
2. Selecionei a aba "Resource groups" no menu lateral esquerdo.
3. Selecionei o Resource Group que havia criado.
4. Cliquei na opção "Delete resource group".
5. Na direita, digiteo o nome do resource group e cliquei em delete.
6. Confirmei o delete.

Fim.
