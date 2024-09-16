# Amazon-Ml-Hackathon-- Was under Top 250 teams among total 25000 teams

We built a model to extract numeric values and units from 130,000 product images. Using PaddleOCR for text extraction and regex for post-processing, we standardized values like weight and volume. This solution is vital for improving product details in fields like e-commerce.

In this hackathon, we built a machine learning model to extract entity values from product images, with a dataset containing 130,000 rows. This task is essential for sectors like healthcare, e-commerce, and content moderation, where extracting key details (e.g., weight, volume, voltage) from images is crucial for product descriptions in digital stores.

Dataset:
index: Unique ID for each sample.
image_link: Public URL for product images.
group_id: Product category code.
entity_name: Entity type (e.g., “item_weight”).
entity_value: Entity value (e.g., “34 gram”). Absent in test data.


Approach:
PaddleOCR: Used for extracting raw text from images. It supports rotated text detection and used the English language model for accuracy.


Regex-based Post-Processing:
First regex ((\d+\.?\d*\s?\w+)) captures numeric values with units (e.g., "5 kg").
Second regex ((\d+(\.\d+)?)(\s*|\b)(grams|kg|cm|etc.)) normalizes units (e.g., "kg" to "kilogram").


Experiments:
PaddleOCR extracted noisy text, which was cleaned using regex to isolate values and units.
Units were mapped to valid formats (e.g., "kg" to "kilogram").


Conclusion:
The combination of PaddleOCR and regex provided efficient extraction and standardization of values and units. Future enhancements could include domain-specific OCR training and expanded regex coverage for complex units.
