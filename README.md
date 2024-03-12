# Neural Style Transfer 

This is my attempt at following along with the [Neural-Style Algorithm](https://arxiv.org/abs/1508.06576) developed by Leon A. Gatys, Alexander S. Ecker and Matthias Bethge. 
I wanted to try my hand at this because it seemed like a great exercise to practice and demonstrate my understanding of working with neural networks, as well as to gain experience
with more computer vision and pattern recognition techniques. There's some pretty complex (at least to me 😵‍💫) math in play here, and I'm still actively working towards understanding
it - hopefully I'll be able to apply similar techniques in future projects 😎😎

All computation was done with the help of Google Colab!

## An Example of Style Transfer:

This is the first image, which I'll be using as the `style_img`, for style reference.
It should be pretty recognizable :)

![Van Gogh's 'Starry Night'](https://github.com/davidjyang/neural_style_transfer/assets/78115200/72a69713-9d11-45c8-8594-a80e3201cc01)

This is the next image, which I'll be using as the `content_img`, for content reference. Hopefully, the result will look like `content_img`, recreated in the style
of the `style_img`. 

![Hokusai's Great Wave Off Kanagawa](https://github.com/davidjyang/neural_style_transfer/assets/78115200/8873b878-4f6f-43dd-bf8b-ad0f13c605b4)

Here's the result!

![Hokusai's Great Wave, after passing through the style transfer model](https://github.com/davidjyang/neural_style_transfer/assets/78115200/dd460703-6cf3-42fb-b829-02ed1b62f706)





