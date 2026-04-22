# Makefile for Deep Neural Network Projects

NOTEBOOKS = neural_network_basics_forward_pass.ipynb \
activation_functions_implementation.ipynb \
forward_and_backpropagation.ipynb \
loss_functions_analysis.ipynb \
gradient_descent_optimization.ipynb \
model_training_and_evaluation.ipynb \
end_to_end_neural_network_pipeline.ipynb

# Run Jupyter Notebook
run:
	jupyter notebook

# Convert all notebooks to Python scripts
convert:
	for nb in $(NOTEBOOKS); do \
		jupyter nbconvert --to script $$nb; \
	done

# Clear outputs from notebooks
clean:
	for nb in $(NOTEBOOKS); do \
		jupyter nbconvert --ClearOutputPreprocessor.enabled=True --inplace $$nb; \
	done

# Install required dependencies
install:
	pip install numpy matplotlib notebook

# Open specific projects

basics:
	jupyter notebook neural_network_basics_forward_pass.ipynb

activation:
	jupyter notebook activation_functions_implementation.ipynb

backprop:
	jupyter notebook forward_and_backpropagation.ipynb

loss:
	jupyter notebook loss_functions_analysis.ipynb

optimization:
	jupyter notebook gradient_descent_optimization.ipynb

evaluation:
	jupyter notebook model_training_and_evaluation.ipynb

pipeline:
	jupyter notebook end_to_end_neural_network_pipeline.ipynb
