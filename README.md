# MLproject
<h2>dataset prepare</h2>
collect celebA<br>
dataset=torchvision.datasets.CelebA(
        root="celeba",split='train',
        transform=transforms.Compose(
            [transforms.Resize(img_size),transforms.CenterCrop(img_size),
             transforms.ToTensor(), transforms.Normalize((0.5,0.5,0.5),(0.5,0.5,0.5))]
        ),download=True
    )<br>
this may not work on your computer,so i recommend you go to"https://drive.google.com/drive/folders/0B7EVK8r0v71pTUZsaXdaSnZBZzg?resourcekey=0-rJlzl934LzC-Xp28GeIBzQ" to get "img_align_celeba.zip" and unzip it in the directory<br>
the attributes and the landmarks have been pushed<br>
<h2>Condition GAN </h2>
待解决的问题：<br>
1.提取celebA库中图片的特征作为label
