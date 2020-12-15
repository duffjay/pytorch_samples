# pytorch_samples

## environment pytorch17

## Modern Computer Vision with PyTorch
https://github.com/PacktPublishing/Modern-Computer-Vision-with-PyTorch  


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

## Data Considerations
### ybat
annotation tool used in the book for YOLO:  
https://github.com/drainingsun/ybat
### security images
#### Dell Laptop

~~~
cd ~/data
ls /media/jay/ssd-usb1/
cp /media/jay/ssd-usb1/*202010.tar.gz .
cp /media/jay/ssd-usb1/*202009.tar.gz .

tar -xvf annotation_202009.tar.gz 
tar -xvf jpeg_images_202009.tar.gz 


# you'll see the data in 
ls ~/data/hsdata/annotation/202009
ls ~/data/hsdata/annotation/202009

# class /hsdata
gedit security_classes.txt

~~~

PascalVOC annotation format seems to be the standard  
