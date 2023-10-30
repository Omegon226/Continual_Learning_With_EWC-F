![image](https://github.com/Omegon226/Continual_Learning_With_EWC-F/assets/69383841/1ed7a8e6-f150-4195-b7d1-33a5ce06491c)

# Что находится в данном репозитории?

В перую очередь я хочу вырозить большую благодарность **db434** за хоршо разработанный код для регуляризации EWC-F (Elastic Weights Consolidation, с использованиаем метода диагоналей Фишера). В данной работе этот метод был доработан и модифицирован для большего удобства пользованием. Если вы уже знакомы с EWC, то увас может появится вопрос, почему я использую абревиатуру EWC-F. Это связано с тем, что существуют другие имплементации EWC, которые не используют диагоналй матриц Фишера для определения важности весов нейронной сети. Более подробно это расписано здесь: [Научная статья из eLIBRARY](https://www.elibrary.ru/download/elibrary_44743628_11697060.pdf)

Данная работа показывает эффективность метода EWC-F для дообучения (постобучения) нейронных сетей. Тогда как обычное обучение не делает никаких расчётов, чтобы предотвратить забывание старых знаний, а L2 регуляризация приходить не к оптимальному минимому - EWC-F позволяет минимальным образом повредить ранее полученный опыть нейронной сети, что позволяет минимизировать проблему критического забывания

<p align="center">
  <img src="https://github.com/Omegon226/Continual_Learning_With_EWC-F/assets/69383841/d305d116-1682-4101-a20d-c570e805b529" alt="EWC-F img" width="600" height="600"/>
</p>

В работе был поставлен и проведён эксперемент, который позволяет сравнить L2 регуляризацию и EWC-F при дообучении модели предсказания курса закрытия Биткойна. В ноутбуке происходит анализ и обработка данных, создание выборок для тестирования и обучения рекурентной нейронной сети для прогнозирования временных рядов, создаётся сама модель, полученная модель тестируется и после этого дообучается два раза с помощью только L2 и только с EWC-F (после дообучения происходит тестирование и сохранение результатов). В конце расчётов производится подведение итогов эксперемента
