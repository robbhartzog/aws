Encryption in transit is achieved with SSL/TLS.

Data at rest on S3 can be encrypted using Server Side Encryption (SSE)-S3, SSE-C,  
SSE-KMS or a client library such as Amazon S3 Encryption Client.

**SSE-S3** uses AWS managed keys and one of the strongest block ciphers available, AES-256,  
to secure your data at rest. Must set header:“x-amz-server-side-encryption":"AES256"

With **SSE-KMS** , the encryption happens in AWS, and theencryption keys are managed by AWS  
but you have full control over the rotation policy of the encryption key. Encryption keys stored in  
AWS KMS.

**SSE-C** is server-side encryption using data keys fullymanaged by the customer outside of  
AWS. Amazon S3 does not store the encryption key you provide. Encryption key must provided  
in HTTP headers, for every HTTP request made

With **Client-Side Encryption** , you have to do the encryptionyourself and you have full control  
over the encryption keys. Using an encryption client library, such as the Amazon S3 Encryption  
Client, you retain control of the keys and complete the encryption and decryption of objects  
client-side using an encryption library of your choice. Some customers prefer full end-to-end  
control of the encryption and decryption of objects (you perform the encryption/decryption  
yourself - AWS cannot decrypt); that way, only encrypted objects are transmitted over the  
Internet to Amazon S3.

#### S3 Object Lock

S3 Object Lock is used to prevent an object from being deleted or overwritten for a fixed amount  
of time or indefinitely. This is not used to lock policies from future edits, but instead objects.If you  
enable the S3 Object Lock feature, you won't be able to upload new versions of an object.