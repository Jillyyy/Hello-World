- 数据集（北京地区二手房数据）说明

  训练集Size 255,080 * 23

  测试集Size 63,771 * 22

  特征说明
  -  **Lng** and **Lat** coordinates, using the **BD09** protocol
  -  **Cid**: community id 
  -  **tradeTime**: the time of transaction 
  -  **DOM**: active days on market.Know more in https://en.wikipedia.org/wiki/Days_on_market 
  -  **followers**: the number of people follow the transaction
  -  **price**: the average price by square 
  -  **square**: the square of house 
  -  **livingRoom**: the number of living room 
  -  **drawingRoom**: the number of drawing room 
  -  **kitchen**: the number of kitchen 
  -  **bathroom** the number of bathroom 
  -  **floor**: the height of the house
  -  **buildingType**: including tower( 1 ) , bungalow( 2 )，combination of plate and tower( 3 ), plate( 4 )
  -  **constructionTime**: the time of construction 
  -  **renovationCondition**: including other( 1 ), rough( 2 ),Simplicity( 3 ), hardcover( 4 ) 
  -  **buildingStructure**: including unknow( 1 ), mixed( 2 ), brick and wood( 3 ), brick and concrete( 4 ),steel( 5 ) and steel-concrete composite ( 6 )
  -  **ladderRatio**: the proportion between number of residents on the same floor and number of elevator of ladder. It describes how many ladders a resident have on average
  -  **elevator** have ( 1 ) or not have elevator( 0 ) 
  -  **fiveYearsProperty**: if the owner have the property for less than 5 years

  注：1）csv文件读取如遇编解码错误，请添加参数encoding='utf-8'

  ​        2)   price单位：万

- 评价指标（Metrics）

  - MSE : $MSE(y,\hat{y})=\frac{1}{N_{samples}}\sum_{i=0}^{N-1}(y_i-\hat{y}_i)^2$
  - MedAE : $MedAE(y,\hat{y})=median(|y_1-\hat{y}_1|,\dots,|y_n-\hat{y}_n|)$

  - R2 Score: $R^2(y,\hat{y})=1-\frac{\sum_{i=0}^{N_{samples}-1}(y_i-\hat{y}_i)^2}{\sum_{i=0}^{N_{samples}-1}(y_i-\bar{y})^2}$
    - 说明：MedAE，对离群点比较鲁棒。R2score，提供了模型对未来样本的预测好坏的度量

- 作业提交格式要求
文件名：prediction.txt
每一行为预测价格，顺序按test.csv，共63,771行。
示例：
```
10245
43563
...
54636
```
结果提交在canvas上。
-  评分
对每位同学的prediction.txt计算三个评价指标，得到三个rank；每一个rank按正态分布评分，最终得分为三个rank得分的均值。
