The Hedgehog & the Porcupine: Expressive Linear Attentions with
Softmax Mimicry

https://arxiv.org/pdf/2402.04347.pdf

Likekly to be a replacement to softmax attention 

![Screenshot from 2024-02-09 16-00-03](https://github.com/vyomakesh09/notes/assets/54256947/913d2ba7-7d7d-4c92-96d8-89b3bd7e8ae2)


from quadratic to linear

linear in-context length doing this to a pre-trained model -0000poo( Llama )

" Linear attentions have shown potential for improving Transformer efficiency, reducing attention's quadratic complexity to linear in sequence length " 

![Screenshot from 2024-02-09 16-00-24](https://github.com/vyomakesh09/notes/assets/54256947/4107e2a4-b541-40c2-b0a4-7621b83aba74)


![Screenshot from 2024-02-09 16-00-35](https://github.com/vyomakesh09/notes/assets/54256947/aaeef21c-f92c-4186-a336-6b9f5f4b42f8)


Holds promise for 
    - Training linear Transformers from scratch 
    - 'Finetuned-conversion' of taks-specific Transformers into linear versions that recover task performance and 
    - 'Pretained-conversion' of Transformers such as LLMs into linear versions finetunable on downstream ta sks 

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

![Screenshot from 2024-02-09 16-11-18](https://github.com/vyomakesh09/notes/assets/54256947/d4e497c5-e2d3-4a56-b4e3-1b12d124f037)

![Screenshot from 2024-02-09 16-11-09](https://github.com/vyomakesh09/notes/assets/54256947/a82b97b5-11a2-42b7-a322-c72f7a8e28bd)

Conclusion 
    we study why prior linear attentions underperform softmax attention and identify two missing properties 
    - ability to capture low entropy or spiky attention maps 
    - to be monotonic wrt the underlying query-key dot products 

Hedgehog -> competitive performance with softmax-based attention in 

    - training from scratch 
    - finetuned-conversion and 
    - pretrained conversion 



HedgeHog Implementation deatails

    -> mechanics for hedge hog feature map 
        - numerical stability 
        - negaiton mapping 
    -> hedgehog feature map and model architecture
    


    -> hedgehog distillation and finetuning  ( obtain linear attention transformers )
        
        - trainning-from-scratch:
            + insert HH MLP for each query and key  projections of randomly initialized transformers 
        - finetuned/ pretrained conversions:
            + attention distillation 
                to compute soft cross-entropy or KL divergence bw the 'predicted' linear attention weights and 'ground-truth' softmax attention weigths 
            + original parameter finetuing
                unfreeze all model weights and train with a standard task-specific loss function 

                