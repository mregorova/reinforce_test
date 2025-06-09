### LEVEl 1
В ходе выполнения задания использовала HuggingFaceTB/SmolLM2-135M-Instruct, поверх обучила reward модель на парах esfrankel17/HelpSteer2_binarized. Затем реализовала алгоритм reinforce из статьи, результаты можно посмотреть в reinforce.py. 

Некоторые результаты можно посмотреть здесь: https://wandb.ai/mregorova-mipt/huggingface?nw=nwusermregorova

Параметр avg_reward	показал высокий рост: 1.67465 на train и 1.88537 на eval. 
