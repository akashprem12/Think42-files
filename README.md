# Think42-files

CASE STUDY:-

This is a test application for real-time data analysis and visulization of student records.

Steps involved in creating the project:-

1. Data collection from UCI ML repository.
2. Understanding the contextual meaning of data.
3. Importing Python libraries and performing Exploratory Data Analysis (EDA).
4. Applying Linear Regression ML Algorithm to check feature coefficients.
5. Using Plot.ly for real time Dashboard Creation.

Now, Objectives to achieve and how I achieved it is as given below:

*Kindly refer "Data.ipynb" notebook file for code execution in python.
*Refer StudentData.csv for database and Attribute info.docx for feature explanation.

Question - Create a real time dashboard for data visualization of student report which gets refreshed 
and updated automatically every 1 hour which a School Principal can view.

Solution - After doing the Exploratory data analysis and applying Machine Learning algorithm, I used Plot.ly 
to create charts. I added those charts to My Dashboards.

*Please download the notebook file (Data.ipynb) on your system.

Now there multpile alternatives to achieve the objective: (P.S. - This is only based upon my research)

1. Create the dashboard in the notebook itself and upload it to the community cloud. 
    *You will need a to register and enter the username and API Key for the same in notebook.
    (plotly.tools.set_credentials_file(username='thecatalyst1210', api_key='Ds8s4Qn3zMlRMXVbBoSJ'))
    
    Libraries being used: :
      plotly.dashboard_objs as dashboard and IPython.display
      These methods are being used in this process: dashboard.Dashboard() and .get_preview()
      
      Now create box plots and upload and insert your data. (dashboard_ops.upload)
      
 
 2. The other way to do is to directly go to Plot.ly website and manually create your plots and add to your dashboards.
    Then you need to find a share-able link for the dashboard and invoke it through your notebook.
    (import webbrowser
      webbrowser.open('https://plot.ly/~thecatalyst1210/0/think42/'))
      
 Now,
 
 How Am I refreshing the database contents after every 1 hour?
 
 -- We need to setup the Database connector on the personal computer (I have used MySQL connector here.) in Plotly.
    Visit for more info: https://help.plot.ly/database-connectors/
    
 -- Then I need to set my data to be updated using peristent queries with Plotly 2.0 and the Plotly Database Connector. 
    Visit : https://help.plot.ly/database-connectors/schedule-query/
    (Your connector will update your data periodically and you have several choices when it comes to the refresh rate of your data. Click on the dropdown above the grid and choose a refresh rate that will be suitable. Here its 1 hour.)
    
    Finally we need to Authorize the connector and schedule the query.
    
    OPEN THE NOTEBOOK FILE AND EXECUTE THE LAST CODE, THE REAL TIME DASHBOARD WILL OPEN AND QUERY HANDLING WILL BE TAKEN CARE OF AUTOMATICALLY.
    
    Link to Dashboard: https://plot.ly/~thecatalyst1210/0/think42/
    
    
  3. Third way is to create visualization Dashboard on Tableau.
     For real time refreshig data we need to use "Schedule Extract Refreshes" in Tableau.
     
     Link for refernces: http://onlinehelp.tableau.com/current/pro/desktop/en-us/help.htm#publish_workbooks_schedules.html
                         https://onlinehelp.tableau.com/current/server/en-us/publish.htm
                         
    
    
      Incremental refreshes reference a column in the extract that has a data type of date, date/time, or integer; such as a timestamp.       Tableau uses this column to identify new rows that need to be added to the extract.
      
      
   4. Final way is a kind of hard-coded way to do this is which needs more of the integration stuff.
      We need to use Ghost.py library of python to periodically run a recurring stuff in notebook.
      For more info: http://ghost-py.readthedocs.io/en/latest/
      
      --Have your script send an HTTP Post request like so. This is the library Requests

      >>> files = {'report.xls': open('report.xls', 'rb')}

      >>> r = requests.post(url, files=files)
      >>> r.text
      then on the receiving side you can use web.py to process the info like this

      x = web.input()
      then do whatever you want with x

      On the receiving side of the POST request import web and write a function that handles the post

for example

    def POST(self):

        x = web.input()
        
        
        
                
  Apart form Python implementation, a separate implementation of R visualization is also provided in "Visualization.R".
  The Shiny framework has been used to create dashboards using Crosstalk library which can be inbuilt as an API or a widget on a webpage.
