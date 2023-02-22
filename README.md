<h1>Seasats Autonomous Seacraft Image Classification</h1>
<p>This is an image classification model for the Seasats Autonomous Seacraft, which classifies images as containing a boat or not containing a boat. The model is based on the Vision Transformer (ViT) architecture and is trained on a dataset of labeled images of the sea surface.</p>

<h2>Installation and Project Setup</h2>
<p>To set up the project, first clone the repository:</p>

<code>git clone https://github.com/your-username/seasats-image-classification.git </code>
<p>Next, create a new conda environment from the provided environment.yml file:</p>

<code>conda env create -f environment.yml</code>
<p>Activate the environment:</p>

<code>conda activate shipclassifier</code>
<p>You should now be able to run the model and train it on new data.</p>

<h2>Prepare Dataset</h2>
<p>This code crops and resizes images to size=256px, input images can be of any aspect ratio / size</p>
<p>Images are expected to be in the following directory structure:</p>
<ul>
<li> 70% of the images at /dataset/train</li>
<li> 30% of the images at /dataset/val</li>
</ul>


<h2>Choosing Hyperparameters</h2>
<p>The ViT model has several hyperparameters that can be tuned to achieve better performance on a particular task. Here are some tips for choosing hyperparameters for the SEASAT dataset:</p>
<ul>
<li>image_size: This parameter controls the size of the input images. In general, larger images may require a larger image_size to capture more details, but may also require more processing power and longer training times. You can experiment with different values to find the best tradeoff between performance and speed.</li>
<li>patch_size: This parameter controls the size of the image patches used by the transformer. Larger patches may capture more contextual information, but may also introduce more noise or reduce the resolution of the input images. Smaller patches may be more precise, but may require more processing power to process. You can experiment with different values to find the best balance.</li>
<li>dim: This parameter controls the dimension of the transformer embeddings. Higher values may allow the model to capture more complex relationships between patches, but may also require more processing power and longer training times. You can experiment with different values to find the best tradeoff between performance and speed.</li>
<li>depth: This parameter controls the number of transformer layers. Deeper models may be able to capture more complex patterns, but may also require more processing power and longer training times. You can experiment with different values to find the best tradeoff between performance and speed.</li>
<li>heads: This parameter controls the number of attention heads in each transformer layer. More heads may allow the model to capture more fine-grained patterns, but may also require more processing power and longer training times. You can experiment with different values to find the best tradeoff between performance and speed.</li>
<li>mlp_dim: This parameter controls the dimension of the multi-layer perceptron used in each transformer layer. Higher values may allow the model to capture more complex patterns, but may also require more processing power and longer training times. You can experiment with different values to find the best tradeoff between performance and speed.</li>

</ul>

<h2>Training</h2>
<p>To train the model on new data, just run the train.py script. But first, choose your training parameters</p>
<p>-- epochs: The number of epochs to train for. (default: 10)</p>
<p>-- batch_size: The batch size for training. (default: 32)</p>
<p>-- lr: The learning rate for the optimizer. (default: 1e-4)</p>


<h2>TODO</h2>
<p>Optimize the preprocessing for the seasats dataset</p>
<p>ViT is optimzied to run on GPU, a different model may be more well suited for the seasats hardware (CNN/RESNET)</p>