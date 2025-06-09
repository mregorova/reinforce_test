### Запуск
Заданию уровня 1 соответствует ноутбук reinforce.ipynb, заданию уровня 2 соответствует ноутбук reinforce2.ipynb.
Можно просто запустить все ячейки последовательно.

### LEVEl 1
В ходе выполнения задания использовала HuggingFaceTB/SmolLM2-135M-Instruct, поверх обучила reward модель на парах esfrankel17/HelpSteer2_binarized. Затем реализовала алгоритм reinforce из статьи, результаты можно посмотреть в reinforce.ipynb. 

Некоторые результаты можно посмотреть здесь: https://wandb.ai/mregorova-mipt/huggingface?nw=nwusermregorova

Параметр avg_reward	показал высокий рост: 1.67465 на train и 1.88537 на eval. 

### LEVEL 2
Чтобы предсказать именно распределение, а не число, воспользуемся формулой:
<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=%5Cmathcal%7BL%7D_%7B%5Ctext%7BRM%7D%7D%20%3D%20-%5Clog%20%5Cleft(%20%5Csum_%7Bi%3D2%7D%5E%7B10%7D%20%5Csum_%7Bj%3D1%7D%5E%7Bi-1%7D%20w_i%20%5Ccdot%20l_j%20%5Cright)%20" alt="Loss Function">
</p>
