# TxExplain (Mezo Edition)

**Translating the complexity of Mezo DeFi into human-readable insights.**

### Problem
For most users, interacting with decentralized finance (DeFi)—specifically borrowing and lending protocols on networks like Mezo—is an exercise in deciphering hex codes and raw numbers on a block explorer. Understanding the relationship between collateral, debt, and risk usually requires manual calculation or deep technical knowledge of the `TroveManager` and `PriceFeed` contracts. This opacity creates a barrier to entry for new participants in the MUSD ecosystem.

### Solution
TxExplain is a lightweight, serverless translation layer developed as a Cloudflare Worker. Instead of showing raw transaction logs, it interprets the on-chain state and provides a natural language summary. Specifically for Mezo, it targets borrower addresses to instantly surface critical financial metrics: current collateral, outstanding debt, accumulated interest, and overall risk profile.

### Fitting the Listing: Mezo Wave 2
| Requirement | TxExplain Feature |
| :--- | :--- |
| **MUSD/MEZO Integration** | Directly integrates with Mezo's `TroveManager` and `PriceFeed` contracts to explain the movements and states of MUSD positions. |
| **Deployment (Mezo/Base/ETH)** | Deployed as a high-performance Cloudflare Worker with a dedicated endpoint for Mezo Testnet. |
| **Wave 2 Progress** | Evolved from a general EVM transaction explainer to a specialized Mezo-aware agent capable of reading specific borrowing protocol logic. |
| **Open Source** | Full codebase available under MIT license. |
| **Live Access** | Fully operational read-only API/Web interface. |

### Architecture
- **Frontend/API:** Cloudflare Workers (Edge Runtime).
- **Blockchain Interaction:** Read-only RPC calls to Mezo Testnet.
- **Logic:** Custom parser mapping `TroveManager` function outputs to human-readable templates based on asset types (BTC/MUSD).
- **License:** MIT.

### Try It
- **Mezo Specific Explorer:** https://txexplain-mezo.muhammetkarakurt1234.workers.dev
- **General EVM Explorer:** https://txexplain.muhammetkarakurt1234.workers.dev

### Status & Roadmap
**Live Today ✅**
- Basic EVM transaction explanation.
- Mezo Testnet Extension: Fetching Collateral, Debt, Interest, and Risk for borrower addresses.
- Deployment on Cloudflare Workers global edge network.

**TO BUILD 🛠️**
- **Real-time Alerting:** Notify users when their risk level changes based on `PriceFeed` updates.
- **Multi-Transaction Narrative:** Ability to group multiple transactions into a "story" (e.g., "User deposited BTC, borrowed MUSD, and paid interest").

### Limitations
- **Read-Only:** Does not facilitate transactions; purely for analysis.
- **Metrics:** Currently operates as a utility tool without user tracking or analytics.
