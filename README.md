# KrishnaBollojula_W11_Graded-Assignment

Create a Virtual Environment. (1 mark)

## creating a virtual environment

C:\gl-seds\KrishnaBollojula_W11_Graded_Assignment>python -m venv gl-seds-w11

## activating virtual environment

C:\gl-seds\KrishnaBollojula_W11_Graded_Assignment>.\gl-seds-w11\Scripts\activate


Install the dependencies from requirements.txt file. ( 1 mark)

## installing python libraries from requirements file

(gl-seds-w11) C:\gl-seds\KrishnaBollojula_W11_Graded_Assignment\Microservices>pip install -r requirements.txt

## Train and save the model. (2 marks)

#train the model by running train.py in code_model_training folder

(gl-seds-w11) C:\gl-seds\KrishnaBollojula_W11_Graded_Assignment\Microservices>python code_model_training\train.py

## Test the Flask web application. (5 marks)

(gl-seds-w11) C:\gl-seds\KrishnaBollojula_W11_Graded_Assignment\Microservices>python app.py

## Test the application and make predictions using the example calls available in the folder/tests.(5 marks)

(gl-seds-w11) C:\gl-seds\KrishnaBollojula_W11_Graded_Assignment\Microservices>python test.py

## Create a docker image containing everything needed to run the application.(10 marks)

create the Dockerfile in the folder with the code below

FROM python:3.8-slim
WORKDIR /app
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt
COPY . .
EXPOSE 5000
CMD ["python3", "app.py", "test.py"]

## create a docker image by running the command from the Dockerfile folder 

Run the containerized application as a prediction service and test it locally by passing some example calls and get the prediction. (10 marks)

docker build -t python-ml-gl-seds .

## run this command to create the container and run the flask api in the background

docker run -itd --name w11_assignment -p 5000:5000 python-ml-gl-seds

