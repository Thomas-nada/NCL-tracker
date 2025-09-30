# Cardano NCL Tracker

[![Live Demo](https://img.shields.io/badge/Live-Demo-blue?style=for-the-badge&logo=githubpages)](https://thomas-nada.github.io/NCL-tracker/)

A sleek, real-time, single-page web application to track Cardano treasury withdrawals against the current Net Change Limit (NCL).



## 📜 About

This tool provides a clear, up-to-date dashboard visualizing the state of the Cardano treasury for the current NCL budgetary period (Epochs 532-604). It was built to promote transparency in on-chain governance by making complex treasury data accessible and easy to understand at a glance.

The entire application is a single `index.html` file with no external dependencies beyond CDN-hosted libraries.

---

## ✨ Features

- **Live On-Chain Data**: Automatically fetches and displays the latest data on page load.
- **Modern Dashboard Layout**: A clean, two-column layout with a summary panel and a scrollable list of withdrawals.
- **NCL Summary**: Key metrics are displayed in a simple, easy-to-read format.
- **Progress Visualization**: An animated progress bar shows the percentage of the NCL that has been withdrawn.
- **Detailed Withdrawal List**: Each enacted treasury withdrawal is listed with its name, amount, and GovAction ID.
- **External Links**: Every proposal title links directly to its entry on Cardanoscan for deeper investigation.
- **Informational Sub-page**: An "About" page explains the purpose of the tool and the NCL itself.

---

## ⚙️ How It Works

The tool performs a multi-step data-gathering process entirely on the client-side:

1.  **Fetch Proposals**: It begins by querying the **Koios API** to get a complete list of all governance proposals on the Cardano blockchain.
2.  **Filter Data**: The script filters this list to isolate only the successful treasury withdrawals that have been ratified within the specified epoch range (532-604).
3.  **Retrieve Metadata**: For each withdrawal, it checks for a metadata URL (`meta_url`) pointing to a file on the **InterPlanetary File System (IPFS)**. It then fetches this file from a public IPFS gateway to retrieve the official proposal title.
4.  **Calculate & Display**: Finally, it calculates the total withdrawn Ada, compares it to the NCL, and dynamically renders the dashboard components.

---

## 🛠️ Technologies Used

-   **HTML5**
-   **Tailwind CSS** for styling.
-   **JavaScript (ES6+)** for all logic, including API calls and DOM manipulation.
-   **Koios API** for on-chain Cardano data.
-   **IPFS** for off-chain proposal metadata.
