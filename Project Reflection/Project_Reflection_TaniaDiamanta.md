# Project Reflection

Name: Tania Diamanta

Student ID: 11585796

## About the Project

This project aimed to forecast the long-term impact of climate change on soil moisture across the UK, using near-surface air temperature (TREFHT) as the primary focus. By combining CESM climate model data (2006–2080) with ERA5 reanalysis data, we implemented a two-stage modelling approach: 
1. **Time series forecasting of temperature** using Prophet and XGBoost
2. **Soil moisture prediction** via XGBoost regression.

The ultimate goal was to assess agricultural risks under projected climate conditions.

## Encountered Challenges

Throughout the project, I personally encountered several technical and conceptual challenges that tested my data handling, modelling, and interpretive skills.

1. **Data Complexity & Preprocessing**

This project marked my first experience working with 3D datasets in NetCDF (.nc) format, rather than the usual CSV files. Initially, I felt completely unsure about how to approach the six provided datasets. I didn't even know how to open them. It wasn’t until I revisited the Week 6 lab that I began to connect the dots. Upon inspection, the files appeared identical in terms of spatial and temporal coverage and contained the same variables. However, after checking the actual values, I noticed subtle differences, which led me to realise these were likely ensemble runs from the same climate simulation. After doing some research, I decided the most robust approach was to merge the datasets by averaging the values across all runs. I also had limited experience working with time series data, so handling missing values in a temporally consistent way was another challenge. It took some trial and error to understand how to impute missing data effectively while preserving the structure and integrity of the time series. Deciding on appropriate imputation strategies (e.g., forward fill, median imputation, etc.) was not straightforward and required experimentation to avoid bias.

2. **Finding External Dataset**

Coming from a non-environmental background, I initially had limited knowledge of where and how to access environmental datasets. I referred back to the Week 6 lab and explored several sources including CMIP6, ERA5, and Google Earth Engine. Navigating these platforms was challenging at first. While CMIP6 datasets were relatively easier to access, I found the accompanying documentation and variable naming conventions quite difficult to interpret. Google Earth Engine, on the other hand, was more intuitive for visualisation, but I wasn’t sure how to export or download the data for local analysis. ERA5 eventually became the most approachable option for me—their documentation was clearer, and the variables were easier to understand. That’s when I got the idea to extract soil-related variables and analyse their relationship with rising temperatures. I initially tried to access the data programmatically using the climetlab package, but despite a successful installation, my code kept failing. In the end, I opted to download the data manually from the ERA5 website, which turned out to be more reliable for my purposes.

3. **Model Selection and Performance Tuning**

Although I wasn't directly responsible for building the model, I contributed significantly to designing our overall modelling approach. I proposed breaking the process into two stages: Stage 1 to forecast temperature, and Stage 2 to use those predictions to estimate future soil moisture. I was also involved in reviewing the model code toward the end of the project.

One of the biggest challenges I encountered was ensuring consistency across spatial and temporal coverage—particularly when aligning the provided datasets with the external ERA5 dataset and maintaining that consistency throughout both modelling stages. Matching coordinates between datasets proved more difficult than expected. It was only during this process that I discovered the Python package XESMF, which is specifically designed for spatial regridding. Learning to apply this tool was a key moment in overcoming those alignment challenges.

4. **Interpreting Results with Real-world Implications**
Translating predicted values (e.g., soil moisture in m³/m³) into meaningful agricultural impact required domain knowledge (e.g., FAO thresholds), which was initially outside my expertise.

Despite these obstacles, each challenge deepened my understanding of climate data analysis and ultimately strengthened the reliability and relevance of our final model outputs.

## Learning Outcomes

This project offered a valuable opportunity to expand my technical skillset, deepen my understanding of climate data, and bridge the gap between data science and environmental applications.

1. **Technical Skills**

- Gained hands-on experience working with complex, multidimensional climate data in NetCDF (.nc) format, including merging ensemble simulation outputs and managing spatial-temporal structures.
- Strengthened data wrangling skills, including unit conversion, imputation strategies, and handling missing or inconsistent values within time series.
- Developed practical skills in time series forecasting using Prophet and regression modelling with XGBoost, with an emphasis on structuring multi-stage modelling workflows.
- Learned to apply XESMF for spatial regridding, enabling consistent coordinate alignment between datasets—a crucial step for maintaining model accuracy.

2. **Data Literacy & Environmental Awareness**

- Gained familiarity with environmental datasets such as CMIP6, ERA5, and Google Earth Engine, and developed the ability to critically evaluate their structure, accessibility, and applicability.
- Improved understanding of key environmental variables (e.g., soil moisture, temperature, precipitation) and their significance in climate-agriculture interactions.

3. **Conceptual and Analytical Thinking**

- Contributed to modelling strategy design, including decomposing the problem into two linked stages to predict long-term soil moisture from temperature trends.
- Developed a better appreciation for the importance of spatial and temporal consistency in model inputs and outputs, and how small mismatches can significantly affect model performance.
- Gained insight into the real-world implications of modelling outputs by interpreting predictions in relation to soil moisture benchmarks and agricultural thresholds (e.g., field capacity, wilting point).

Overall, the experience not only enhanced my confidence in handling complex environmental datasets but also strengthened my ability to apply data-driven methods to real-world challenges in climate and agriculture.

## Future Improvements

For future improvements, the modelling framework could be enhanced by integrating additional predictors such as soil temperature, precipitation, and evapotranspiration to better capture the drivers of soil moisture variability. Focusing the analysis specifically on crop-growing seasons—by excluding winter months could also yield more agriculturally relevant insights. Expanding the spatial coverage beyond the UK to a pan-European or even global scale would increase the generalisability and policy relevance of the findings. Additionally, exploring advanced deep learning models, such as Long Short-Term Memory (LSTM) networks or Convolutional Neural Networks (CNNs), could offer improved capabilities in modelling complex spatiotemporal patterns.
