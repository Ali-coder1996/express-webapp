# Express.js Web Application

This is a simple Express.js web application that responds with a message and the current timestamp.

## Running the Web Application Locally

To run the web application locally, follow these steps:

1. Make sure you have Node.js and npm installed on your machine.
2. Clone this repository to your local machine.
3. Navigate to the project directory.
4. Install dependencies by running the following command:
 ```
 npm install
 ```
 5. Start the server by running the following command:
 ```
 npm start
 ```
 6. Open your web browser and visit [http://localhost:3000](http://localhost:3000) to view the web application.

## Triggering the CI/CD Pipeline

The CI/CD pipeline is set up to trigger automatically whenever there's a change in the source code repository. However, you can also trigger it manually by following these steps:

1. Make changes to the source code or configuration files.
2. Commit and push your changes to the repository.
3. Visit the "Actions" tab in your GitHub repository to monitor the progress of the pipeline.

The pipeline will build the Docker image, push it to the container registry, and deploy the updated image to the Kubernetes cluster provisioned by Terraform.
