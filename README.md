# Data-Analyst-Portfolio
file:///C:/Users/DELL/OneDrive/Harish%20Data%20Analyst%20Portfolio.pdf
-- Find high-risk customers
SELECT
customer_id,
loan_amount,
income,
loan_status,
CASE
WHEN loan_status = 'Default' THEN 'High Risk'
ELSE 'Low Risk'
END AS risk_category
FROM loans;

-- Default rate
SELECT
COUNT(CASE WHEN loan_status = 'Default' THEN 1 END) * 100.0 / COUNT(*) AS default_rate
FROM loans;
