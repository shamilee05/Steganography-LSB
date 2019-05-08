# Steganography using LSB
A basic MATLAB program to apply Steganography on an image using the LSB technique.

Steganography is a method of **encoding data** onto a form of media so as to conveniently hide the data from being read. This is hence a **data hiding** technique.


With image steganography, there are multiple methods of implementation, one of which is using the concept of the **LSB**. For an image, every pixel has an intensity value which 
when represented in the binary form, gives us a sequence of bits wherein the **MSB** or the **Most Significant Bit** gives us the **most amount of information** about the image whereas 
the **LSB** or the **Least Significant Bit** gives us the **least amount of information** about the image.

This LSB when replaced **does not significantly change** the appearance of the image, hence the data to be hidden can be encoded into the binary form and inserted into these LSB positions. 
Since there is no change in the appearance of the image, a third person will **not be able to detect the presence** of the hidden data in the image. 

This image can then be sent to the destination where the message can be decoded by retrieving the LSB bits of the image.

*Important terms:*
- **Cover Image**: The image which is to be used to hide the data.
- **Stego Image**: The image which has been embedded with the hidden data.

<br>

The methodology followed by the program is as given below:
1. Take the secret message and convert it to the binary format.
2. Take the cover image and convert it to grayscale. (Using grayscale is much more convenient as an 8-bit per pixel grayscale image will have 8 bit-sequences as opposed to a 24-bit per pixel coloured image with 24-bit sequences.)
3. For each of the pixel in the image, take the intensity value (lying in the range 0 to 255) and convert it to the binary format.
4. Take the **right-most bit or the LSB** and replace it with a **bit** from the **secret message**.
5. Repeat this until all the bits of the secret message have been embedded. The image will then be called as a stego image.

The process is followed in exact reverse at the destination to decode the hidden message from the stego image.

An instance of how the program works is as shown below:

There is no difference seen whatsover in these images, even though there is a hidden message present in the stego image:

![alt text](https://github.com/shamilee05/Steganography-LSB/blob/master/Cover_Stego.png)

<br>

The hidden message is embedded at the source and decoded at the destination:

![alt text](https://github.com/shamilee05/Steganography-LSB/blob/master/Hidden_Message.png)
