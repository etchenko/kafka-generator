# Kafka Generator
The goal of this project was to train the GPT-2 model on a majority of Franz Kafka's works, to create computer generated paragraphs of text that could be mis-attributed to Kafka. I worked on this project in order to gain some experience with the gpt-2 model and computer generated text, as well as out of a curiosity in seeing how easy it would be to generate fake text.

## Samples

You can find some samples of 'Kafkaesque' text that I have generated in the samples.txt file. Since the model I used is the 345M GPT-2 model, the samples that it managed to create were not always understandable or even decipherable, so generating a few sample texts from a few input sentences can create the best results for text generation.

## Setup

### GPT-2 Model

In order to train the model on sample data, you need to download the actual GPT-2 model. This can be done with the following command:

''' python download_model.py 345M '''

### Requirements

You can use the requirements.txt file in order to make sure that you have all the correct packages installed on your machine before use:
''' pip install -r requirements.txt '''

### Tensorflow

Because this instantiation of the model was created using tensorflow 1.15.0, you need to install the correct version of tensorflow, otherwise the program will malfunction:

''' pip install tensorflow-gpu==1.15.0
    pip install 'tensorflow-estimator<1.15.0rc0,>1.14.0rc0' --force-reinstall '''

### Cude

Finally, this model requires the use of cuda in order to function. If you do not already have Cude installed, you can run the following commands:

'''wget https://developer.nvidia.com/compute/cuda/9.0/Prod/local_installers/cuda-repo-ubuntu1604-9-0-local_9.0.176-1_amd64-deb
dpkg -i cuda-repo-ubuntu1604-9-0-local_9.0.176-1_amd64-deb
apt-key add /var/cuda-repo-*/7fa2af80.pub
apt-get update
apt-get install cuda-9-0
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-9.0/lib64/ '''

## Usage

### Running the Model

In order to run this model, you can run the following command:

'''PYTHONPATH=src ./train.py --dataset src/all.txt --model_name '345M' '''

> :warning: This is program is very computationally intensive, and is recommended that it be ran using a GPU, otherwise training for multiple generations may take a very long time

### Getting Samples

To generate samples from the trained model, you can use the 'conditional_model' method in order to generate texts based on a seed sentence. 

# gpt-2

Code from the paper ["Language Models are Unsupervised Multitask Learners"](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf).

See more details in our [blog post](https://blog.openai.com/better-language-models/).

## History

The repository is forked from mohamad-ali-nasser who contributed a method called conditional_model().

## Development

See [DEVELOPERS.md](./DEVELOPERS.md)

## Contributors

See [CONTRIBUTORS.md](./CONTRIBUTORS.md)

## Citation

Please use the following bibtex entry:
```
@article{radford2019language,
  title={Language Models are Unsupervised Multitask Learners},
  author={Radford, Alec and Wu, Jeff and Child, Rewon and Luan, David and Amodei, Dario and Sutskever, Ilya},
  year={2019}
}
```

## License

[MIT](./LICENSE)
