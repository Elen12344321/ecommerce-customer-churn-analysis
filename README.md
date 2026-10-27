# Customer Churn Prediction and Behavioral Analytics (500K+ Dataset)

## Overview and Business Problem
In a highly competitive e-commerce environment, retaining existing customers is critical for ensuring stable revenue. Acquiring new buyers costs significantly more than keeping current ones, and losing every fifth customer (a 20.7% overall churn rate) directly impacts financial performance.

The primary objective of this project is to build an analytical and machine learning pipeline to identify users prone to churning before they leave the platform, as well as to uncover key behavioral drivers behind customer attrition to support proactive retention strategies.

---

## Dataset Description
The analysis utilizes the Customer Churn Prediction Dataset V2 (500K), a large-scale synthetic relational dataset designed for machine learning and business intelligence practice.

- **Scale:** 500,000 unique customers and 1,000,000 orders, totaling over 3 million records across six interconnected tables.
- **Relational Structure:**
  - `customers.csv`: Customer demographic and profile information.
  - `orders.csv`: Purchase history and transaction details.
  - `engagement.csv`: Website and mobile app activity metrics.
  - `payments.csv`: Payment history and subscription records.
  - `support_tickets.csv`: Customer support interactions and service metrics.
  - `customer_summary.csv`: Aggregated customer metrics with an ML-ready churn target.

---

## Methodology and Project Scope
- **Exploratory Data Analysis (EDA):** Investigated behavioral patterns, correlations, and high-risk segments (`At Risk`, `New`).
- **Feature Engineering:** Developed custom business metrics to enhance model performance:
  - `avg_spend_per_order`: Average transaction value per customer.
  - `days_per_order`: Estimated purchase interval frequency.
  - `points_per_dollar`: Loyalty program engagement ratio.
  - `high_return_flag`: Binary indicator for return rates exceeding 20%.
- **Predictive Modeling:** Trained and evaluated Logistic Regression and Random Forest classifiers using stratified data splitting and feature scaling.
- **Business Insights Translation:** Converted model outputs into actionable strategies for marketing and CRM teams.

---

## Key Results and Performance

### Model Comparison
| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Logistic Regression** | 0.9995 | 0.9990 | 0.9988 | 0.9989 | 1.0000 |
| **Random Forest** | 0.9927 | 0.9820 | 0.9828 | 0.9824 | 0.9997 |

### Main Behavioral Drivers
1. **Inactivity Duration (`last_purchase_days` and `days_per_order`):** Account for over 54% of predictive importance. An inactivity period exceeding 300 days serves as the main indicator of imminent churn.
2. **Product Quality and Returns (`return_rate`):** High return rates (20-21% in the churned group compared to 7% for active users) rank among the top risk factors.
3. **Segment Vulnerability:**
   - The `At Risk` segment shows a critical 67.0% churn rate.
   - The `New` customer segment exhibits a 47.6% churn rate, highlighting weaknesses in early onboarding.

---

## Actionable Business Recommendations

1. **Inactivity Management:** Set up automated CRM triggers and targeted discounts when a customer's order interval doubles their historical median.
2. **Return Audits and Support:** Audit product categories with return rates above 20% and provide proactive support to customers who make frequent returns.
3. **Onboarding Optimization:** Introduce welcome bonus sequences during the first 30 days post-registration to lower new user churn by 15-20%.
4. **Targeted Reactivation:** Allocate dedicated marketing budgets specifically for the `At Risk` segment to run high-ROI recovery campaigns.

---

## Tech Stack
- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn, KaggleHub
- **Environment:** Jupyter Notebook / Google Colab
