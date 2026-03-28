# 🛍️ Customer Segmentation using RFM & KMeans Clustering

_A machine learning project that segments retail customers based on purchasing behavior using RFM (Recency, Frequency, Monetary) analysis and KMeans clustering. The system analyzes customer transactions to identify VIP, Regular, and Inactive customers to support better business decision making._

---

## 📌 Table of Contents
- <a href="#overview">Overview</a>
- <a href="#problem-statement">Problem-Statement</a>
- <a href="#dataset">Dataset</a>
- <a href="#tools--technologies">Tools & Technologies</a>
- <a href="#project-structure">Project Structure</a>
- <a href="#data-cleaning">Data Cleaning</a>
- <a href="#feature-engineering">Feature Engineering</a>
- <a href="#exploratory-data-analysis">Exploratory Data Analysis</a>
- <a href="#rfm-analysis">RFM Analysis</a>
- <a href="#model-building">Model Building</a>
- <a href="#customer-segmentation">Customer Segmentation</a>
- <a href="#cluster-evaluation">Cluster Evaluation</a>
- <a href="#business-insights">Business Insights</a>
- <a href="#how-to-run-this-project">How to Run This Project</a>
- <a href="#future-improvements">Future Improvements</a>
- <a href="#author--contact">Author & Contact</a>

---

<h2><a class="anchor" id="overview"></a>Overview</h2>

Customer segmentation is a key technique used by businesses to understand their customers and personalize marketing strategies.

This project performs **customer segmentation using RFM analysis and KMeans clustering** on an online retail dataset. The system analyzes customer purchase behavior and groups customers into different segments such as:

- VIP Customers
- Super VIP Customers
- Regular Customers
- Inactive Customers

By identifying these segments, businesses can improve marketing campaigns, increase customer retention, and optimize sales strategies.

---

<h2><a class="anchor" id="problem-statement"></a>Problem-Statement</h2>

Retail businesses often have thousands of customers, but not all customers contribute equally to revenue.

The goal of this project is to:

- Identify high-value customers.
- Segment customers based on purchasing behavior.
- Apply RFM analysis to understand customer value.
- Use clustering algorithms to group similar customers.
- Generate business insights that help companies improve customer targeting and retention.

---

<h2><a class="anchor" id="dataset"></a>Dataset</h2>

The project uses the **Online Retail Dataset**, which contains transactional data from an online retail store.

Dataset features include:

- InvoiceNo
- StockCode
- Description
- Quantity
- InvoiceDate
- UnitPrice
- CustomerID
- Country

Dataset location:

```
dataset/raw/online_retail.csv
```

The dataset contains customer purchase transactions including product information, purchase dates, and prices.

---

<h2><a class="anchor" id="tools--technologies"></a>Tools & Technologies</h2>

Programming & Libraries
- Python
- Pandas
- NumPy
- Scikit-Learn

Data Visualization
- Matplotlib
- Seaborn

Machine Learning
- KMeans Clustering
- RFM Analysis
- StandardScaler
- Silhouette Score

Development Environment
- Jupyter Notebook (VS Code Jupyter Extension)

Version Control
- Git
- GitHub

---

<h2><a class="anchor" id="project-structure"></a>Project Structure</h2>

```
sentiment_analysis/
│
├── dataset/
│   └── raw/
│       └── online_retail.csv
│
├── notebook/
│   └── sentiment_analysis.ipynb
│
├── output/
│   ├── customer_segments.csv
│   └── rfm_clusters.csv
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

<h2><a class="anchor" id="data-cleaning"></a>Data Cleaning</h2>

Data cleaning is performed to ensure the dataset is ready for analysis.

Key cleaning steps include:

1. Handling Missing Values
   - Remove rows where **CustomerID** is missing.
   - Missing descriptions are analyzed and cleaned.

2. Removing Duplicates
   - Duplicate transactions are removed to ensure data quality.

3. Data Type Conversion
   - Convert **InvoiceDate** to datetime format for time-based analysis.

These steps ensure that the dataset is consistent and reliable for further analysis.

---

<h2><a class="anchor" id="feature-engineering"></a>Feature Engineering</h2>

New features are created to help analyze customer behavior.

TotalPrice feature is created:

```
TotalPrice = Quantity × UnitPrice
```

This feature represents the **total revenue generated per transaction**.

---

<h2><a class="anchor" id="exploratory-data-analysis"></a>Exploratory Data Analysis</h2>

EDA helps understand customer purchasing patterns.

Key analyses performed:

1. Top Buyers
   - Identify customers with the highest total spending.

2. Country-wise Sales
   - Analyze which countries generate the most revenue.

3. Product Popularity
   - Identify the most frequently purchased products.

Visualizations used:

- Bar Charts
- Distribution Plots
- Scatter Plots

---

<h2><a class="anchor" id="rfm-analysis"></a>RFM Analysis</h2>

RFM analysis is a widely used method to evaluate customer value.

RFM consists of:

Recency → How recently a customer made a purchase  
Frequency → How often a customer makes purchases  
Monetary → How much money a customer spends

RFM metrics are calculated for each customer using transaction data.

---

<h2><a class="anchor" id="model-building"></a>Model Building</h2>

Before applying clustering, the RFM features are scaled.

StandardScaler is used to normalize the data so that all features contribute equally to the clustering algorithm.

To determine the optimal number of clusters, the **Elbow Method** is applied.

The Elbow Method plots the **Within Cluster Sum of Squares (WCSS)** for different numbers of clusters.

The optimal cluster count is chosen where the curve forms an elbow.

---

<h2><a class="anchor" id="customer-segmentation"></a>Customer Segmentation</h2>

KMeans clustering is applied to the scaled RFM data.

Customers are grouped into **four clusters**:

Cluster Names:

- VIP Customers
- Super VIP Customers
- Regular Customers
- Inactive Customers

Each cluster represents a group of customers with similar purchasing behavior.

---

<h2><a class="anchor" id="cluster-evaluation"></a>Cluster Evaluation</h2>

Cluster quality is evaluated using **Silhouette Score**.

Silhouette Score measures how well each customer fits within its cluster compared to other clusters.

Higher scores indicate better clustering performance.

---

<h2><a class="anchor" id="business-insights"></a>Business Insights</h2>

Customer segmentation provides several valuable insights:

- Identify **high-value VIP customers** who generate most revenue.
- Detect **inactive customers** who may require marketing campaigns.
- Understand purchasing behavior across customer segments.
- Discover **popular products** within each customer group.

These insights can help businesses design better marketing strategies and increase revenue.

---

<h2><a class="anchor" id="how-to-run-this-project"></a>How to Run This Project</h2>

1. Clone the repository:

```bash
git clone https://github.com/yourusername/customer-segmentation-rfm.git
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open the notebook:

```
notebook/sentiment_analysis.ipynb
```

4. Run the notebook cells to:

- Clean the dataset
- Perform RFM analysis
- Train the clustering model
- Generate customer segments

5. Output files will be saved in:

```
output/customer_segments.csv
output/rfm_clusters.csv
```

---

<h2><a class="anchor" id="future-improvements"></a>Future Improvements</h2>

- Add interactive dashboards using Power BI or Tableau
- Apply advanced clustering algorithms (DBSCAN, Hierarchical Clustering)
- Deploy segmentation pipeline as an automated system
- Use time-based behavioral segmentation
- Integrate recommendation systems for targeted marketing

---

<h2><a class="anchor" id="author--contact"></a>Author & Contact</h2>

**Ritresh Kumar**  
BCA Student | Aspiring Data Scientist

Skills:
- Python
- Machine Learning
- Data Analysis
- Customer Analytics
- Deep Learning

📧 Email: ritresh273@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/feed/)  
🔗 [GitHub](https://github.com/Ritresh/Ritresh)
