# 🔐 ECC Elliptic Curve Implementation

## 📋 Project Overview
This project demonstrates the implementation of **Elliptic Curve Cryptography (ECC)** over a finite field. The elliptic curve used is defined as:

`y^2 mod 263 = (x^3 + x + 1) mod 263`

The group elements (points on the curve) and cryptographic operations (point addition, scalar multiplication) are implemented to support elliptic curve encryption and decryption.

## ✨ Key Features
- **Curve Definition**: `y^2 = x^3 + x + 1 mod 263`
- **Elliptic Curve Points**: Contains 263 points including (1, 23), (87, 61), etc.
- **🔑 Public Key Encryption**: Implements ECC-based encryption and decryption using Alice and Bob's public keys.
- **🧮 Finite Field Arithmetic**: Supports point addition, doubling, and scalar multiplication.

### 🔐 Example Encryption
- **Public Keys**:
  - A's public key: `Pa = 51 × (148, 27) = (3, 89)`
  - B's public key: `Pb = 212 × (148, 27) = (61, 52)`
- **🔐 Encryption**: Alice sends an encrypted message to Bob: 
`Encrypted Message = {(3, 89), 240, 222}`
- **🔓 Decryption**: Bob decrypts the message and obtains the plaintext `(10, 89)`.


## 🚀 Getting Started
To run the ECC implementation:
1. 📥 Clone the repository.
2. 💻 Import the project into your environment.
3. 🔨 Build the project.
4. ▶️ Run the `main.cpp` file.


## What To Expect?
The elliptic curve: y^2 mod 263 = (x^3+1x+1) mod 263

Points on the curve (i.e. the group elements):
```cpp
(0, 1) (0, 262) (1, 23) (1, 240) (2, 96) (2, 167)
(3, 89) (3, 174) (4, 73) (4, 190) (6, 111) (6, 152)
(7, 80) (7, 183) (8, 28) (8, 235) (10, 119) (10, 144)
(14, 38) (14, 225) (15, 32) (15, 231) (21, 128) (21, 135)
(22, 64) (22, 199) (23, 57) (23, 206) (24, 35) (24, 228)
(27, 81) (27, 182) (29, 111) (29, 152) (30, 87) (30, 176)
(31, 34) (31, 229) (33, 27) (33, 236) (38, 101) (38, 162)
(39, 45) (39, 218) (40, 55) (40, 208) (44, 65) (44, 198)
(45, 35) (45, 228) (47, 81) (47, 182) (48, 60) (48, 203)
(49, 123) (49, 140) (51, 64) (51, 199) (57, 25) (57, 238)
(58, 5) (58, 258) (59, 6) (59, 257) (60, 123) (60, 140)
(61, 52) (61, 211) (66, 34) (66, 229) (67, 119) (67, 144)
(68, 74) (68, 189) (69, 108) (69, 155) (72, 85) (72, 178)
(74, 4) (74, 259) (75, 25) (75, 238) (77, 116) (77, 147)
(78, 53) (78, 210) (81, 0) (82, 27) (82, 236) (83, 114)
(83, 149) (87, 61) (87, 202) (88, 91) (88, 172) (99, 79)
(99, 184) (103, 131) (103, 132) (108, 83) (108, 180) (110, 130)
(110, 133) (111, 77) (111, 186) (112, 44) (112, 219) (115, 59)
(115, 204) (116, 125) (116, 138) (117, 18) (117, 245) (118, 106)
(118, 157) (123, 23) (123, 240) (127, 2) (127, 261) (131, 25)
(131, 238) (132, 70) (132, 193) (134, 29) (134, 234) (137, 107)
(137, 156) (138, 29) (138, 234) (139, 23) (139, 240) (141, 109)
(141, 154) (142, 26) (142, 237) (143, 37) (143, 226) (144, 69)
(144, 194) (145, 115) (145, 148) (146, 97) (146, 166) (147, 94)
(147, 169) (148, 27) (148, 236) (150, 129) (150, 134) (152, 124)
(152, 139) (154, 123) (154, 140) (157, 100) (157, 163) (159, 102)
(159, 161) (162, 104) (162, 159) (166, 34) (166, 229) (169, 107)
(169, 156) (170, 130) (170, 133) (173, 90) (173, 173) (174, 109)
(174, 154) (175, 20) (175, 243) (180, 122) (180, 141) (181, 59)
(181, 204) (182, 110) (182, 153) (184, 43) (184, 220) (185, 127)
(185, 136) (186, 119) (186, 144) (188, 70) (188, 193) (189, 81)
(189, 182) (190, 64) (190, 199) (192, 15) (192, 248) (194, 35)
(194, 228) (195, 7) (195, 256) (196, 116) (196, 147) (199, 2)
(199, 261) (200, 2) (200, 261) (206, 70) (206, 193) (207, 117)
(207, 146) (208, 24) (208, 239) (210, 79) (210, 184) (211, 109)
(211, 154) (216, 4) (216, 259) (217, 79) (217, 184) (218, 108)
(218, 155) (219, 118) (219, 145) (220, 107) (220, 156) (221, 33)
(221, 230) (222, 58) (222, 205) (223, 50) (223, 213) (224, 9)
(224, 254) (226, 99) (226, 164) (228, 111) (228, 152) (230, 59)
(230, 204) (236, 4) (236, 259) (239, 108) (239, 155) (240, 31)
(240, 232) (242, 72) (242, 191) (245, 48) (245, 215) (246, 130)
(246, 133) (249, 98) (249, 165) (251, 75) (251, 188) (253, 116)
(253, 147) (254, 29) (254, 234) (259, 14) (259, 249) (260, 51)
(260, 212)
```
some point P  = (1, 23), 2P = (87, 61)
some point Q = (1, 240), P+Q = (0, 0)
P += Q = (0, 0)
P += P = 2P = (87, 61)

EC message encryption:
G = (148, 27), order(G) is 15
A's public key Pa = 51*(148, 27) = (3, 89)
B's public key Pb = 212*(148, 27) = (61, 52)
J's public key Pj = 153*(148, 27) = (195, 256)


Plain text message from Alice to Bob: (10, 89)
Encrypted message from A to B = {Pa,c1,c2} = {(3, 89), 240, 222}

        B's decrypted message from A = (10, 89)

J's decrypted message from A = (93, 174)


