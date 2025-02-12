
### Additional Notes:
- Please run the `docker-compose` file before testing out the API. The `docker-compose` runs a testing MongoDB container, which is acting as a testing DB. You can go to the Mongo Express URL at `localhost:8081` to see how the documents and collections are being uploaded.

	- To run the Docker Compose, please run the following command:
		```console
		docker-compose up -d
		```
- Please note that I followed the same file structure that you asked for, except for the fact that I created a dedicated package called `api` to better handle the imports.

- In order to replicate a real-life situation, I have added an additional `/token` endpoint which authenticates the user. You can test run the API by logging in yourself as one of the users in `FAKE_USERS_DB`, given in the `config.py` file.

  - Make sure to log in before you test the API in Swagger UI by clicking the `Authorize` button. For example, to act as Mohammad, put in the username: `mohammad` and password: `secret` in the form-data.

- To run the API:
	- First create the conda environment by running the following command:

	```console
	conda env create -f environment.yml
	```

	- Activate the newly created conda environment

	```console
	conda activate fastapi
	```
	- Run the server
	
	```console
	uvicorn app:app --reload
	```

### Problem faced during setup:
I faced the port number issue while setuping docker env with mongodb, because already my another mongo server is running on default port 27017. I proxy to 27019 in docker file.
