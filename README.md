# MLproject
datasetprepare<br>
collect celebA<br>
dataset=torchvision.datasets.CelebA(
        root="celeba",split='train',
        transform=transforms.Compose(
            [transforms.Resize(img_size),transforms.CenterCrop(img_size),
             transforms.ToTensor(), transforms.Normalize((0.5,0.5,0.5),(0.5,0.5,0.5))]
        ),download=True
    )
Condition GAN <br>
待解决的问题：<br>
1.提取celebA库中图片的特征作为label
