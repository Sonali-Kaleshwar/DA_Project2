# Streamlit cloud deployment

This copy stores every historical record in data/assessment_features.csv.gz.
Do not extract or decompress that file. The app reads it directly.
The compressed bytes decompress to the exact original CSV, with no sampling,
row removal or precision changes. Models and training logic are unchanged.

1. Extract the deployment ZIP on your computer.
2. Upload the extracted math_assessment_abi folder and its contents to GitHub.
   Upload the .csv.gz file as-is. Do not upload the deployment ZIP itself as
   the only repository file: Streamlit needs access to app.py and its folders.
3. Confirm GitHub shows app.py, insights.py, requirements.txt, data, models
   and outputs. No individual file in this package exceeds 25 MB.
4. In Streamlit Community Cloud select math_assessment_abi/app.py if the
   folder is at repository root, or app.py if you uploaded its contents directly.
5. Use Python 3.12 for consistency with the tested local runtime.
6. Deploy and test all tabs before submitting the live URL.

Local launch from this folder: python -m streamlit run app.py

The offline training script is unchanged. If run later, it writes the ordinary
CSV and the loader will prefer that newly generated file over the gzip copy.
Compress a fresh deployment copy before uploading an updated dataset.
