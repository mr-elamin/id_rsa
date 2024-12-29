
# Encrypted SSH Private Key

This repository contains an encrypted SSH private key. Below are the steps to create the encrypted key and how to decrypt it.

## Steps to Encrypt the SSH Private Key

1. **Encrypt Your SSH Private Key**:
   Use GPG to encrypt your SSH private key with a password:

   ```sh
   gpg --symmetric --cipher-algo AES256 ~/.ssh/id_rsa
   ```

   This command will prompt you to enter a passphrase to encrypt the file. The encrypted file will be saved as `id_rsa.gpg` in the same directory.

2. **Add the Encrypted Key to the Repository**:
   - Copy the encrypted key file to the repository directory:

     ```sh
     cp ~/.ssh/id_rsa.gpg .
     ```

   - Add and commit the encrypted key file to the repository:

     ```sh
     git add id_rsa.gpg
     git commit -m "Add encrypted SSH private key"
     ```

   - Push the changes to GitHub:

     ```sh
     git push origin main
     ```

## Steps to Decrypt the SSH Private Key

1. **Clone the Repository**:
   - Clone the repository to your local machine:

     ```sh
     git clone https://github.com/mr-elamin/id_rsa.git
     cd your-repository
     ```

2. **Decrypt the Key**:
   - Use GPG to decrypt the key:

     ```sh
     gpg --output ~/.ssh/id_rsa --decrypt id_rsa.gpg
     chmod 600 ~/.ssh/id_rsa
     ```
