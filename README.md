<html lang="en"><head>
    <meta charset="UTF-8">
    </head>
<body marginheight="0"><h2>The code for DBIA on DeiT</h2>
<ul>
<li><p>This is the source code of DBIA: Data-free Backdoor Injection Attack against Transformer Networks <a href="https://arxiv.org/pdf/2111.11870.pdf">https://arxiv.org/pdf/2111.11870.pdf</a></p>
<li><p>Moreover, we refer to the released code of DeiT, which is from <a href="https://github.com/facebookresearch/deit">https://github.com/facebookresearch/deit</a></p>
</li>
</ul>
<h3>Environment</h3>
<ul>
<li>PyTorch 1.7.0+ and torchvision 0.8.1+ and pytorch-image-models 0.3.2</li>
</ul>
<h3>Data Preparation</h3>
<ul>
<li>Imagenet2012 validation set data is placed in <code>./data/imagenet2012/val</code></li>
</ul>
<p><img src="https://github.com/yangyunfei16/DBIA/blob/main/DBIA/pictures/data_preparation.png" alt="data preparation">

</p>
<h3>Starting Poisoning</h3>
<ul>
<li>Generate the background picture required for training trigger<pre><code>  python preprocess.py</code></pre>
</li>
<li>Background picture and <code>blend_ tensor.pt</code> is stored in <code>./savedfigure</code></li>
</ul>
<h3>Reversing Trigger</h3>
<ul>
<li>First, write the path of <code>blend_tensor.pt</code> on line 38 of the file <code>activate_trigger.py</code><pre><code>  python activate_trigger.py</code></pre>
</li>
<li>Trigger pictures are stored in the triggers folder</li>
</ul>
<h3>Training Poisoning Model</h3>
<ul>
<li>First, write the path of the selected trigger on line 35 of the file <code>tensors_dataset.py</code><pre><code>  python backdoor_main.py</code></pre>
</li>
</ul>
<h3>Citation</h3>
<ul>
<li>If it helps you, you can cite our paper as below:<pre><code>  @article{lv2021dbia,
  title={Dbia: Data-free backdoor injection attack against transformer networks},
  author={Lv, Peizhuo and Ma, Hualong and Zhou, Jiachen and Liang, Ruigang and Chen, Kai and Zhang, Shengzhi and Yang, Yunfei},
  journal={arXiv preprint arXiv:2111.11870},
  year={2021}
}</code></pre>
</li>


</body></html>

