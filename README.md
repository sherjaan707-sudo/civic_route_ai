Development for Artificial Intelligence | Course Assessment
DEVELOPMENT FOR ARTIFICIAL INTELLIGENCE
COURSE ASSESSMENT
CivicRoute AI Supporting Data
Data Dictionary and Category Guide
The supplied structured data is synthetic educational materials. They do not represent real residents, real municipal requests or real personal information. Assessment scope Only the supplied structured CivicRoute AI dataset, namely civic_requests_prepared.csv is required for the assessment. The TensorFlow/Keras starter notebook is also supplied to aid your coding efforts.
Request Categories Category label Plain-language meaning pothole Damage or a hole in a road surface. water_leak Visible or reported water escaping from municipal infrastructure. broken_streetlight A streetlight that is not operating correctly. illegal_dumping Waste or unwanted material left in an unauthorised public area.
Assessment Dataset Fields
The following fields appear in the civic_requests_prepared.csv dataset file. Field Type Description Notes request_id text Unique educational request identifier. Identifier; exclude from model inputs. created_hour integer Hour of day when the request was created, from 0 to 23. Prepared numerical field; possible model input. neighbourhood category Neighbourhood linked to the request. Categorical field; consider fairness and reporting-pattern limitations. channel category Submission channel: mobile app, web portal, call centre or service office. Categorical field with 4 missing values to inspect and handle. urgency_level category Prepared urgency indication: low, medium or high. Prepared categorical field; input feature, not a final routing decision. recent_rain_flag category Whether recent rain was recorded. Yes/no categorical field. night_report_flag category Whether the request was submitted at night. Derived from created_hour; consider whether both fields are needed. repeat_report_count integer Number of similar nearby reports recorded recently. Prepared numerical feature. image_quality_score decimal Prepared image-quality score from 0 to 1. Prepared image-quality metadata score from 0 to 1; 10 values are missing. No image files are supplied. nearby_asset_age_years decimal Approximate age of the nearby infrastructure asset. Prepared numerical feature. description_word_count integer Number of words in the prepared request description. Prepared numerical feature; the description text itself is not supplied. previous_resolution_days decimal Days previously required to resolve a similar case. Prepared numerical feature with 9 missing values to inspect and handle. category_label category Target request category. Prediction target with four balanced request categories.
Development for Artificial Intelligence | Course Assessment
Dataset Summary
Item Summary
Assessment file and size civic_requests_prepared.csv: 600 records and 13 fields.
Target categories 4 balanced categories with 150 records each: pothole,
water_leak, broken_streetlight and illegal_dumping.
Missing values channel: 4; image_quality_score: 10; previous_resolution_days:
9. All other fields are complete.
Assessment use Inspect and slice the data, handle the small preparation issues,
encode or transform selected fields, then build one small
TensorFlow/Keras classifier.
