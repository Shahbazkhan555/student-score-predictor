# Student Score Predictor

## Introduction

The Student Score Predictor project is an educational application designed to help students estimate their future academic performance based on historical data and various input factors. The main goal of the project is to provide students with insights into their potential scores and offer suggestions for improvement. The application utilizes machine learning techniques to predict students' scores and offers data transformation and model training functionalities.

## Pipelines

### Continuous Integration (CI) Pipeline

The CI pipeline is triggered whenever code is pushed to the "main" branch, except for changes in the "README.md" file. The CI pipeline performs the following tasks:

1. Code Linting: The code is linted to ensure it adheres to coding standards.

2. Unit Testing: The unit tests are executed to verify the functionality of the code.

### Continuous Delivery (CD) Pipeline

The CD pipeline is triggered after successful completion of the CI pipeline. It involves building and pushing the Docker image of the Gemstone Price Predictor model to Amazon Elastic Container Registry (ECR). The CD pipeline performs the following steps:

1. Docker Image Build: A Docker container is built for the student score Predictor model.

2. Docker Image Tagging: The Docker image is tagged with the latest version.

3. Docker Image Push: The Docker image is pushed to Amazon ECR for deployment.

### Continuous Deployment (CD) Pipeline

The CD pipeline is responsible for deploying the Docker image from Amazon ECR and serving the Gemstone Price Predictor model to users. It performs the following tasks:

1. Pull Latest Docker Image: The latest Docker image from Amazon ECR is pulled.

2. Run Docker Image: The Gemstone Price Predictor model is deployed as a Docker container and exposed on port 8080.

## MLOps Concepts Covered

The Gemstone Price Predictor App incorporates several MLOps concepts:

1. **Continuous Integration (CI):** The CI pipeline automates code testing and linting whenever code is pushed to the repository.

2. **Continuous Delivery (CD):** The CD pipeline automates the process of building and deploying the Docker image to ECR.

3. **Continuous Deployment (CD):** The CD pipeline deploys the Docker image to serve users.

4. **Versioning and Tagging:** Docker image versioning and tagging are used to ensure reproducibility and track changes.

5. **Infrastructure as Code (IaC):** The Dockerfile defines the infrastructure required for the application.

6. **AWS Integration:** AWS services, such as ECR, are integrated into the workflow for seamless deployment.


## Getting Started

To use this project locally, follow the steps below:

### Prerequisites

Make sure you have the following installed on your machine:

- Python 3.8 or later
- Docker (optional, for running the app in a container)
- AWS CLI (optional, for accessing AWS services)

### Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/student-score-predictor.git
   cd student-score-predictor
   ```

2. Create a virtual environment (recommended):

   ```bash
   python3 -m venv venv
   source venv/bin/activate   # On Windows, use: venv\Scripts\activate
   ```

3. Install the required Python packages:

   ```bash
   pip install -r requirements.txt
   ```

### Data Ingestion

To start the data ingestion process, run the following command:

```bash
python data_ingestion.py
```

This will read the student data, split it into training and test sets, and save the data in the "artifacts" directory.

### Model Training

To train the student score prediction model, run the following command:

```bash
python model_trainer.py
```

The script will initiate model training using various machine learning algorithms, including CatBoost, and save the best model in the "artifacts" directory.


### Docker Image (Optional)

If you have Docker installed, you can build and run the app in a Docker container. Follow these steps:

1. Build the Docker image:

   ```bash
   docker build -t student-app .
   ```

2. Run the Docker container:

   ```bash
   docker run -p 8080:8080 student-app
   ```

The app will be available at `http://localhost:8080`, and you can make predictions using the same method as described above.

## Contributing

If you wish to contribute to this project, feel free to create a pull request. We welcome your contributions and ideas.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

We would like to thank the contributors and the community for their support and valuable feedback.
