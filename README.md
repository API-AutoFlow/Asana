

# Summary
* Integrate with Asana API
* Extract data from Asana
* Iterate over the data and filter only the relevant

# API AutoFlow Version:
Configuration config.json was created using AutoFlow version __0.2.5__

# Need help?
Is you have questions about this example, feel free to post your question on the community "<a href="https://interactor.com/autoflow/questions" target="_blank">Ask Questions</a>" website.

<a href="https://interactor.com/autoflow/questions" target="_blank">[Link button](http://example.com/){: .btn }</a>

# Asana integration + Data extraction

## Flow overview
1. HTTP Server
2. Endpoint (Method: GET)
3. Action __communication/http-request__ to make the HTTP API call to Asana
4. Action __json/decode__ to make the JSON easier to use
5. Action __data/set__ to create an empty array for storing the extracted database
6. Action __iteration/for-each__ to iterate over the Asana data which is in array
7. Action __array/insert-at__ to insert the extracted data into the array
8. Action __data/set__ to set the result in the response body
![Image](https://github.com/API-AutoFlow/asana-with-data-extraction/blob/master/img/0.png)


## Simulated Mock data
When build API solution, it is easier to mock the data, which makes it easier to build and test the solution.

![Image](https://github.com/API-AutoFlow/asana-with-data-extraction/blob/master/img/1.png)

## Step 1. Make HTTP API Call to Asana
Set the URL to the path that was created from previous string/join action.
The query comes from the user which consists of ID and Key.  In our solution, you can simulate that.
The returned data is stored in a new variable called "result"

![Image](https://github.com/API-AutoFlow/asana-with-data-extraction/blob/master/img/2.png)

## Step 2. Decode JSON data
Asana returns the data in JSON format.  We can use the json/decode action to put the data in a more accessible format.

![Image](https://github.com/API-AutoFlow/asana-with-data-extraction/blob/master/img/3.png)

## Step 2. Extract just the list
Extract the list from the data returned from Asana API

![Image](https://github.com/API-AutoFlow/asana-with-data-extraction/blob/master/img/4.png)

## Step 3. Create (declare) empty array
Array is commonly used to structure extracted data. Before we iterate over the Asana data, we use data set to delcare/create an empty array.

![Image](https://github.com/API-AutoFlow/asana-with-data-extraction/blob/master/img/5.png)

## Step 4. Iterate over Asana data
Notice that decoded Asana data was saved in a variable called "result_decoded".
Each element's index and value are stored in index and value variables respectively.

![Image](https://github.com/API-AutoFlow/asana-with-data-extraction/blob/master/img/6.png)

## Step 5. Insert only the relevant data
As the Asana data is iterated, array/insert-at action inserts the selected data into the "sorted" array that was created earlier

![Image](https://github.com/API-AutoFlow/asana-with-data-extraction/blob/master/img/7.png)

## Step 6. Set data to response body
To make the data available, data/set action is used to set data in the response body.

![Image](https://github.com/API-AutoFlow/asana-with-data-extraction/blob/master/img/8.png)


## Configuring Asana API

For Additional help on Asana API:
https://asana.com/guide/help/api/api

Get Asana Key (you must be signed in)
https://app.asana.com/0/developer-console
