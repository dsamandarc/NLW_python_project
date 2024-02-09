# NLW_python_project
This repository is NLW Expert Python Project
## Barcode Tag Creator

### Overview
This Python project provides a backend service for creating barcode tags, primarily using the Code128 barcode standard. It's designed with a clean architecture, separating concerns into modules such as controllers, drivers, validators, and views. The service includes error handling and a testing suite for validating the functionality.

### Features
- Generation of Code128 barcodes.
- REST API endpoint for creating barcode tags.
- Input validation for product codes.
- Custom error handling with HTTP response codes.
- Automated tests for key components.

### Getting Started

#### Prerequisites
- Python 3.x
- Flask
- Cerberus Validator
- python-barcode


#### Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/dsamandarc/NLW_python_project.git
 
2. Navigate to the project directory:
    ```sh
    cd pythonProject
    
3. Install the dependencies:
    ```sh
    pip install -r requirements.txt
   
### Running the Service:
- To start the service, run:
    ```sh
    python run.py

The web server will start, and the service will be available at the configured port (default: 3000).

### Usage

To create a barcode tag, send a `POST` request to the `/create_tag` endpoint with a JSON payload containing the `product_code` key.

#### Request:

    ```http
    POST /create_tag HTTP/1.1
    Host: <your-server-hostname>
    Content-Type: application/json

    {
        "product_code": "1234567890"
    }

#### Response:
The server will respond with a JSON object containing the path to the generated barcode image.

    ```http
    {
        "data": {
            "type": "Tag Image",
            "count": 1,
            "path": "<path-to-generated-barcode>.png"
        }
    }

#### Tests:
- To run the automated tests with pytest, execute:
    ```sh
        pytest
  
### Modules
- **Controllers**: Handles the business logic for tag creation.
- **Drivers**: Interfaces with the barcode library to create barcode images.
- **Errors**: Define and handle custom exceptions.
- **Validators**: Validates incoming request data.
- **Views**: Manages the HTTP interactions and invokes controller logic.
- **Main**: Sets up and runs the Flask server.

#### Contributing:
- Contributions are welcomed! If you have suggestions for improvements, or have discovered a bug, please open an issue. For direct contributions, please fork the repository, make your changes, and submit a pull request. 
