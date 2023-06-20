In this notebook, we'll be building a generative adversarial network (GAN) trained on the MNIST dataset. From this, we'll be able to generate new handwritten digits! GANs were first reported on in 2014 from Ian Goodfellow and others in Yoshua Bengio's lab. Since then, GANs have exploded in popularity. Here are a few examples to check out: Pix2Pix CycleGAN & Pix2Pix in PyTorch, Jun-Yan Zhu A list of generative models The idea behind GANs is that you have two networks, a generator 𝐺 and a discriminator 𝐷 , competing against each other. The generator makes "fake" data to pass to the discriminator. The discriminator also sees real training data and predicts if the data it's received is real or fake. The generator is trained to fool the discriminator, it wants to output data that looks as close as possible to real, training data. The discriminator is a classifier that is trained to figure out which data is real and which is fake. What ends up happening is that the generator learns to make data that is indistinguishable from real data to the discriminator. The general structure of a GAN is shown in the diagram above, using MNIST images as data. The latent sample is a random vector that the generator uses to construct its fake images. This is often called a latent vector and that vector space is called latent space. As the generator trains, it figures out how to map latent vectors to recognizable images that can fool the discriminator. If you're interested in generating only new images, you can throw out the discriminator after training. In this notebook, I'll show you how to define and train these adversarial networks in PyTorch and generate new images!
