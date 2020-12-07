# pytorch_samples

## environment pytorch17

## Modern Computer Vision with PyTorch
## Notes
common problem of data directory - not consistent; use:  
data_folder = '~/data/FMNIST'   

### Chapter 04
Running the notebooks in colab (as recommended) works fine - run it in a local python/jupyter environment - nope!    You’ll find imgaug version mis-match.

book:

plt.imshow(aug.augment_image(tr_images[0]), cmap='gray')

you’ll get:  TypeError: %d format: a number is required, not str

local python with imgaug 0.4:

plt.imshow(aug.augment_image(tr_images[0].numpy()), cmap='gray')

the difference - convert the torch tensor to numpy – which makes sense.  
