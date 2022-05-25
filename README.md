# data-fusion2022-open-solution
Открытое решение для [Data Fusion Contest 2022](https://ods.ai/tracks/data-fusion-2022-competitions)

* Результаты на публичном лидерборде 

| Task | ROC-AUC | R1 | MRR@100 | Precision@100 | Current place (15.05) |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Education | 0,788535 |  |  |  | ***31*** |
| Puzzle |  | 0,0425695056 | 0,0235027126 | 0,2255448555 | ***20*** |
| Matching |  |  | Queued |  | ```¯\_(ツ)_/¯``` |

* [education_submit](submissions/education_submit.csv) - файл для отправки в задачу Education
* [puzzle_submit](submissions/puzzle_submit.csv) - файл для отправки в задачу Puzzle. Считался 30 минут
* ~~[matching_submit](submissions/matching_submit) - папка с архивом для отправки в задачу Matching~~

### Short description:
Решение основано на подходе из [Catboost baseline](https://ods.ai/tracks/data-fusion-2022-competitions/competitions/data-fusion2022-main-challenge/Baselines). Оно использует нейросети и градиентный бустинг. 
* [data-preprocessing](data-preprocessing.ipynb) - предварительная обработка данных, уменьшение объёма используемой памяти
* [making-embeddings](making-embeddings.ipynb) - создание признаков на основе совершённых транзакций и посещённых страниц
* [fitting-lifestream](fitting-lifestream.ipynb) - обучение pytorch-lifestream, получение дополнительного набора эмбеддингов
* [education-solution](education-solution.ipynb) - обучение catboost, получение предсказаний для задачи Education
* [puzzle-solution](puzzle-solution.ipynb) - обучение catboost, получение предсказаний для задачи Puzzle

### Requirements:
* Решение использует библиотеку [pytorch-lifestream](https://github.com/dllllb/pytorch-lifestream). Для её работы необходим Python 3.8 или новее. Используемая [версия](pytorch-lifestream-main)  находится в репозитории. ```!pip install ./pytorch-lifestream-main```
* [dockerfile](dockerfile) - файл для построения docker image c Python 3.8 и [необходимыми библиотеками](requirements.txt)
* Для запуска локально: 32Gb Ram, GPU
