# Fedimint Footprints: Exploring What's Visible | Brad Stachurski | bitcoin++ ecash edition | October 2024 | Berlin, Germany
A brief exploration of publicly available data from Fedimints using an open-source tool, Fedimint Observer. Recorded in Berlin, in October 2024 during bitcoin++ ecash edition.

[![Fedimint Footprints: Exploring What's Visible](https://img.youtube.com/vi/RMi0SYS8GFU/0.jpg)](https://www.youtube.com/watch?v=RMi0SYS8GFU)

## Video Summary generated by AI:

Fedimint Footprints: An Introduction to Fedimint Observer and Data Exploration

In this presentation, Brad, a contributor to Fedimint since August 2023, takes the audience through an in-depth exploration of Fedimint Observer, a tool that provides visibility into the operations of a Fedimint federation. The session covers various aspects, including setting up the tool, interacting with live data, and delving into transaction details like deposits, withdrawals, and the construction of UTXOs (Unspent Transaction Outputs).

### Introduction to Fedimint and Fedimint Observer
Fedimint is a federated mint system that aims to offer privacy-preserving financial services built on Bitcoin and the Lightning Network. The key component of the system is the federation, a group of trusted parties that operate together to manage a shared multi-signature wallet. Users can deposit and withdraw Bitcoin through this federation while maintaining privacy.

Fedimint Observer acts like a specialized block explorer but focuses on observing the data of a Fedimint federation. It allows users to connect to a federation using an invite code and query all publicly available endpoints. The tool is invaluable for users who want to understand the data visible to third parties and for developers identifying bugs or improving the system’s design.

### Setting Up Fedimint Observer
To begin using Fedimint Observer, users need to clone the repository, set up the server, and connect to a federation using an invite code. Brad demonstrates the connection process, emphasizing that while syncing data can take time (since most federations have over 100,000 sessions), once the data is available, users can query it for valuable insights.

### Exploring On-Chain Deposits and Withdrawals
Once connected to a federation, users can explore on-chain deposits and withdrawals:

Deposits: A wallet input is used for deposits, which involves a Pagan proof. This proof includes a Merkle proof and a transaction output that proves funds were sent to a specific tweaked address derived from the federation's multi-signature wallet descriptor. Brad walks through the process of extracting this data and analyzing the largest deposit seen on the federation.

Withdrawals: For withdrawals, users submit a pegout request, which contains a Bitcoin address and the withdrawal amount. The federations then use a Partially Signed Bitcoin Transaction (PSBT) to withdraw the Bitcoin. The tool helps track these withdrawals, showing the inputs and outputs associated with each transaction.

Brad demonstrates how to use SQL queries to extract and verify withdrawal and deposit data, providing transparency and accountability for users and developers.

### Building a View of UTXOs
The next step in the demonstration involves building a view of a federation's UTXOs—all the unspent transaction outputs associated with a federation. This process includes:

Identifying all deposits to the federation (inputs).
Extracting all change outputs and withdrawal inputs.
Creating an aggregate view of all unspent coins.
Brad walks the audience through the process of using Fedimint Observer to find all relevant data, like deposits, change outputs, and withdrawn coins, and then compiles them into a complete view of the federation’s UTXOs.

### The Importance of Privacy and Data Visibility
An essential lesson from this session is the importance of maintaining privacy within a federation. The visibility of large deposits and withdrawals can compromise a user's privacy. Brad mentions the case of a user depositing seven Bitcoin into a federation and withdrawing it shortly after, which led to visible spikes in transaction volume. To avoid such exposure, it's advisable to not make large, quick in-and-out deposits and withdrawals.

### Practical Use Cases for Fedimint Observer
Fedimint Observer has several practical applications:

Privacy Verification: Users can check what data is publicly visible when using Fedimint and ensure their transactions are as private as expected.
Bug Identification and Design Improvements: The development team uses this tool to identify bugs and potential areas for improvement, such as the coin selection algorithm.
Federation Health Monitoring: By using the tool, developers and users can track the operational status of different federations, identifying those with better uptime and fewer issues.
### Conclusion and Key Takeaways
Brad concludes the presentation by emphasizing the importance of data transparency and privacy within Fedimint. While tools like Fedimint Observer provide detailed insights into how federations work, they also highlight the need for users to be cautious about their privacy. Making large deposits and withdrawals can expose a user’s activities, undermining the privacy promises of the system.

This session provides a great foundation for understanding how Fedimint works under the hood and how tools like Fedimint Observer can be used for data exploration, privacy analysis, and system debugging.

By sharing insights into the inner workings of Fedimint, Brad encourages developers and users to explore the system, ask questions, and experiment with the available data, drawing parallels with the early days of Bitcoin when block explorers were a novel way of understanding blockchain data.