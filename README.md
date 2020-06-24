# streamlit-fastapi-model-serving

Simple example of usage of streamlit and FastAPI for ML model serving

When developing simple APIs that serve machine learning models, it can be useful to have _both_ a backend (with API documentation) for other applications to call and a frontend for users to experiment with the functionality.

In this example, we serve an image semantic segmentation model using `FastAPI` for the backend service and `streamlit` for the frontend service. `docker-compose` orchestrates the two services and allows communication between them.

To run the example in a machine running Docker and docker-compose, run:

    docker-compose build
    docker-compose up

To visit the FastAPI documentation of the resulting service, visit http://localhost:8000 with a web browser.  
To visit the streamlit UI, first inspect logs of the streamlit service via

    docker-compose logs streamlit

and visit the `Network URL` address that can be found in the logs.