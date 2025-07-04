### Запуск
Заданию уровня 1 соответствует ноутбук reinforce.ipynb, заданию уровня 2 соответствует ноутбук reinforce2.ipynb.
Можно просто запустить все ячейки последовательно.

### LEVEl 1
В ходе выполнения задания использовала HuggingFaceTB/SmolLM2-135M-Instruct, поверх обучила reward модель на парах esfrankel17/HelpSteer2_binarized. Затем реализовала алгоритм reinforce из статьи, результаты можно посмотреть в reinforce.ipynb. 

Некоторые результаты можно посмотреть здесь: https://wandb.ai/mregorova-mipt/huggingface?nw=nwusermregorova

Параметр avg_reward	показал высокий рост: 1.67 на train и 1.88 на eval. Accuracy 0.63.

### LEVEL 2
Чтобы предсказать именно распределение, а не число, воспользуемся формулой:

![formula](https://latex.codecogs.com/svg.latex?%5Cmathcal%7BL%7D_%7B%5Ctext%7BRM%7D%7D%20%3D%20-%5Clog%20%5Cleft%28%20%5Csum_%7Bi%3D2%7D%5E%7B10%7D%20%5Csum_%7Bj%3D1%7D%5E%7Bi-1%7D%20w_i%20%5Ccdot%20l_j%20%5Cright%29)

Далее я обучила модель на двух эпохах с результатом на валидации accuracy 0.49 и 0.63 соответственно. Благодаря добавлению эпохи ощутим прогресс, однако точность всё ещё довольно низкая. После повторного обучения reinforce получаем avg_reward 5.96 на train и 5.65 на test. Само по себе обучение распределения выгодно тем, что для распределения мы можем посчитать статистические величины (например, дисперсию) и сделать дополнительные выводы о точности предсказаний модели.

Хоть в целом награда в ходе обучения модели выросла, другие метрики, такие как avg_advantage -0.63 заставляют задуматься об ухудшении качества модели. Для улучшения инференса модели я бы посоветовала больше обучить reward_model и провести эксперименты с гиперпараметрами. Возможно, также стоит обратить внимание на используемый датасет и расширить его, дополнив аугментациями и корнеркейсами. Без этого нельзя сказать, что качество сильно улучшилось в ходе эксперимента.
