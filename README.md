# Football Tournament Smart Contract

## Overview

The Football Tournament smart contract is a simple Ethereum-based contract designed to manage a football tournament and declare a gold medalist footballer based on their total goals scored. The contract keeps track of footballers and their respective goal counts, updating the gold medalist when a footballer surpasses the current leader's goal count.

## Features

- **Declare Medalist Footballer:** Footballers can be declared as medalists by specifying their address and total goals.
- **Gold Medal Tracking:** The contract keeps track of the gold medalist based on the highest total goals scored.
- **Event Emission:** An event (`NewMedalistFootballer`) is emitted whenever a new gold medalist is declared.

## Getting Started

### Usage

1. Deploy the `FootballTournament` contract on an Ethereum network.

2. Call the `declareMedalistFootballer` function to declare a footballer as a medalist by providing their address and total goals.

3. Monitor the emitted events to stay updated on the gold medalist changes.

Example usage:

```solidity
// Deploy contract
const footballTournament = await FootballTournament.deploy();

// Declare medalist footballer
await footballTournament.declareMedalistFootballer(player1, 20);

// Event listener for new medalist
footballTournament.on("NewMedalistFootballer", (footballer, totalGoals) => {
  console.log(`New Gold Medalist: ${footballer} with ${totalGoals} goals`);
});
```

## Functions

### `declareMedalistFootballer`

```solidity
function declareMedalistFootballer(address footballer, uint totalGoals) public
```

Declares a footballer as a medalist by providing their address and total goals. If the footballer surpasses the current gold medalist's total goals, a new gold medalist is declared.

## Variables

### `goldMedalist`

```solidity
address public goldMedalist;
```

Stores the address of the current gold medalist.

### `footballerGoals`

```solidity
mapping(address => uint) public footballerGoals;
```

Maps footballers' addresses to their respective total goals.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
