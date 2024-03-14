# Neural Style Transfer 

This is my attempt at following along with the [Neural-Style Algorithm](https://arxiv.org/abs/1508.06576) developed by Leon A. Gatys, Alexander S. Ecker and Matthias Bethge, as well as recreating (without looking!) [a PyTorch tutorial](https://pytorch.org/tutorials/advanced/neural_style_tutorial.html) explaining a neural style transfer. 
I wanted to try my hand at this because it seemed like a great exercise to practice and demonstrate my understanding of working with neural networks, as well as to gain experience
with more computer vision and pattern recognition techniques. There's some pretty complex (at least to me 😵‍💫) math in play here, and I'm still actively working towards understanding it - hopefully I'll be able to apply similar techniques in future projects 😎😎

This project was especially fun to work through, trying to understand why the model works in the way that it does, because I could literally apply these this style transfer model to any image. Obviously, I spent way too much time playing around with what my dog would look like in the style of Picasso. 

All computation was done with the help of Google Colab's free T4 GPUs.

## An Example of Style Transfer:

This is the first image, which I'll be using as the `style_img`, for style reference.
It should be pretty recognizable :)

![Van Gogh's 'Starry Night'](https://github.com/davidjyang/neural_style_transfer/assets/78115200/72a69713-9d11-45c8-8594-a80e3201cc01)

This is the next image, which I'll be using as the `content_img`, for content reference. Hopefully, the result will look like `content_img`, recreated in the style
of the `style_img`. 

![Hokusai's Great Wave Off Kanagawa](https://github.com/davidjyang/neural_style_transfer/assets/78115200/8873b878-4f6f-43dd-bf8b-ad0f13c605b4)

Here's the result!

![Hokusai's Great Wave, after passing through the style transfer model](https://github.com/davidjyang/neural_style_transfer/assets/78115200/dd460703-6cf3-42fb-b829-02ed1b62f706)

You can definitely see how a lot of the yellows, blues, and greens were brought into Hokusai's *The Great Wave off Kanagawa*, and how the final image seems to have brushstrokes despite the original being a woodblock print.

## The Network Used

The network I used is a pretrained VGG network with 19 layers. VGG networks, or visual geometry group networks, were developed and popularized by Karen Simonyan and Andrew Zisserman in their 2014 paper, [Very Deep Convolutional Networks for Large-Scale Image Recognition](https://arxiv.org/abs/1409.1556). I thought there were a few intuitions that really opened my eyes in this project - the first being inserting `style_loss` and `content_loss` inbetween specific convolutional layers in the network:

![code snippet iterating through layers in network](https://github.com/davidjyang/neural_style_transfer/assets/78115200/8144b36a-ab08-4123-a89f-5a4da516f46f)
![actual insertion of style and content losses](https://github.com/davidjyang/neural_style_transfer/assets/78115200/64fad322-47e7-452b-b4a1-4c99f1fb6605)

I think usually, I'm used to computing loss after each pass, instead of after specific layers; however, it's really interesting to see that computing loss after specific layers can target content/style, according to Gatys et al.!

The related intuition that was surprising to me was that Gatys et al.'s algorithm claims that style and content feature maps were deeper in the network layers - it's not that I doubt it, but it's just interesting to think about and I guess makes sense with the idea that object classification also occurs at deeper layers (and makes sense with why loss is computed as we do above). I think I'm still trying to wrap my head around it all 💫😵💫.

## Another (Slightly Worse) Example of Style Transfer

For the next example, let's stick with the same `content_img`, Hokusai's _Great Wave_, and try a different `style_img` called _nine lives_ by yumikrum in the pastel vaporwave aesthetic:

![nine lives by yumi krum - a pink, purple artwork with two black cats in the foreground](https://github.com/davidjyang/neural_style_transfer/assets/78115200/b2ab0810-f529-4c74-a9d3-8357f8b6e127)

(["nine lives"](https://www.flickr.com/photos/94725359@N06/32671299630) by [yumikrum](https://www.flickr.com/photos/94725359@N06) is licensed under [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/?ref=openverse).)

Take note of the color palette - the pinks, purples, and white, as well as the stark black of the cats - and other than the cats, the generally low contrast of the artwork.
What do you think the result looks like?

![Hokusai's Great Wave, after passing through the style transfer model](https://github.com/davidjyang/neural_style_transfer/assets/78115200/ca1dc530-9514-452a-8a8d-0e399e3efab0)




