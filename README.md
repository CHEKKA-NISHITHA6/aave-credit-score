# Aave V2 Wallet Credit Scoring

This project generates a credit score for each wallet interacting with the Aave V2 protocol based on historical transaction behavior. The score ranges from 0 to 1000 — with higher scores indicating responsible, reliable usage, and lower scores flagging risky or exploitative behavior.

---

## 🚀 Objective

- Behavior-based credit scoring model for DeFi wallets
- Uses Aave V2 transaction-level actions (deposit, borrow, repay, etc.)
- Output: credit score between **0–1000** per wallet

---

## 📁 Project Structure

aave-credit-score/
├── data/
│   └── user_transactions.json
├── src/
│   └── score_generator.py
├── output/
│   ├── wallet_scores.csv
│   └── score_distribution.png
├── README.md
└── analysis.md

---

## ⚙️ Engineered Features

| Feature                  | Description                             |
|--------------------------|-----------------------------------------|
| total_deposits           | Total amount deposited                  |
| total_borrows            | Total amount borrowed                   |
| total_repays             | Total amount repaid                     |
| borrow_repay_ratio       | Repayments relative to borrows          |
| num_deposits             | Number of deposit actions               |
| num_liquidations         | Number of liquidation events            |
| unique_tokens_used       | Diversity of tokens used                |
| avg_time_between_actions | Activity frequency                      |
| redeem_to_deposit_ratio  | Indicator of risky churn behavior       |

---

## 🧮 Scoring Logic

The score is a weighted sum of normalized features:

- 25% – Borrow-Repay Ratio  
- 15% – Total Deposits  
- 15% – Number of Deposits  
- 15% – Token Diversity  
- 10% – Low Liquidations  
- 10% – Low Redemption Ratio  
- 10% – Frequent Activity  

Final scores are scaled to a range of 0–1000.

---

## 🧪 How to Run

Step 1: Place the Aave transaction JSON file at: data/user_transactions.json

Step 2: Run the script: python src/score_generator.py


---

## 📊 Output

- `output/wallet_scores.csv`: Wallets with assigned credit scores  
- `output/score_distribution.png`: Histogram of credit scores

---

## 📄 Deliverables

- `README.md` — method, logic, architecture  
- `analysis.md` — wallet behavior insights, score trends
