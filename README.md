# zkSNARK Circuit Guide

This guide covers the setup and deployment of a zkSNARK circuit designed to validate a specific logic gate operation. It includes steps for generating zero-knowledge circuits, proofs, and Solidity verifiers.

## Setup

### Installation

To install the required dependencies, run the following command in your project directory:

```bash
npm install
```

### Compilation

Compile the project by executing:

```bash
npx hardhat circom
```

This command generates the `out` directory, which contains circuit intermediaries and the `LogicGateCircuitVerifier.sol` contract.

### Proof Generation and Deployment

To deploy the contract and generate a proof, run the deployment script with:

```bash
npx hardhat run scripts/deploy.ts
```

This script performs the following actions:

1. Deploys the `LogicGateCircuitVerifier.sol` contract to the blockchain.
2. Generates a proof using the circuit intermediaries with the `generateProof()` function.
3. Creates calldata for the verification process using the `generateCallData()` function.
4. Verifies the proof by calling the `verifyProof()` method on the deployed Verifier contract with the generated calldata.

Running this script will deploy the Verifier contract and validate the proof against the circuit, ensuring your implementation's correctness.

To deploy the contract on the Polygon network (Amoy chain), use:

```bash
npx hardhat run scripts/deploy.ts --network amoy
```
