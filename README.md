# Vehicle Routing Optimization

This is a Django-based web application for solving Vehicle Routing Problems (VRP). It uses Google OR-Tools to calculate optimal routes for a fleet of vehicles to serve a set of customers with various constraints, such as time windows.

## Key Technologies

*   **Django:** A high-level Python web framework for rapid development.
*   **Google OR-Tools:** A software suite for combinatorial optimization, used here for solving the VRP.
*   **Geopy:** A Python library for geocoding and distance calculations.
*   **Numpy & Scikit-learn:** Used for numerical operations and data analysis.
*   **Openpyxl:** A Python library for reading and writing Excel files, used for handling input data.
*   **HERE API:** Used to visualize the computed routes on a map.

## Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the Django development server:**
    ```bash
    python manage.py runserver
    ```
    The application will be available at `http://127.0.0.1:8000/`.

## How to Use

1.  **Open the application in your browser.**
2.  **Provide input data in one of the following ways:**
    *   **Upload Coordinates and Distances:** Upload two separate Excel files: one with customer coordinates and another with a distance matrix between all locations.
    *   **Upload Pre-calculated Routes:** Upload an Excel file containing pre-calculated routes (e.g., `Input_route_example_time.xlsx`).
3.  **Enter your HERE API credentials:**
    *   Provide your `app_id` and `app_code` to visualize the routes on a map.
4.  **Click the "Submit" button.**

The application will then display the optimal routes on a map, along with a summary of each route (distance, duration, number of customers).

## Project Structure

*   `vehiclerouting/`: The main Django project directory.
*   `findroute/`: The Django app that contains the core logic for the V-RP solver.
    *   `views.py`: Handles the web requests and responses.
    *   `vrpSolver.py`: Orchestrates the VRP solving process.
    *   `googlerouting.py`: A wrapper for the Google OR-Tools library.
    *   `models.py`: Defines the data models for the application.
    *   `templates/`: Contains the HTML templates for the user interface.
*   `requirements.txt`: A list of the Python dependencies for the project.
*   `manage.py`: A command-line utility for interacting with the Django project.
*   `*.xlsx`, `*.xlsm`: Example input files.
