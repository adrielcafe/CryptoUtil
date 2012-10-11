CryptoUtil
==========
This C# utility class allows you to:
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
This also is very simple. Look:
```csharp
// From a string
string str = "my password";
Console.WriteLine("Original String: " + str);
Console.WriteLine("MD5:    " + CryptoUtil.GetHashFromString(str, Algorithm.MD5));
Console.WriteLine("SHA1:   " + CryptoUtil.GetHashFromString(str, Algorithm.SHA1));
Console.WriteLine("SHA256: " + CryptoUtil.GetHashFromString(str, Algorithm.SHA256));
Console.WriteLine("SHA384: " + CryptoUtil.GetHashFromString(str, Algorithm.SHA384));
Console.WriteLine("SHA512: " + CryptoUtil.GetHashFromString(str, Algorithm.SHA512));

// From a file
string str2 = @"c:\my_file.txt";
Console.WriteLine("MD5:    " + CryptoUtil.GetHashFromFile(str2, Algorithm.MD5));
Console.WriteLine("SHA1:   " + CryptoUtil.GetHashFromFile(str2, Algorithm.SHA1));
Console.WriteLine("SHA256: " + CryptoUtil.GetHashFromFile(str2, Algorithm.SHA256));
Console.WriteLine("SHA384: " + CryptoUtil.GetHashFromFile(str2, Algorithm.SHA384));
Console.WriteLine("SHA512: " + CryptoUtil.GetHashFromFile(str2, Algorithm.SHA512));

/* Output:
  > STRING
  Original String: my password
  MD5:    329670c3265b6ccd392e622733e9772f
  SHA1:   a2f8f7fa195a080a22a689041daa8f2044f9f336
  SHA256: bb14292d91c6d0920a5536bb41f3a50f66351b7b9d94c804dfce8a96ca1051f2
  SHA384: 5cb69a1f4be83cf7d4eca6d8a806cd56a97c27b756f15a6417edbe2d7eaa16117230d137407bdf322172b683847f9d0e
  SHA512: e28bdbf8faa97dab2203fcc89e397a4bf8d4a5b370421e5481a55f317caee4f81be5a810bb1cffc4695c32198717b9a6e835895852ee3a8689d0963463f2db15
  
  > FILE
  MD5:    21b2c27fbe338d800826e5ad67db7d0e
  SHA1:   1e7bd74bd8f834b42c892d893976e5be5493e029
  SHA256: 9e189ad1eb128bfd032968943f323dcf788fd6641cdc7ebddb72a3fa49aceb0f
  SHA384: 70a5d4cf1ad3af999180496f38e8190ea77b12da08992ce3f129989cc0a70d2661e28e819ac60bfb878b78fbaef4c7f1
  SHA512: 1c6aef5f220ad1c61c96f42da883c7046a3520d86144c5eb513b02d19587aca47fdeb71fd898bdc5be3fde0cd1f02f05e3104795ad9a0a8f19e292408ccdd7c3
*/
```


#### Simple like that!