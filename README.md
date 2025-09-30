# Cardano NCL Tracker

A real-time dashboard to track Cardano treasury withdrawals against the Net Change Limit (NCL).

## 🚀 Live Demo

You can access the live tracker here: **[https://thomas-nada.github.io/NCL-tracker/](https://thomas-nada.github.io/NCL-tracker/)**

---

## ✨ Features

* **Live On-Chain Data**: Automatically fetches and displays the latest data on page load.
* **Modern Dashboard Layout**: A clean, two-column layout with a persistent summary panel and a scrollable list of withdrawals.
* **NCL Summary**: Key metrics including **Total Withdrawn**, **Net Change Limit**, and **Remaining Allowance** are clearly displayed.
* **Progress Visualization**: An animated **progress bar** shows the percentage of the NCL that has been withdrawn.
* **Detailed Withdrawal List**: Each enacted treasury withdrawal is listed as a separate transaction. Governance actions containing multiple withdrawals are clearly marked with a **"Multi-withdrawal"** badge.
* **Advanced Sorting**: Sort the list of withdrawals by **Epoch**, **Amount**, or **Name** (alphabetical).
* **Direct On-chain Links**: Every proposal title links to its `GovAction` on Cardanoscan, while each `TxID` links to its specific transaction.
* **Informational Sub-page**: An "About" page explains the purpose of the tool and the NCL itself.

---

## ⚙️ How It Works

This tool is a single web page that performs a multi-step data-gathering process on page load:

1.  **Fetch Proposals**: It begins by querying the **Koios API** to get a complete list of governance proposals.
2.  **Filter Data**: The script isolates successful treasury withdrawals ratified within the current NCL period (Epochs 532-604).
3.  **Identify Multi-withdrawal Actions**: It inspects the list to find governance actions (`proposal_id`) that are associated with more than one withdrawal transaction.
4.  **Retrieve Metadata**: For each unique proposal, it follows a metadata URL to a file on the **InterPlanetary File System (IPFS)** to retrieve the official proposal title.
5.  **Calculate, Sort & Display**: Finally, it calculates the summary, sorts the list (defaulting to the newest epoch first), and renders all the data on the dashboard.

---

## 🛠️ Technologies Used

* HTML5
* Tailwind CSS
* JavaScript (ES6+)
* Koios API
* IPFS
