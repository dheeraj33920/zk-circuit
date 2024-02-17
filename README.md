# zk-circuit

Here's a basic outline of what your README file might look like for the Final Challenge:

---

## Description
This project aims to implement a circuit in circom, compile it to generate circuit intermediaries, generate a proof using specific inputs, deploy a solidity verifier to either the Sepolia or Mumbai Testnet, and finally, call the verifyProof() method on the deployed contract to assert the output as true.

## Prerequisites
Before attempting to run the project, ensure you have the following prerequisites installed:
- Node.js
- Circom
- SnarkJS
- Solidity compiler (solc)
- Truffle

## Installation
1. Clone the repository to your local machine.
2. Install dependencies by running `npm install`.

## Usage
### 1. Writing the Circuit
Edit the `circuit.circom` file to define the circuit according to your requirements.

### 2. Compiling the Circuit
Compile the circuit using Circom:
```
circom circuit.circom -o circuit.json
```

### 3. Generate Circuit Intermediaries
Generate the circuit intermediaries:
```
snarkjs setup --circuit circuit.json
```

### 4. Generating Proof
Generate a proof using inputs A=0 and B=1:
```
snarkjs calculatewitness -w witness.wtns -i input.json -o public.json
snarkjs prove --witness witness.wtns --pk proving_key.json --public public.json --proof proof.json
```

### 5. Deploying Solidity Verifier
Deploy the Solidity verifier contract to either the Sepolia or Mumbai Testnet using Truffle.

```
truffle migrate --network <network_name>
```

Replace `<network_name>` with either Sepolia or Mumbai Testnet configuration from your `truffle-config.js`.

### 6. Calling the verifyProof() Method
Call the `verifyProof()` method on the deployed contract and assert the output as true.


Feel free to customize this README according to the specifics of your project and add more detailed instructions or explanations where necessary.
