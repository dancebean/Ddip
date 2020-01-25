# `ddipp`'s known limitations, issues, bugs, and things to add


## Limitations, Issues, and Bugs:

* **Works in Single Host with Multiple GPU only**

    `ddipp` was developed/tested on a single host with multiple GPUs, and isn't likely to work in "*multiple nodes x multiple GPU*" yet.  Would be an interesting project though. 

* **Process group must starts with GPU 0, and in consecutive, ascending order**

    In other words, on a host with GPU [0,1,2,3], the following DDP group specification may not work properly yet: 
    `3,2,1,0`, or `1,2,3`, or `0,3` etc...

* **Problems with FastAI notebooks:**
    * lesson6-pets-more the cnn_learner doesn't show training speed-up with multiple GPUs

    * lesson4-imdb, a langauge modelling task, doesn't seem to train correctly when in multiple-GPU DDP mode.

        Something isn't done right when loading a previously trained model/text embedding to train another language model.  Not seeing improvement in accuracy.

## Things to Add:
* **Unit tests, and perhaps CI**

    So far FastAi's lesson notebooks are used as integration test.  `ddipp` needs and will benefit from some unit tests.

* **FastAi V2** #feature
    
    `ddipp` was developed using FastAi v1's lesson notebooks, and `fastai v2` is being rolled out. `ddipp` may need to catch up.

* **FastAi's `nbdev` Approach**
    
    *[Use Jupyter Notebook for Everything](https://www.fast.ai/2019/12/02/nbdev/)* - Jeremy Howard, Dec 2, 2019

    Centuries of wisdom from experimental science distilled from the many great minds, all point to the benefit of iteractive tinkering and collaborative research via documentation and tests. 
    
    In software development of this age, finally a pragmatic tool to foster one-stop development of code, documentation, and tests is emerging --- `nbdev`, the labor of love from the brains behind FastAi.

    `ddipp` needs better documentation, more unit tests, and there are new features to explore -- for those future tasks, it would be interesting to see the productivity gain by trying out `nbdev`.


* **Support for Fastai in Swift**  *Gasp!*




