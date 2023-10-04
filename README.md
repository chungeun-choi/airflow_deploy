## Deploying Airflow with Docker

This repository is defined to deploy Airflow using Docker containers in a dynamic infrastructure environment.

### Deployment Configuration

When deploying Airflow, the worker component is separated into its own deployment. The remaining components, including webserver, scheduler, database, and Redis, are defined in the same YAML file. The `AIRFLOW__WEBSERVER__SECRET_KEY` option allows fetching worker logs from the webserver for monitoring.

![Airflow_divide_deploy](https://github.com/cucuridas/airflow_deploy/assets/65060314/c84f8b59-b65a-4af1-939d-99121fd563a1)


### Important Notes and References

- The provided definition files use a `requirements.txt` file and Dockerfile to build Docker images and create containers for Airflow services to support the required modules in workflows (refer to the image).
    
    ![airflow_docker_img](https://github.com/cucuridas/airflow_deploy/assets/65060314/c7850954-2988-467c-b07e-3a45f9ba3d7a)

    
- To enable communication between the Airflow worker service and the Airflow webserver, create a `.env` file and define the `AIRFLOW__WEBSERVER__SECRET_KEY` value.
- Requires Docker Engine to be installed.
- TLS settings are not applied for quick deployments.