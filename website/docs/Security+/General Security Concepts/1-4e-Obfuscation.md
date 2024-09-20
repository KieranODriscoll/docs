# 1.4e - Obfuscation
## Obfuscation
- The process of making something unclear
	- It's now much more difficult to understand
- But it's not impossible to understand
	- If you know how to read it
- Hide information in plain sight
	- Store payment information without storing a credit card number
- Hide information inside of an image
	- Steganography
## Steganography
- Greek for "concealed writing"
	- Security through obscurity
- Message is invisible - But it's really there
- The cover text - The container document or file
## Common Steganography Techniques
### Network based 
- Embed messages in the TCP packets
### Use an image 
- Embed the message in the image itself
### Invisible watermarks
- Yellow dots on printers
## Other steganography types
### Audio Steganography
- Modify the digital audio file
- Interlace a secret message within the audio
- Similar technique to image steganography
### Video Steganography
- A sequence of images
- Use image steganography on a larger scale
- Manage the signal to noise ratio
- Potentially transfer much more information
## Tokenization
- Replace sensitive data with a non-sensitive placeholder
	- SSN 266-12-1112 is now 691-61-8539
- Common with credit card processing
	- Use a temporary token during payment
	- An attacker capturing the card numbers can't use them later
- This isn't encryption or hashing
	- The original data and token aren't mathematically related
	- No encryption overhead
![Pasted_image_20240905154046](//assets/Pasted_image_20240905154046.webp)
## Data masking
- Data obfuscation
	- Hide some of the original data
- Protects PII
	- And other sensitive data
- May only be hidden from view
	- The data may still be intact in storage
	- Control the view based on permissions
- Many different techniques
	- Substituting , shuffling, encrypting, masking out, etc
