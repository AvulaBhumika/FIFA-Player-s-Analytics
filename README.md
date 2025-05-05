# FIFA Player's Analytics

![image](https://github.com/user-attachments/assets/554a3d3e-ed85-4998-8706-0886aacbaf0b)


A data-driven exploration of 18,000+ football players using clustering (K-Means) and PCA. Analyzes skill distributions, wage trends, and peak performance age to identify player archetypes (attackers vs defenders). Includes visualizations for country-wise talent distribution and age-rating relationships.

## **Task 1: Complete Data Analysis Report**  

### **1. Dataset Overview**  
- **Total records**: 18,000+ players  
- **Features**: Player demographics, contract info, skill ratings, physical traits, positional stats  
- **Objective**: Analyze football player skills and group similar profiles  

### **2. Data Preprocessing**  
- Removed null rows in key skill columns  
- Scaled numeric skill features using `StandardScaler`  
- **Feature selection for clustering**:  
  - `pace`, `shooting`, `passing`, `dribbling`, `defending`, `physic`  

### **3. Descriptive Statistics**  
- **Age Range**: 16 to 42  
- **Overall Rating**: Min 48, Max 94  
- **Player Value Range**: €20K to €118M  

---  

## **Task 2: Clustering Football Players Based on Skill Attributes**  

### **Step 1: Unsupervised Learning (K-Means Clustering)**  
- Selected skill attributes: `pace`, `shooting`, `passing`, `dribbling`, `defending`, `physic`  
- Used `StandardScaler` to normalize input  

### **Step 2: Finding Optimal Clusters**  
- **Metric**: Silhouette Score  
- Tested range: `K = 2` to `10`  
- **Optimal number of clusters**: **2**  

### **Step 3: Cluster Profiles**  

| Cluster | Pace  | Shooting | Passing | Dribbling | Defending | Physic |  
|---------|-------|----------|---------|-----------|-----------|--------|  
| 0       | 71.89 | 60.17    | 61.79   | 68.08     | 47.07     | 63.73  |  
| 1       | 60.09 | 38.00    | 48.96   | 52.44     | 59.67     | 66.95  |  

- **Cluster 0**: Attack-oriented (higher pace, dribbling, shooting)  
- **Cluster 1**: Defense-heavy (higher defending, physical strength)  

### **Step 4: Visualizing Clusters with PCA**  
- PCA reduced dimensions to 2D  
- Scatter plot showed clear separation between clusters  

![image](https://github.com/user-attachments/assets/60e2c59c-1301-4e99-a423-af4c12b2dacc)
  

---  

## **Task 3: Country-Wise Player Representation**  

![image](https://github.com/user-attachments/assets/ed433462-b3b7-4861-9421-8280a74368d2)

**Insight**: European countries dominate player production, especially England, Germany, and Spain.  

---  

## **Distribution of Overall Rating vs Age**  

![image](https://github.com/user-attachments/assets/05aebe68-aa43-4661-b5b1-1f5e50aaf945)

**Visual Summary**  
- **Blue Dots**: Individual players' overall ratings by age.  
- **Red Line**: Smoothed trend line (LOWESS/rolling average).  

**Key Insights**  
- **Peak Performance Age**: Players peak around **26–30 years**.  
- **Youth Development**: Higher variation in ratings for players under 22.  
- **Late-Career Decline**: Gradual but non-uniform (elite players maintain high ratings).  

---  

## **Offensive Players vs Wage**  

![image](https://github.com/user-attachments/assets/7c4278e1-72db-4bf9-b851-4ec0978e7cdf)

**Insights**  
1. **Strikers (ST) command the highest wages** (primary goal-scorers).  
2. **Left Wingers (LW)** are highly paid but less than ST (dual role in scoring/creating).  
3. **Right Wingers (RW)** earn significantly less (possible tactical or depth reasons).  

---  

## **Additional Analytics**  

### **1. Wage vs. Overall Skill by Position**  
![image](https://github.com/user-attachments/assets/e797d0b4-1831-4cbd-b79b-81aac3dc2d55)

### **2. Age vs. Potential: Identifying Rising Stars**  
![image](https://github.com/user-attachments/assets/46e62732-e809-4dd5-9ec9-611d23f57a77)
 

### **3. Trait Distribution Across Top Players**  
![image](https://github.com/user-attachments/assets/a721cb23-33ba-494c-92f0-a3f6f75b05e8)

---  

## **Challenges & Solutions**  
| Challenge                        | Solution                                  |  
|----------------------------------|-------------------------------------------|  
| Imbalanced target classes        | Used class weighting + SMOTE oversampling |  
| High dimensionality in clustering | PCA for reduction + visualization         |  
| Feature selection                | Focused on core skill attributes          |  
| Missing data                     | Dropped rows with null skill values       |  

---  

## **Conclusion**  
- K-Means clustered players into **attack-focused** vs. **defense-focused** groups.  
- PCA validated cluster separability.  
- Country-level insights highlight talent origins (Europe dominates).  
- Foundation for scouting, performance tracking, and club strategy.  

 **~AVB**
