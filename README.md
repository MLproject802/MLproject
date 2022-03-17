# MLproject
datasetprepare
collect celebA
dataset=torchvision.datasets.CelebA(
        root="celeba",split='train',
        transform=transforms.Compose(
            [transforms.Resize(img_size),transforms.CenterCrop(img_size),
             transforms.ToTensor(), transforms.Normalize((0.5,0.5,0.5),(0.5,0.5,0.5))]
        ),download=True
    )
