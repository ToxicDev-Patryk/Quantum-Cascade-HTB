<img src='https://github.com/hackthebox/public-templates/blob/master/assets/banner.png' style='zoom: 80%;' align=left /> <font size='10'>Quantum Cascade</font>

1<sup>st</sup> August 2023

Prepared By: PatrykToxicDev

Challenge Author(s): PatrykToxicDev

Difficulty: <font color='orange'>Medium</font>

<br><br>

## Synopsis (!)
The user must decode an encrypted message by reversing the "Quantum Cascade" encryption algorithm provided in the challenge code.

## Description (!)
The Python code implements a complex encryption algorithm that generates encryption keys, mixes them, and uses the mixed key to encrypt a given string (flag). To solve the challenge, the user needs to understand and reverse the encryption process to retrieve the original flag.

## Skills Required (!)
Python

Researching Skills

Cryptographic Concepts

Familiarity with algorithm analysis

## Skills Learned (!)
Learn how complex encryption algorithms are constructed.

Learn how to reverse-engineer encryption mechanisms.

Gain insights into key generation and mixing techniques.

## Enumeration (!)
### Analyzing the source code (*)
Upon unzipping the challenge files, you receive a Python script with the following key functions: get_keys(), mix_keys(), and encrypt().

Analyze these functions to understand the encryption process in depth.

...

If we look at main.py, we can see that our goal is to reverse the encryption process defined in the encrypt function to retrieve the original flag.

The basic workflow of the script is as follows:

The main() function orchestrates the execution by generating keys and encrypting the input string (flag).

The get_keys() function generates a series of encryption keys.

The mix_keys() function processes these keys to create a final mixed key.

The encrypt() function uses the mixed key to transform the input string into an encrypted byte sequence.

A little summary of all the interesting things we have found out so far:

The key generation involves complex mathematical operations to ensure variability and unpredictability.

The key mixing process creates a final mixed key that is essential for encryption.

The encryption function applies multiple transformations to obscure the original data.

## Solution (!)
### Finding the vulnerability (*)
The vulnerability lies in understanding the encryption process and reversing it to retrieve the original message (flag).

## Exploitation (!)

Let us consider our attack scenario.

Analyze the key generation process.

Reverse the key mixing process to derive the original keys.

Apply the reverse transformations to decrypt the encrypted byte sequence.

The attack explained above can be implemented with the following code:

`def reverse_key_mixing(mixed_key, original_keys):
    # Implement the logic to reverse the key mixing process
    pass`

`def decrypt(encrypted_data, mixed_key):
    # Implement the logic to decrypt the encrypted data using the reversed keys
    pass`
    
## Getting the flag (!)
A final summary of all that was said above:

Understand the key generation and mixing processes.

Reverse these processes to retrieve the original keys.

Apply reverse transformations to decrypt the encrypted message.

This recap can be represented by code using pwn() function:

`def pwn():
    mixed_key = reverse_key_mixing(mixed_key_from_server, original_keys)
    flag = decrypt(encrypted_flag, mixed_key)
    print(flag)`
