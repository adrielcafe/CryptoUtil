CryptoUtil
==========
This utility class allows you to:
* Encrypt and decrypt a string using a secret key
* Get the hash of a string or a file using some of this algorithms: **MD5**, **SHA-1**, **SHA-256**, **SHA-384** or **SHA-512**

How to use
----------

### Encrypt and decrypt a string using a secret key
First of all we must define the secret key:
```csharp
CryptoUtil.key = "my secret key";
```
**WARNING**: It's not a good idea change the secret key in production mode!

Now we can encrypt and decrypt easily:
```csharp
string str = "Testing Crypto";
string encrypted = CryptoUtil.Encrypt(str);
string decrypted = CryptoUtil.Decrypt(encrypted);

Console.WriteLine(string.Format("{0} > {1} > {2}", str, encrypted, decrypted));

// Output: Testing Crypto > rn3ThfZkwFdii9mpWeuJkA== > Testing Crypto
```

### Getting the hash of a string or a file
