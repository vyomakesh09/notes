CodeIt Self Improving LLM with prioritized hindsight replay 

https://arxiv.org/pdf/2402.04858.pdf

![Screenshot from 2024-02-08 17-28-58](https://github.com/vyomakesh09/notes/assets/54256947/36f6df8e-ec42-4db2-806e-a1837c810bff)


sampling -> hindsight relabeling <- learning 

![Screenshot from 2024-02-08 16-53-24](https://github.com/vyomakesh09/notes/assets/54256947/19639de8-e8a3-455d-a8b1-0a3f6b8b484e)

![Screenshot from 2024-02-08 17-29-09](https://github.com/vyomakesh09/notes/assets/54256947/b24abc3d-22fd-4dc9-8529-2c6f08f18b53)

![Screenshot from 2024-02-08 16-53-49](https://github.com/vyomakesh09/notes/assets/54256947/d67e6e9a-2d27-47e8-b092-eb6e742f0fb6)


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
  			![Screenshot from 2024-02-08 16-53-11](https://github.com/vyomakesh09/notes/assets/54256947/bbcb63d0-3a49-49e1-bd3e-43a45177a492)

	Expert Iteration ( ExIt ) 
	DreamCoder  
	# temperature t = 0.95 
	# sample n p = 24  

This method iterates between 	
	# program sampling and hindsight relabeling and,
	# learning from prioritized experience replay  
