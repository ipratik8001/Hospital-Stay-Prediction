# Hospital-Stay-Prediction
Problem Statement  Task 1:- Prepare a complete data analysis report on the given data.  Task 2:- Create a machine learning model to predict the length of stay (in days) of a patient entering the hospital, given various factors about their stay.

Research determined the values for Ward Facility Code correspond to an actual medical/hospital standard.

There is an ABCDEF bundle used in health care. We will convert this to a numerical value since this medical featue probably affects LOS.

See references below:

https://nyschp.memberclicks.net/assets/docs/EventsEducation/Sleep%20no%20more%20ABCDEF%20Ashulter.pdf

https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5351776/#:~:text=the%20ABCDEF%20bundle.-,The%20ABCDEF%20bundle%20includes%3A%20Assess%2C%20Prevent%2C%20and%20Manage%20Pain,engagement%20and%20empowerment%20(F)

https://journals.lww.com/ccejournal/fulltext/2021/03000/abcdef_bundle_and_supportive_icu_practices_for.12.aspx

https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8286762/ (COVID specific)

Analysis of Ward Type and Ward Facility Code Features
The values in Ward Type and Ward Facility Code correspond to medical care acronyms and that could be the case in our dataset.

Ward Type has unique values of PQRST which correspond to PQRSTU assessment method.

Ward Facility Code has unique values of ABCDEF which correspond to the ABCDEF medical bundle.

Even if we do not have the domain knowledge or access to a domain knowledge expert, we can reasonably assume/conclude that these two features will affect the target variable (Stay) in our dataset.

Data Science in Health Care
The authors of the recently released Data Science in Context make the point that data science is transdisciplinary and needs to builds coalitions, “Data science operates in a societal context. Making sure we “get it right” requires partnerships which must include viewpoints from non-STEM (science, technology, engineering, and mathematics) domains such as sociology, law, economics, philosophy, and political policy.”

This point is important because doing/getting data science right cannot be reduced to getting high model accuracy scores. The authors agree that data science can help solve problems in healthcare, but also “illustrate the complexity of gaining meaningful results. Whether due to data quality, privacy, complex models, or the difficulties in determining causality, using healthcare records at scale is difficult.”

They continue, “To support data gathering and use, there must be complex data management software that aggregates data while both preserving privacy and allowing for the transparency needed in scientific studies. When data is gathered from multiple sites, due attention must be paid to the risks of fraud. Sites are likely to anonymize or aggregate data prior to release, making validation more difficult.”

“The near-universal collection of healthcare records can suggest new hypotheses, support post-approval monitoring of new drugs, provide an interactive analysis platform for researchers to explore new ideas, catalyze new approaches for screening or preventing disease, and sometimes answer critical healthcare questions. However, frequently, issues of data quality and availability, modeling complexity, privacy and security, the difficulty in determining causal relationships, and more make these applications difficult.”

We must keep the above in mind as we apply suitable ML algorithms and record their results/scores for our business problem.

Shayan Mohanty, a guest on Super Data Science Podcast Episode (635), The Perils of Manually Labeling Data for Machine Learning Models, made relevant points about the ethical and other concerns about using hand labeled data in supervised machine learning. While a full discussion of this topic might be out of scope here, it should be noted and a link to the show which includes the show's transcript is provided for reference.

Feature & Model Selection
It is labelled data so we have to choose from supervised ML algorithms: Linear Regression, Decision Trees for example.

Writing for The JetBrains Datalore Blog, Jodie Burchell, How to Prepare Your Dataset for Machine Learning and Analysis, says "Most datasets for machine learning projects or analyses are not purpose-built, meaning that occasionally we have to guess how the fields were collected or what they actually measure. In the absence of a data dictionary, or someone to explain what the dataset’s fields mean, we may need to work this out based on the information we have."

We have to work out as best we can in the absence of (1) a domain expert like a doctor, or (2) someone who was directly involved in collecting/creating the dataset, what the features of the dataset mean. It is unlikely that this dataset was purpose-built to answer/solve our business problem, therefore not all of the features will necessarily apply to our business problem.

One way to determine what our features are measuring is to check their relationships with other features. If two or more fields/features are highly correlated we can assume that they are measuring similar things.

We also have to check for feature leakage, that is, if any of our features are too highly related to the target (Stay in this case). That doesn't seem to be the case here.

Create a Final Dataset with Features to be used in Models
We think the following features can be dropped from this dataset as they do not seem to contribute to our business problem/project and would not affect LOS: Hospital Code, Hospital Type Code, City Code Hospital, Hospital Region Code, Patient ID, City Code Patient


Conclusion:-
The ability to predict LOS can provide a clinical indicator of the health status of a patient as well as assist in predicting the level of care that is required.LOS varies with respect to many factors including severity of illness, diagnosis and a variety of patient factors. This paper provides a review of LoS prediction methods, their respective shortcomings as well as the types of data and features that have been used in the literature. Despite the continuing efforts to predict and reduce the LOS of patients, The model tuning and data preprocessing steps are too specific and result in a large proportion of the current prediction mechanisms being restricted to the hospital that they were employed in.

Machine learning implementations and their explanations, if not sufficiently interpretable, could further hamper the day-to-day effort, of a healthcare worker. Balancing the interpretability of such models with the overall prediction performance that they provide will be a key challenge in the future of LOS prediction.
