# Cypher for items dat file

All names in file items.dat are encoded using simple cypher. This cypher is for now always using key `PBG892FXX982ABC*`. This cypher is using XOR function, so same code can be used for both encoding and decoding. You will find code with explained functionality bellow.


Here is code for decoding/encoding cypher:
```CPP
std::string secret = "PBG892FXX982ABC*"; // this contains cypher key

std::string input = "..."; // to this variable you need to assign input data
int itemID = ...; // to this variable you need to assign ID of item for which you are encoding/decoding data
std::string output = ""; // this variable will contain output data

int inputLen = input.length();
int secretLen = secret.length();

for (int i = 0; i < strLen; i++) {
  int secretCharPos = (i + itemID) % secretLen; // we get positon of secret character by adding together position of orginal character and item ID, on top of this is applied modulo with value of length of secret text
  char secretChar = secret[secretCharPos]; // we get secret character based on position which we calculated
  char inputChar = input[i]; // we are getting one character of original data each time we execute this loop
  output += inputChar ^ secretChar; // input character is XORed together with character of secret text, which gives us final output character
}
```
