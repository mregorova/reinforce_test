### Запуск
Заданию уровня 1 соответствует ноутбук reinforce.ipynb, заданию уровня 2 соответствует ноутбук reinforce2.ipynb.
Можно просто запустить все ячейки последовательно.

### LEVEl 1
В ходе выполнения задания использовала HuggingFaceTB/SmolLM2-135M-Instruct, поверх обучила reward модель на парах esfrankel17/HelpSteer2_binarized. Затем реализовала алгоритм reinforce из статьи, результаты можно посмотреть в reinforce.ipynb. 

Некоторые результаты можно посмотреть здесь: https://wandb.ai/mregorova-mipt/huggingface?nw=nwusermregorova

Параметр avg_reward	показал высокий рост: 1.67465 на train и 1.88537 на eval. 

### LEVEL 2
Чтобы предсказать именно распределение, а не число, воспользуемся формулой:
$$
\boxed{ 
\mathcal{L}_{\text{RM}} = -\log \left( \sum\limits_{i=2}^{10} \sum\limits_{j=1}^{i-1} w_i \cdot l_j \right) 
}
$$
