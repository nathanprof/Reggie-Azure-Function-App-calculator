# Reggie-Azure-Function-App-calculator
- Using Http Trigger to call an Azure-Function-App that sums the value of x and y and inputs the result
- The app is tested locally using VS code, later published to Azure and also tested in Azure using http as it's trigger
- The class was renamed to sum
- The function attribute was also renamed to sum
- The content of run method was deleted
- The logger was not deleted
- Lines as written below were added
- int x = int.Parse(req.Query["x"]);
- int y = int.Parse(req.Query["y"]);
- int result = x + y;
- return new OkobjectResult(result);
- The parseInt method parses a value as a string and returns the first integer
- more information about partInt can be gotten from this link https://www.w3schools.com/jsref/jsref_parseint.asp
- the sum was calculated in the local environment by clicking the start button without debugging, which will automatically open a command prompt where you copy this link to a browser http://localhost:7075/api/sum and then add ?x=70&y=50 to it e.g http://localhost:7075/api/sum?x=70&y=50
- To verify it worked your browser will display the following sum of 120 which is the addition of 70 + 50
# Creating Azure Function App 
- Azure Functions lets you run your code in a serverless environment without having to first create a virtual machine (VM) or publish a web application
- Sign in to the Azure portal with your Azure account
- In the search bar, enter Function App and click on Create
- On the Basics page, use the function app settings as specified in the following *Function App name - runtime should be .NET with your proper Region selected to save cost
- On the Hosting page, enter the following settings. *Operating system- Windows *Plan- Consumption (Serverless-In this serverless hosting, you pay only for the time your functions run
- Give the storage a globally unique name
- Select "Review + create" to review the app configuration selections.
On the "Review + create" page, review your settings, and then select "Create" to provision and deploy the function app
# Deploying from VS code to Azure Portal
- Search for "Publish" Select Azure / Right-click on the project in Solution Explorer and select "Publish"
- Then select "Azure" and  click next then "Azure function App (windows)" Click Next
- Then choose Select Function Instance here it depends you might be prompted to sign in to your Azure accout then the resource-group will appear then drpo down the function-app name will show click on the and the next button will highlight then click and then click finish.
- Wait till you see ready to publish then click on publish "Select Finish",to deploy the package containing your project files to your new function app in Azure
- After the deployment completes, the root URL of the function app in Azure is shown in the Publish tab
- From the left menu of the Function App window, select "Functions"
- The name of the class is shown in the Functions tab in my case it is sum click on it then click on select "Get function url"
- The sum was calculated in Azure platform using the link that was gotten from "Get function url" in the function tab of azure function app that was created earlier open a new tab in your browser and paste it there https://reggie-azure-function-app-calculator.azurewebsites.net/api/sum?code=FZz8cl_znbvmnlIjhmHcKSwm-djw6ZqbLz_NmngVSVipAzFu4iAKgQ== then add &x=60&y=80 to it. e.g https://reggie-azure-function-app-calculator.azurewebsites.net/api/sum?code=FZz8cl_znbvmnlIjhmHcKSwm-djw6ZqbLz_NmngVSVipAzFu4iAKgQ==&x=60&y=80
- To verify it is working your browser will display 140 which is the total sum of 60+80
- Thanks for reading
