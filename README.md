
# Simplewishlist

## Description

This is a Python project using Django-ninja & React. 
It is a simple wishlist application where users can create, update, delete and view their wishlists.

## Setup and Installation

### Prerequisites

Backend:
- Python 3.8 or higher
- package manager uv : https://astral.sh/blog/uv

Frontend:
- Node.js 14.17.0 or higher
- npm 6.14.13 or higher

## Installation using Docker compose

1. Clone this repository, this is now the root directory.

2. Clone both the frontend and backend repositories to the root directory.

   >Frontend: https://github.com/Camille-cmd/simplewishlist_frontend

   >Backend: https://github.com/Camille-cmd/simplewishlist_backend

3. Create the environment files for the frontend and backend by copying the corresponding `.env.example` files and renaming them to `.env`.

4. For the first installation, build the docker images by running the following command:
    ```bash
    docker compose build
    ```
   
5. Run the following command to start the application:
    ```bash
    docker compose up
    ```
 
6. Insert the initial data by running the following command:
    ```bash
    docker exec -it simplewishlist_backend python manage.py loaddata wishlist_data.json
    ```
   > Note: 
   > The initial data is a list of users and wishlists. 
   > You can find the data in the file `core/fixture/wishlist_data.json` in the backend repository.
   
   > You may need to restore the database to its initial state by using the flush_db.sh script in the root directory.
   > This script will remove all the data from the database and insert the initial data.

7. Navigate to `http://localhost:5173` in your browser to see the application running.
   > To see directly a wishlist, you can use the following URL: `http://localhost:5173/link/6999920a-67df-4c0d-8299-ebc88446d64c#gandalf`

8. You can access the API documentation at the following URL: `http://localhost:5173/api/docs`

9. You can access the admin panel at the following URL: `http://localhost:5173/admin`
    - Username: admin
    - Password: admin

## Testing

To run the tests, use the following command:
```bash
docker exec -it simplewishlist_backend python3 manage.py test
```
> Note:
> You can use the run_tests.sh script in the backend root directory to run the tests.

## Before you commit

We use pre-commit to run some checks before you commit your changes.
To install pre-commit, run the following command:
```bash
    pre-commit install
```

Before you commit, make sure to run the tests and check the coverage:
```bash
# Make sure coverage is higher than 80% and tests pass
docker exec -it simplewishlist_backend coverage run manage.py test
```

## License

This project is licensed under the GNU Affero General Public License v3.0 - see the `LICENSE.md` file for details
