CodeIt Self Improving LLM with prioritized hindsight replay 

https://arxiv.org/pdf/2402.04858.pdf


sampling -> hindsight relabeling <- learning 

Benchmarks
	Abstraction and Reasoning Corpus ( ARC ) 


Methods 
	Programming language 
		domian-specific language ( opensource DSL ) 
	
	Grid manipulation funcitons ( vmirror or hmirror {which mirrors the gird along the vertical or horizontal axis } )

	Policy ( pretrained encored-decoder LLM )

	CodeT5+ - 220million parameter model and its default tokenizer 
	
	Grid representation [x, y]
	
	The code Iteration Algo
		# Initializaion 
		# Sampling and hindsight relabeling 
			# Q theta
			# search set ( ARC eval )
			# ARC train set
		# Learning 
	Expert Iteration ( ExIt ) 
	DreamCoder  
	# temperature t = 0.95 
	# sample n p = 24  

This method iterates between 	
	# program sampling and hindsight relabeling and,
	# learning from prioritized experience replay  
