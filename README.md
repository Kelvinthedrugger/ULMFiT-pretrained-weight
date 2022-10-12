# ULMFiT-pretrained-weight
ULMFiT language model pre-trained weight of several stages, since I couldn't find it myself, I decided to do one and save people hours, and of course, help the energy problem globally.

Link of both the thesis and code can be found on [papers with code](https://paperswithcode.com/method/ulmfit)

Hope this will help people that try to use deep learning to solve problems

## Plot twist

There WERE pretrained weights (on a smaller DS)...

```bash
!wget http://files.fast.ai/models/wt103_tiny.tgz
!tar xf {path}/wt103_tiny.tgz -C {path}
```
, and everything would just work out of the box

## Note
I use AWD_LSTM architecture & IMDB dataset to train the whole thing, just like how the [original notebook](https://github.com/fastai/fastai/blob/master/nbs/examples/ulmfit.ipynb) did.

## Usage
what i can think of now is to use Dropbox link, due to the limitation of file size on GitHub, 

not sure if Git for large files would work

Even better if there's a way to compress the files without damage to the original files

Stuff listed in [Items](https://github.com/Kelvinthedrugger/ULMFiT-pretrained-weight/edit/main/README.md#items) is all you needed to do a text classification use AWD_LSTM model arch.

## Items

### stage1
[link](https://www.dropbox.com/s/77ujgedl5hs8aic/stage1.pth)

### finetune1
[link](https://www.dropbox.com/s/zzv5u8stafi0qoi/finetune_stage_finished_0815.pth)


## Result
```python
learn.unfreeze()
lr /= 5
learn.fit_one_cycle(2, slice(lr/(2.6**4),lr), moms=(0.8,0.7,0.8), wd=0.1)
```
<img src="https://user-images.githubusercontent.com/59814445/184619787-5127276f-e4eb-43a7-8e72-2587c7666697.png" height="180" width="732" />


## Citation
[arXiv:1801.06146v5](https://arxiv.org/abs/1801.06146v5)

