# Rental Recommendation Web Service

## Introduction
Finding a rental property that aligns with specific preferences can be a time-consuming task for users, given the vast number of listings available online. While existing platforms like Zillow and Realtor.com offer basic filters, they often fall short when it comes to addressing nuanced user needs such as proximity to specific locations, quiet neighborhoods, or low-crime areas. This gap inspired us to create a more effective solution: a rental recommendation web service powered by a robust clustering model.

Our application allows users to search for rental listings in a desired area and view personalized recommendations for similar properties when exploring a specific listing.

The recommendation system uses a clustering algorithm trained on scraped property data, identifying patterns and grouping similar properties based on features like location, price, size, and amenities. By focusing on the relationships between these attributes, our application simplifies the property search process, delivering results that are more relevant and tailored to user preferences.


The project is built on four key components:
1. **Frontend**
2. **Backend**
3. **Web Scraper Pipeline**
4. **Recommendation Model Training Pipeline**

### Frontend
- **Technologies**: React, Redux
- **Description**: Ensures a responsive and modular user interface.

### Backend
- **Technologies**: Python, FastAPI
- **Description**: Handles REST APIs, integrates with MongoDB for managing housing data, and utilizes Redis for caching frequently accessed information.

### Web Scraper Pipeline
- **Technologies**: Kafka, Apache Flink
- **Description**: Collects and processes rental listings from platforms like Zillow and Realtor.com using a nightly cron job. This ensures the database remains comprehensive and up-to-date.

### Recommendation Model Training Pipeline
- **Technologies**: Google Colab, AWS S3
- **Description**: The recommendation model is trained offline and deployed to AWS S3, enabling periodic updates to maintain its relevance and accuracy.

## Clustering Techniques
By combining efficient clustering techniques, such as k-means and HDBSCAN, with dimensionality reduction methods like UMAP, our system identifies meaningful patterns in the data and creates clusters of similar properties. This approach not only ensures a streamlined and user-friendly property search experience but also addresses critical gaps in existing rental platforms.

## Getting Started

### Prerequisites
- Node.js and npm
- Python 3.8+
- MongoDB
- Redis
- Kafka
- Apache Flink
- Google Colab account
- AWS account

### Installation

#### Frontend
1. Navigate to the `web-app` directory:
    ```sh
    cd web-app
    ```
2. Install dependencies:
    ```sh
    npm install
    ```
3. Start the development server:
    ```sh
    npm start
    ```

#### Backend
1. Navigate to the `listing-service` directory:
    ```sh
    cd listing-service
    ```
2. Create a virtual environment and activate it:
    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```
3. Install dependencies:
    ```sh
    pip install -r requirements.txt
    ```
4. Start the FastAPI server:
    ```sh
    uvicorn main:app --reload
    ```

#### Web Scraper Pipeline
1. Set up Kafka and Apache Flink as per their official documentation.
2. Configure the nightly cron job to run the web scraper.

#### Recommendation Model Training Pipeline
1. Train the model in Google Colab.
2. Deploy the trained model to AWS S3.

## Usage
1. Open the frontend application in your browser.
2. Search for rental listings in a desired area.
3. Explore a specific listing to view personalized recommendations for similar properties.

## Contributing
We welcome contributions to improve our rental recommendation web service. Please follow these steps:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Create a new Pull Request.

## License
This project is licensed under the MIT License.

## Acknowledgements
- Realtor.com for providing property data.
- The developers and maintainers of React, Redux, FastAPI, Kafka, Apache Flink, Google Colab, and AWS.