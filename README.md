# Korean Compound Noun Decomposition(한국어 복합 명사 분해)


This Korean compound noun decomposition is made, in particular, on the following version.

```
OS: Ubuntu 16.04.1
Python version: 3.5.2
Tensorflow version: 1.8.0
```

If you encounter some error, check the version above once again. 

# Before running predic.py script, download model with downloader shell script

> ./downloader.sh

```shell
```

**After downloading the model, You would find out **model** directory, then you can run predict.py.**

But you don't have **curl**, intall it on Ubuntu

> sudo apt-get install curl

# How To Run this Korean automatic spacing program.

> python3 predict.py [-h] [-o OUTPUT] [-n NUMBER] input

1. -h: means help message about how to use this script to run 

2. -o  OUTPUT: output file you want to get on input file 

3. -n NUMBER: When you have big size file, you could test some batches together. 
           So "-n" means how much you want to test together maximumally on a test.

4. input: Input file

If you know abot how to run, see the help message below:

Also you can check on prompt if you type in **python3 predict.py -h**

```
usage: predict.py [-h] [-o OUTPUT] [-n NUMBER] input

split program for compound nouns

positional arguments:
  input                 input file

optional arguments:
  -h, --help            show this help message and exit
  -o OUTPUT, --output OUTPUT
                        output file
  -n NUMBER, --number NUMBER
                        Batch size, this must be less than your number of
                        data, and memory size
```

When you run the python scipt, predict.py, you have to specify the input file, 

If you not, you get the following error:

```shell
$ python3 predict.py 
/home/nlp-gpu/.local/lib/python3.5/site-packages/tensorflow/python/ops/gradients_impl.py:100: UserWarning: Converting sparse IndexedSlices to a dense Tensor of unknown shape. This may consume a large amount of memory.
  "Converting sparse IndexedSlices to a dense Tensor of unknown shape. "
usage: predict.py [-h] [-o OUTPUT] [-n NUMBER] input
predict.py: error: the following arguments are required: input
```
**Be careful**

Don't touch **data and model directory**

This file contains vocabulary dictionary and model file after traninig. 

### an example of running predict.py

In order to get result of Korean automatic spacing, If you type in as follows:

> python3 predict.py input_file -o output_file

````shell
````

But If you type in "-n" option, evaluation time would get shoter as follows: 

```
```

If you don't know how to run, go through **run.sh** script file. 

This would show how to run Korean automatic spacing. 

**sample_x** : is sample file to test whether predict.py script works or not,  When you execute **run.sh** 

# Result

There are two ways you can get result of running this Korean automatic spacing. 

But, in any case, all of the result will be created under **result** directory. 

First, If you specify output file, it would create itself under **result** directory.

```shell
./
|...
| result/
| | ourput_file
| | PREDICTIONS_TAGS # This tag value like "B" or "I"
| run.sh
.....
```

Second, If you don't specify output file. it would create the default output file named **PREDICTIONS_RESULT**

```shell
./
|...
| result/
| | PREDICTIONS_RESULT # -> this file is the defualt result file of Korean automatic spacing. 
| | PREDICTIONS_TAGS # This tag value like "B" or "I"
| run.sh
.....
```

