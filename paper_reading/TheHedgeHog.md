The Hedgehog & the Porcupine: Expressive Linear Attentions with
Softmax Mimicry

https://arxiv.org/pdf/2402.04347.pdf

Likekly to be a replacement to softmax attention 

from quadratic to linear

linear in-context length doing this to a pre-trained model ( Llama )

" Linear attentions have shown potential for improving Transformer efficiency, reducing attention's quadratic complexity to linear in sequence length " 

Holds promise for 
    - Training linear Transformers from scratch 
    - 'Finetuned-conversion' of taks-specific Transformers into linear versions that recover task performance and 
    - 'Pretained-conversion' of Transformers such as LLMs into linear versions finetunable on downstream tasks 

Performance Gap: " linear attention often under-performs standard softmax attention in quality " 

    To close this gap: " Low-entropy ( or spiky ) weights and dot-product monotonicity " 

HEDGEDOG, A LEARNABLE LINEAR ATTENTION THAT RETAINS THE SPIKY AND MONOTONIC PROPERTIES OF SOFTMAX ATTENTION WHILE MAINTAINING LINEAR COMPLEXITY

    - Uses trainable MLPs to produce attention weights mimicking softmax attention 

Linear attention reduce attention's time and space complexity 
from O ( n ** 2 d ) to O ( n d d^ ) 
    n: sequence lenght
    d: head dimension 
    d^: feature map dimension 


Training-from-scratch 
Finetuned-convesion 
Pretained-conversion 

Low-entropy "spikyness"
Dot-product monotonicity 

Models used 
    Llama-2 7B fintuning with low-rank adapters ( LoRA )
    GPT-2 125M - outperformes TR2 ( Tranformer to RNN ), H3 and Hyena
    BERT-base fintuned on GLUE
    ViT-B/16 trained on ImageNet-1k



Datasets used
    WikiText-103


Learnable LInear Attentions for mimicking softmax
    Spiky MLP feature map 
    Attention weigth distillation loss 

Benchamarking Hedgehog for Expressivity and Efficiency 

Conclusion 
    we study why prior linear attentions underperform softmax attention and identify two missing properties 
    - ability to capture low entropy or spiky attention maps 
    - to be monotonic wrt the underlying query-key dot products 

Hedgehog -> competitive performance with softmax-based attention in 

    - training from scratch 
    - finetuned-conversion and 
    - pretrained conversion 