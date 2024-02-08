- CodeIt Self Improving LLM with prioritized hindsight replay 

https://arxiv.org/pdf/2402.04858.pdf

- sampling -> hindsight relabeling <- learning 

Benchmarks
	- Abstraction and Reasoning Corpus ( ARC ) 


Methods 
	- domian-specific language ( opensource DSL ) ( Programming language )
		- grid manipulation funcitons ( vmirror or hmirror {which mirrors the gird 
						along the vertical or horizontal axis } )
	- policy ( pretrained encored-decoder LLM ) ( CodeT5+ 220million parameter model and its default tokenizer ) 
	- grid representation [x, y]
	- The code Iteration Algo
		- Initializaion 
		- sampling and hindsight relabeling 
			- Q theta
			- search set ( ARC eval )
			- ARC train set
		- Learning 
	- Expert Iteration ( ExIt ) 
	- DreamCoder  
	- temperature t = 0.95 
	- sample n p = 24  

This method iterates between 	
	- 1) program sampling and hindsight relabeling and,
	- 2) learning from prioritized experience replay  
