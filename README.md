# Azure Inteligência Artificial(IA) - Configuração do modelo e padrão de leitura dos dados
Objetivo é configurar o serviço de Machine Learning para ler a base de dados e apresentar os resultado.

### Ferramentas utilizadas:

- Azure: https://azure.microsoft.com/pt-br/get-started/azure-portal/
- Azure ML: https://ml.azure.com/
- Serviço da Azure: ``` Azure Machine Learning ```

### Pontos Importantes:

 - Caso esteja realizando apenas um prática de estudo, no final excluir tudo que foi construído nesse laboratório. Desta forma, minimiza o risco de ser cobrado algum valor. Lembre-se você está em um ambiente real de produção.
 - Links uteis com detalhamento:
   
    * https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/02-content-safety.html
      
    * https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html

### Resumo (Passo-a-passo): Configuração Machine Learning:

 - Ir para "Go to Resouce"
 - Clicar em "Launch studio"
 - Abrirá uma pagina nova então selecionar o workspace criando anteriormente
 - Clicar no botão "Automated ML"
 - Selecionar o item "New automated job"
 - Preencher "Basic setting"
 - Preencher "Task type & data"
 -  

   
### Detalhamento (Passo-a-passo): Configuração Machine Learning

01 - Clicar no botão no final da tela: ``` Go to Resouce ```

![image](https://github.com/user-attachments/assets/701b2239-10e1-4b20-9c28-f1e2c9a13bf7)

02 - Clicar no botão ``` Launch studio ```

![image](https://github.com/user-attachments/assets/e7d5dff3-c0eb-47bc-8b6f-9da007117602)

03 - Então, abrirá uma nova pagina com endereço: https://ml.azure.com/. Pode acontece de abrir e não está logado. Então precisa fazer o login. Após fazer o login, clicar em "Automated ML"

Perceba que o Workspace que você criou no passo anterior (https://github.com/WanderBernardo/AzureIA_MachineLearning_Workspace), já aparece.

![image](https://github.com/user-attachments/assets/b2f6dfba-983d-4d90-a717-fcd799fe4333)

Caso não apareça, então, clicar em "All workspaces" e selecionar o Workspaces que foi criado anteriormente.

04 - Selecionar a item: ``` New Automated job ```

![image](https://github.com/user-attachments/assets/72e0c092-6cfc-4e96-ac12-fbf0b052eeba)

05 - A partir de agora, preencher conforme o padrão solicitado. Pois estamos executando exercicio disponibilizado pela microsoft. Mas na vida real, incluir os dados compativel com modelo que estão desenvolvendo. Pós preenchimento clicar em ``` Next ```
   * Job name: mslearn-bike-automl
   * Experiment name: Padrão do sistema, não alterar.
   * New experiment name: mslearn-bike-rental
   * Description: Automated machine learning for bike rental prediction
   * Tag: none

![image](https://github.com/user-attachments/assets/ae7f491e-4592-4f6e-b368-6b4784bff3a8)

06 - Preencher com os dados ``` Task type & data ```
   * Select task type: aqui que tipo de tarefa será realizado: uma regressão, classificação, entre outras. No nosso caso, será uma ``` Regressão ```
     
![image](https://github.com/user-attachments/assets/2c261d31-77bc-41e6-b00d-763411e1439a)

07 - Na parte ``` Select data ``` , clicar no botão ``` Create ``` . Então, vai abrir uma tela para preencher, após preenchimento clicar em: ``` Next ```
   * Data type:
      * Name: Não incluir dados sensiveis ou confidencias. No nosso modelo será: bike-rentals
      * Description: Historic bike rental data
      * Type: Table (mltable) - Aqui tem link para mais informações para melhor o entendimento do tipo de dados você consegue trabalhar. No nosso caso estamos usando um CSV.
        
   ![image](https://github.com/user-attachments/assets/7c03ac6d-b128-4b80-88f2-da4840b66900)

   * Data source: Selecionar a opção ``` From local files ``` depois ``` Next ``` 
     
   ![image](https://github.com/user-attachments/assets/790c3451-1509-4dab-b71d-dce6ffd8bd08)

   * Nesta proxima tela mantém a configuração padrão em seguida ``` Next ```
      * Datastore type: Azure Blob Storage
      * Name: workspaceblobstore
   
     ![image](https://github.com/user-attachments/assets/4b161107-bcb6-4d0d-b1e3-b9b306ca8a09)

08 - Neste próximo passo, será necessário baixar o arquivo de exemplo que vamos usar e descompactar (em anexo). Link  para baixar: https://aka.ms/bike-rentals

![image](https://github.com/user-attachments/assets/dfb2bc53-9273-45db-9955-fc36aa9aa74f)

09 - Então deve fazer o upload do arquivo e ``` Next ```

![image](https://github.com/user-attachments/assets/e41a452c-c1a9-41d8-9c2d-fdc395e51a31)

10 - Agora, o neste próximo passo o sistema vai validar as configurações. Quando concluir vai mostrar a tela com resumo das configurações e o botão create ativo. Click no bortão e aguardar concluir. Não sair da tela até concluir.

![image](https://github.com/user-attachments/assets/7d251609-0590-42ff-a794-84a715e03672)

11 - Vai apresentar uma mensagem de sucesso na parte superior e em seguida, selecionar a opção criado, pois foi o que você criou nos passos anterior e ``` Next ```

![image](https://github.com/user-attachments/assets/4b185037-9307-4bb2-82f2-097535abe034)

12 - Agora neste passo, a configuração necessaria é selecionar Target column: ``` rentals (Integer) ```

E abaixo do campo acima selecionar e ajustar: ``` View additional configuration settings ```

![image](https://github.com/user-attachments/assets/558d35a7-877e-4a2b-a6d3-e7604095c75d)

Então, vai abrir uma nova tela onde vai precisar desmarcar as 3 opções:
   * Explain best model
   * Enable ensemble stacking
   * Use all supported models
E na opção: Allowed models, selecionar "RandomForest" e "LightGBM"

![image](https://github.com/user-attachments/assets/c2662d00-c7db-4b11-a43c-c223d7c26895)

Reforçando, que essa configuração é para o nosso exemplo. Cada caso, precisa ser analisado qual configuração será necessário.

13 - Agora, nessa parte da configuração "Limits", irá configurar o tempo limite timeout, máximo de avaliação etc. Basicamente, são os paramêtros para indicar o limite e tempo de pesquisas vai ser realizado para apresentar o resultado.  

![image](https://github.com/user-attachments/assets/9b6dfdaa-b43a-4e93-8b4e-9d03626d74d1)

14 - Neste parte, Validate and test, preencher conforme abaixo e ``` Next ```
   * Validation type: Train-validation split
   * Percentage validation of data: 10
   * Test data: None

![image](https://github.com/user-attachments/assets/fe3693cb-5fdb-4258-a46b-d2698fe59fd7)

15 - Agora, selecionar as configuração o desempenho que gostaria dedicar para realizar essa tarefa. Mantém a configuração padrão. Então, ``` Next ```

![image](https://github.com/user-attachments/assets/3c42c7e3-f066-47d2-bc69-a5352f27b304)

15 - Vai apresentar uma tela com resumo das configurações realizadas e clicar em  ``` Submit training job ```

![image](https://github.com/user-attachments/assets/815ebc1a-cdd5-4832-a044-d96ebd143cbb)

Não saia da tela. Aguardar concluir:

![image](https://github.com/user-attachments/assets/cb740a01-b9ac-48ad-b1c8-60754a13a452)

Status de concluído:

![image](https://github.com/user-attachments/assets/05276488-a041-48bd-8313-d2f30ddc3da8)

### Próximo Passo

https://github.com/WanderBernardo/AzureIA_MachineLearning_AnalysisTest
