# Data Analysis and Visualization

This project involves analyzing and visualizing data from a dataset containing tweets with various attributes such as sentiment, age of users, country, and more. The goal is to explore sentiment distribution, demographic information, and relationships between different features and building machine learning model.


## Libraries Used

- `numpy`: For numerical operations.
- `matplotlib.pyplot`: For creating static, interactive, and animated visualizations.
- `seaborn`: For statistical data visualization.
- `pandas`: For data manipulation and analysis.
- `re`: For regular expression operations.
- `sklearn.preprocessing`: For feature scaling and encoding.
- `warnings`: To manage warnings in the code.

## Data Import

- `train.csv`: The main dataset containing the tweets and associated information.
- `test.csv`: A separate dataset for testing purposes.

## Analysis and Visualization

1. **Sentiment Distribution**

   - **Description**: Displays the distribution of sentiments in the dataset.
   - **Visualization**: A count plot of sentiments.
   - **Code**: 
     ```python
     sns.countplot(data=df, x='sentiment', palette='husl')
     ```

2. **Age Distribution**

   - **Description**: Shows the distribution of users' ages.
   - **Process**:
     - Convert age intervals to numeric values using mean.
     - Handle infinite values and drop missing values.
   - **Visualization**: A histogram of users' ages.
   - **Code**:
     ```python
     sns.histplot(data=df, x='Age of User', color='yellow')
     ```

3. **Country Distribution**

   - **Description**: Visualizes the distribution of tweets across different countries.
   - **Visualization**: A bar plot showing the top 100 countries by tweet count.
   - **Code**:
     ```python
     top_countries.plot(kind='bar', color='cyan')
     ```

4. **Population and Land Area**

   - **Description**: Normalizes and compares population and land area of countries.
   - **Process**:
     - Normalize population, land area, and density using Min-Max Scaling.
   - **Visualization**: A scatter plot of normalized population vs. land area.
   - **Code**:
     ```python
     plt.scatter(df["Normalized Population"], df["Normalized Land Area"], color='yellow')
     ```

5. **Demographic Correlation**

   - **Description**: Analyzes the correlation between normalized population, land area, and density.
   - **Visualization**: A heatmap of the correlation matrix.
   - **Code**:
     ```python
     sns.heatmap(correlation_matrix, annot=True, cmap="coolwarm")
     ```

6. **Sentiment by Time**

   - **Description**: Shows the sentiment distribution across different times of the day.
   - **Visualization**: A count plot with sentiment hues by time of day.
   - **Code**:
     ```python
     sns.countplot(data=df, x='Time of Tweet', hue='sentiment')
     ```

7. **Sentiment by Age**

   - **Description**: Visualizes how sentiment varies with user age.
   - **Visualization**: A count plot of sentiment by age.
   - **Code**:
     ```python
     sns.countplot(data=df, x='Age of User', hue='sentiment')
     ```

8. **Sentiment by Text Length**

   - **Description**: Examines the relationship between sentiment and the length of the text.
   - **Process**:
     - Add a column for text length.
   - **Visualization**: A box plot of text length by sentiment.
   - **Code**:
     ```python
     sns.boxplot(x="sentiment", y="Text Length", data=df)
     ```

## Files

- `train.csv`: The main dataset for analysis.
- `test.csv`: Test dataset.
- `plot.png`: Saved heatmap plot.
- `sentiment.png`: Saved sentiment by time plot.

## Notes

- The analysis uses a dark background style for plots to enhance readability.
- Warning messages are suppressed for cleaner output.

## Dependencies

Ensure you have the following Python libraries installed:
- `numpy`
- `matplotlib`
- `seaborn`
- `pandas`
- `scikit-learn`

You can install these libraries using pip:
```bash
pip install numpy matplotlib seaborn pandas scikit-learn
