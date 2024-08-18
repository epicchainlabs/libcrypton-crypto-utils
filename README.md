# libcrypton-crypto-utils

**libcrypton-crypto-utils** is a sophisticated C++ cryptography library tailored for the EpicChain blockchain ecosystem. This library forms an integral part of the **libcrypton** suite, delivering a comprehensive set of cryptographic utilities crucial for secure and efficient blockchain operations.

## 🚀 Overview

**libcrypton-crypto-utils** is meticulously engineered to provide robust cryptographic functions essential for safeguarding data integrity and securing transactions within the EpicChain ecosystem. Whether you're developing blockchain applications, implementing security protocols, or building cryptographic solutions, this library offers the tools you need to achieve high standards of security and performance.

### 🔑 Key Features

- **Encryption and Decryption:** Implement secure encryption and decryption using both symmetric (e.g., AES) and asymmetric (e.g., RSA) algorithms. This ensures the confidentiality and protection of sensitive data.
- **Hashing Functions:** Compute cryptographic hashes with algorithms such as SHA-256, SHA-3, and more. This is vital for data integrity checks, digital signatures, and various security protocols.
- **Key Management:** Effortlessly generate and manage cryptographic keys, supporting multiple formats and algorithms, essential for securing communications and transactions.
- **Data Encoding:** Efficiently convert between binary data and encoding formats like Base64 and Hex, facilitating seamless data processing and interchange.
- **Random Number Generation:** Produce cryptographically secure random numbers, crucial for key generation and other cryptographic processes requiring randomness.
- **Padding Schemes:** Apply and manage padding for data to meet the block size requirements of various encryption algorithms, ensuring compatibility and security.

## 📦 Getting Started

To explore and utilize the capabilities of **libcrypton-crypto-utils**, you can use the `crypdev` command-line tool included with the library. Below are detailed instructions to get started.

### 🔧 Building the Library and Tool

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/epicchainlabs/libcrypton-crypto-utils.git
   cd libcrypton-crypto-utils
   ```

2. **Install Dependencies:**
   
   **For Linux:** Ensure you have the necessary dependencies such as `openssl` and `gtest`. These are managed as submodules.

   - Initialize and update submodules:
     ```bash
     git submodule update --init --recursive
     ```
   - Install `libgmp-dev` for C++ native implementation:
     ```bash
     sudo apt-get install libgmp-dev
     ```

3. **Build the Library and Tool:**

   ```bash
   mkdir build
   cd build
   cmake ..
   make
   ```

   This will compile the library and build the `crypdev` tool, placing the executable in `./bin/crypdev`.

### 🛠️ Using `crypdev`

`crypdev` is a powerful command-line tool that allows you to interact with the cryptographic functions provided by **libcrypton-crypto-utils**. Here's a glimpse of what you can do with it:

- **Hashing Data:**
  
  ```bash
  ./bin/crypdev
  ```

  ```
  > hash sha256 ""
  hash: e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
  ```

- **Generating Keys:**

  ```bash
  > set ecc secp256r1
  CURVE SET TO 'secp256r1'

  > gen ecc keypair
  public key (compressed format): 037c50d797720fefe9194ecd5b4ef3c25b3791abb45639aa8453d110bae08a945a
  private key: 13043155bf3e00b6e6352ffafba9f7fa96704de08c7db2fe810a92d644199258
  ```

- **Signing and Verifying Data:**

  ```bash
  > sign ecc 4f7f56c979e2fafbe26c5d9164066ea581b4e08a52805ca377d573a853f0aa5e hash 9ec1171a37169a9e4b38726127730d64bed872f7840afeaf54028834e531e2d89a8d269f78eb426628f6cc3dc3ad99a2a43b
  signature: 7b6d7a7b0738f98bfcb7f94bcc7f5e4c4dd3469d321235d52117711096360e8eb133d42831f01a603d94574b626eb68b2d3686d7e75433b8d69874bc4f3948ce

  > verify ecc 02bff10e1aa6b544fd9fc07b28488425931e6a0d9c44b5f3fd6b7c2f489a9987ad 7b6d7a7b0738f98bfcb7f94bcc7f5e4c4dd3469d321235d52117711096360e8eb133d42831f01a603d94574b626eb68b2d3686d7e75433b8d69874bc4f3948ce hash 9ec1171a37169a9e4b38726127730d64bed872f7840afeaf54028834e531e2d89a8d269f78eb426628f6cc3dc3ad99a2a43b
  verification result: 1
  ```

- **Direct Command Execution:**

  ```bash
  ./bin/crypdev -c "rand 5 ; hash sha256 0x0001 ; rand 10"
  d070440077
  1e52f7557c
  635c59ca7d16aab29eb6
  ```

  Or use a script file:

  ```bash
  cat scripttest.txt
  rand 5
  hash sha256 0x0001
  rand 10

  ./bin/crypdev -f scripttest.txt
  b2c6db7ab4
  b413f47d13ee2fe6c845b2ee141af81de858df4ec549a58b7970bb96645bc8d2
  635c59ca7d16aab29eb6
  ```

## 📜 License

**libcrypton-crypto-utils** is licensed under the MIT License. The implementation of `BigIntegerGMP.cpp` is licensed under LGPLv3, due to its dependence on the GNU MP Bignum Library. For detailed licensing information, please refer to the `LICENSE` file included in this repository.

## 🌟 Contribution Guidelines

We welcome contributions to enhance **libcrypton-crypto-utils**. To contribute:

- **Report Issues:** Use the [GitHub Issues page](https://github.com/epicchainlabs/libcrypton-crypto-utils/issues) to report any bugs or request new features.
- **Submit Pull Requests:** Create pull requests for bug fixes or feature enhancements. Ensure that your contributions adhere to our coding standards and include thorough documentation.

## 🌐 Connect with Us

Engage with the **libcrypton** community and stay updated with the latest developments:

- **GitHub:** [libcrypton-crypto-utils GitHub](https://github.com/epicchainlabs/libcrypton-crypto-utils)
- **Twitter:** [@EpicChainLabs](https://twitter.com/EpicChainLabs)
- **Discord:** Join our conversations on [Discord](https://discord.com/invite/u7PmNUpSGg)

## 🚀 Explore More

Discover additional libraries and modules within the **libcrypton** suite to find comprehensive solutions for your cryptographic needs in the EpicChain blockchain ecosystem.

For detailed documentation and advanced usage, visit our [documentation page](https://github.com/epicchainlabs/libcrypton-crypto-utils/wiki).

Happy coding and secure development!

**EpicChain Security Team** (2024)
