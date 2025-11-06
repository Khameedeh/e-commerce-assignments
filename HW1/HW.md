# 📊 Simulation of Price and Advertisement Competition in an Online Market using Social Networking and the Effect of Game Theory

**Deadline:** 1404.08.19 (Iranian Calendar Date)

---

## 🎯 Approach and Scenario

Assume an **online market** like Amazon or Digikala where **two sellers** offer **similar products**. Each seller must make two decisions:
1.  **Reducing the product price**.
2.  **Allocating a budget for advertisements**.

### Description

* Assume $p$ is the product price. By reducing the price, more customers can be attracted, but the final profit from the product sale will be lower.
* With more advertising, a larger number of customers can be reached, ultimately leading to higher sales, but advertising is costly.
* Customers select a product based on a combination of:
    * Price
    * Level of advertising
    * **Social influence** (recommendations from other customers or influencers)

### General Overview

In this project, you must **simulate a simple online market** where several sellers compete to sell a similar product.

Each seller decides:
1.  What price to set for their product.
2.  How much to spend on advertising, especially **social network advertising**.

Customers make their purchase decision from one of the sellers based on three factors:
* The product price.
* The amount of advertising.
* The **influence of other buyers** (recommendations and comments from other users).

You must use the concepts of **Game Theory** to simulate the sellers' behavior and find the **Nash Equilibrium** for price and advertising.

---

## Task I - Data Preparation

The dataset can be downloaded from this link (link not provided in the source).

### Dataset Description

The dataset columns are, in order:
* `Invoice` (Invoice Number)
* `StockCode` (Item Code)
* `Description` (Item description, which can be considered the product name)
* `Quantity` (Quantity purchased)
* `InvoiceDate` (Invoice date)
* `Price` (Unit price)
* `Customer ID` (Customer ID)
* `Country` (Country)

### Pre-processing

* Perform an initial review and pre-process the data. For example, remove **null data**, **duplicate rows**, or **negative values**.
* **Note on Duplicates:** The dataset includes similar items (similar codes and descriptions), and this issue can be very helpful for implementing the seller simulator. Therefore, **only remove identical (fully repeated) rows, not similar items**.
* In this section, you can review the **average price** and the **quantity purchased** for each item, disregarding which seller offered it.
* The goal is an initial overview of the data.

---

## Task II - Modeling Sellers, Demand Function, and Profit

Since seller names are not mentioned in this dataset, you must use strategies to **categorize the data** to create **hypothetical sellers** and implement Game Theory for sellers with **similar products**.

### Hypothetical Sellers

* By reviewing the data, you will find that similar products have been offered at **different prices** in this online store.
* You can define **two or three hypothetical sellers**.
* Each seller has the following features:
    * **Fixed production cost ($\text{cost}$)** (e.g., 5 or 10 monetary units).
        * **Note:** The provided dataset only contains sales information ($\text{Price}$ and $\text{Quantity}$) and lacks production cost. A **fixed value** must be assumed to enable profit analysis and dynamic behavior modeling.
    * **Selling price ($\text{p}$)**.
    * **Advertising budget ($\text{m}$)**.

### Demand Function

Define a function for each seller to calculate the demand ($\text{D}$) based on price, advertising, and social influence.

The demand function for seller $i$ is:
$$D_{i}=\text{base demand}+(\alpha\times m_{i})+(\beta\times(p_{i}-p_{j}))+(\gamma\times \text{influence score})$$

Where:
* $\text{base demand}$: The base demand defined without advertising or network influence.
* $\alpha$: The impact of the advertising budget ($\text{m}$) on demand.
* $\beta$: Demand sensitivity to the price difference $(p_{i}-p_{j})$.
* $\gamma$: The impact of the network score (social influence).

### Profit Function

Calculate the profit. The goal here is to create a profit function for each seller (player) in the game.

The profit function for seller $i$ is:
$$Profit_{i}=(p_{i}-\text{cost})\times D_{i}-m_{i}$$

---

## Task III - Game Simulation and Finding Equilibrium

Use **iterations (loops)** to update the price and advertising of each seller to find the **best response** to the competitor.

The **Nash Equilibrium** is reached when **no seller has an incentive to change their strategy**.

---

## Task IV - Adding Social Influence

* Build a **customer network** using the **NetworkX** library.
* Designate some customers as **influencers** with a higher influence coefficient.
* Incorporate the **total network influence coefficient** into the demand model.
* Analyze how the sellers' **prices and profits change** if social influence (e.g., word-of-mouth advertising) increases.

---

## Task V - Visualization

Plot the following using **Seaborn** or **Matplotlib**:
* Changes in **profit** relative to **price and advertising**.
* Displaying the **Nash Equilibrium** on a **two-dimensional graph**.
* The **impact of the social network** on increased sales.

### Tools and Submission

* **Recommended Packages:** Pandas, Numpy, networkX, Matplotlib/Seaborn.
* You can write your code in **Jupyter Notebook/Lab, Colab**, or as a modular script in any editor you are comfortable with.
* **Submission:** Compress the final code(s) along with a **report file** explaining the process and solution into a **zip file**.
* **Email Subject Naming Convention:** Name the compressed file and the email subject as `name_familyname_stdID e-commerce hw1`.
* **Submission Address:** `yadollahisamin4@gmail.com`.
* **GitHub Option:** If the code is hosted on GitHub, simply write the project address in the report file and **only send the report file**.

**Good luck!**