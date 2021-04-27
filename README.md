<br><h1 style="font-family:COMIC SANS;text-align:center;background-color:lightpink" ><b>📑Table of Contents📑</b></h1><br>
<font size=3 color="black" style="font-family:COMIC SANS MS" ><i>

🤷‍[Purpose of Analysis](#Purpose-of-Analysis)<br>
🌐 [Basic Pandas functions](#Basic-Pandas-functions)<br>
📖 [Reading Dataset](#Reading-Data) <br>
👀 [Exploring Dataset](#Exploring-Dataset)<br>
🎭 [Converting Datatypes](#Converting-Datatypes) <br>
🩸 [Add/Rename/Drop/Filter Columns](#Add-Rename-Drop-Filter-Columns)<br>
❓ [Missing Values](#Missing-Values) <br>
📄 [Descriptive Statistics](#Descriptive-Statistics)<br>
🔪 [Slicing/Subsetting](#Slicing-Subsetting)<br> 
👨‍👨‍👯‍[Data Aggregation ,Combining data frame and Groupby](#Data-Aggregation-dataframe-and-Groupby)<br>

<h1 style="font-family:COMIC SANS ;text-align:center;background-color:lightpink"><b>🤷‍ Purpose of Analysis 🤷‍</b></h1>
#Purpose of Analysis
<font size=3 style="font-family:COMIC SANS MS" ><b><i>The biggest motivation for this notebook was a simple thought to get better at Pandas.The best way to learn or improve is to write about it .With this thought process, I have created a simple tutorial along with a Case study on a Youtube trending Dataset to provide examples how these Panda functions can be used during analysis.
Questions which I want to answer with this analysis :
    
- Which is most watched video in India. ❓(Most watch doesnot mean trending)
- Number of videos published in 2021❓<br>
- How many videos did T-Series publish ❓<br>
- Top 30 videos that has been most watched❓<br>
- Top 3 Categories having maximum pubished videos in 2020❓<br>
- Top 10 Most liked videos in India❓
</i></b></font>
#Reading Data
<font size=3 style="font-family:COMIC SANS MS" style="font-family:COMIC SANS MS" ><b><i><u> Getting  Dataset: 🧧</u></i></b></font>

<table style ="width:100%;border:black;border-width:1px; border- style:solid;  border-collapse: collapse" >
  <thead>
    <tr>
      <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px "> 
              To Read  Dataset From 
      </th>
      <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">
              Method
      </th>
      </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
              CSV&nbsp;
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
              pd.read_csv(filename)
            </td>
        </tr>
        <tr >
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
              TAB/Delimited /TSV
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
              pd.read_table(filename)
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
             EXCEL
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
             d.read_excel('myfile.xlsx',sheet_name='Sheet1', index_col=None)
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
             SQL Table
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
             pd.read_sql(query,connection_object)
            </td>
        </tr>
        <tr >
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
             JSON formatted string<
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                pd.read_json(json_string)
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                HTML url
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                pd.read_html(url)
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                Clipboard
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                pd.read_clipboard()
            </td>
        </tr>
    </tbody>
</table><br>
<font size=3 style="font-family:COMIC SANS MS" style="font-family:COMIC SANS MS" ><b><i> <u>Analyzing Dataset🔭🔭</u> :
When you begin working with a new data set, it is  best to check out the first few rows ,look at datatypes, 
check for any datatype mismatch in variables. This will show you what kind of data is in the dataset, 
what data types you are working with, and help you in your analysis.</i></b></font>

<table style ="width:100%;border:black;border-width:1px; border- style:solid;  border-collapse: collapse" >
  <thead>
    <tr>
        <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">
            Description 
        </th>
        <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">
            Method
      </th>
    </tr>
   </thead>
   <tbody>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                Displays top 5 row or  n rows;</td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_india.head()/df_india.head(n)
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                Displays bottom 5 row or  n rows
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                df_india.tail()/df_india.tail(n)
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                Displays randomly selected rows
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                df_india.sample(n)
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                Selecting  certain columns
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                col=['title','trending_date','view_count']
                df_india[col].head()
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                Select and order top n entries
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_india.nlargest(10, 'view_count')
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                Select and order bottom n entries
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_india.nsmallest(10, 'view_count')
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                Distinct values in a column
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-family:COMIC SANS MS;font-size:100%;padding: 10px">
                df_india['trending_date'].nunique()
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                Count number of rows with each unique value of variable
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                df_india['trending_date'].value_counts()
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                To display datatypes of variables
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                df_india.dtypes 
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                Displays numbers of rows and column our dataset <br>contains.Its a tuple representing the dimensions
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_india.shape 
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                This method print info about a dataset including the index dtype <br>and columns,non-null values and memory usage
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px" >
                df_india.info() 
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                A selection of numeric dtypes  to be included/excluded.
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                df_india.select_dtypes(include = [np.number]).dtypes
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                A selection of object dtypes to be included/excluded. 
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                df_india.select_dtypes(include = [np.object]).dtypes
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                A selection of datetime dtypes to be included/excluded.  
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                df_india.select_dtypes(include =  [np.datetime64]).dtypes
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                To select Pandas categorical dtypes 
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                df_india.select_dtypes(include = 'category').dtypes
            </td>
        </tr>
    </tbody>
</table><br>  
<font size=3 style="font-family:COMIC SANS MS" ><b><i><u>Converting Datatypes 🎭:</u>
        Pandas automatically assign datatype to the columns,depending on what data the columns hold.For eg weight column may have data in form of 60.5kg  so the datatype here would be object. But we want weight to be float . We can remove kg and change data type to float.</i></b></font><br>
<table style ="width:100%;border:black;border-width:1px; border- style:solid;  border-collapse: collapse" >
    <thead>
        <tr>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px "> 
                Description 
            </th>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">
                Method      
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To convert object datatype to categorical datatype 
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px "> 
                 df_india.description=df_india.description.astype("category")
            </td>
        </tr>
         <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To convert object datatype to Integer datatype 
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px "> 
                 df_india.description=df_india.description.astype("int")
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To convert object datatype to float datatype 
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px "> 
                 df['DataFrame Column'] = df['DataFrame Column'].astype(float)
            </td> 
        </tr>    
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To Convert object to datetime datatype
            </td>
           <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >                                                df_india.publishedAt=pd.to_datetime(df_india.publishedAt)
            </td>
        </tr>    
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To make a copy of dataset
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " > 
                df_copy=df_india.copy()
            </td>
        </tr>
    </tbody>
</table> <br>    
 <font size=3 style="font-family:COMIC SANS MS" ><b><i><u>Adding /Renaming/Dropping Columns </u>➕🩸🩸</i></b></font>
        
<table style ="width:100%;border:black;border-width:1px; border- style:solid;  border-collapse: collapse" >
    <thead>
        <tr>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px "> 
                Description 
            </th>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">
                Method      
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To add new columns to a dataframe.
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px "> 
                   df_india['count_max_view'] =df_india.groupby(['video_id'])['view_count'].transform(max)
            </td>
        </tr>
         <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To rename a column
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px "> 
                 df_india.rename(columns={'description':'desc'})
            </td>
        </tr>    
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To drop a column
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " > 
                df_india.drop()
            </td>
        </tr>    
     </tbody>
</table>      <br>
 
<font size=3 style="font-family:COMIC SANS MS"><b><i><u>Descriptive Statistics📄📄</u>   
    Descriptive statistics, which include things like the mean, median,Quartiles,Minimum,Standard Deviation etc of the data , can be useful to understand the spread of the variables are and what variables may be the most important. Descriptive statistics on pandas objects exclude missing data by default</i></b></font><br> 

<table style ="width:100%;border:black;border-width:1px; border- style:solid;  border-collapse: collapse" >
    <thead>
        <tr>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px "> 
                Description 
            </th>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">
                Method
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To get statistical summary for numeric value, to understand the distrubution
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_india.describe()(n)
            </td>
        </tr>    
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To get summary for Categorical value
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px">                                                   df_india.describe(include='category')
            </td>
        </tr>    
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To get Minimum value for all numeric columns
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_india.min()
            </td>
        </tr>    
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To get Mean value for  all numeric columnss
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_india.mean()
            </td>
        </tr>   
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To get exact middle value among a dataset. Useful for skewed distribution or data with outliers
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_india.median()
            </td>
        </tr>   
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To get most frequent element in a dataset.
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_india.mode()
            </td>
        </tr>               
        <tr>   
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To get standard deviation of numeric column
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_india.std()
            </td>
        </tr>               
    </tbody>
</table><br>
<font size=3 style="font-family:COMIC SANS MS">
    <b>
        <i><u>Checking and Handling Missing Values.:❓❓</u>
   .When no data value is stored for feature for a particular observation, we say this feature has a missing value.Missing value handling is a post in itself and will be covered later </i>
    </b>
</font> <br>
<table style ="width:100%;border:black;border-width:1px; border- style:solid;  border-collapse: collapse" >
    <thead>
        <tr>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">                     Description 
            </th>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">                     Method
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                This function returns boolean value indicating whether values are missing (NaN)
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df.isna()
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                 This function check for not null or non-missing values.
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df.notna()
            </td>
        </tr>
        <tr>    
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
               This function is used to replace values with other values dynamically.
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df.Replace()
            </td>
        </tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                This function returns boolean value indicating whether values are missing (NaN)
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                pd.isnull()
            </td>
        <tr>    
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
               This function checks for not null or non-missing values.
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                pd.notnull()
            </td>
        </tr>
        <tr>    
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                This function is used to remove missing value.
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                pd.dropna()
            </td>
        </tr>
        <tr>
             <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
               Return a copy of the data with missing values filled or imputed
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                pd.fillna()
            </td>
         </tr>    
    </tbody>
</table><br>
<font size=3 style="font-family:COMIC SANS MS" ><b><i><u>Slicing /Subsetting  DataSet :🔪🔪</u>
        One of the most effective ways to get more information out of a dataset is to divide it into smaller, 
        more uniform subsets, and analyze each of these "subset" on its own. </i>
    </b>
</font> <br>
        
       
<table style ="width:100%;border:black;border-width:1px; border- style:solid;  border-collapse: collapse" >
    <thead>
        <tr>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">                  Description 
            </th>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px                     ">Method    
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10pxF ">
                To Select rows by position use ilocs .<br>It allows integer-location based indexing for selections .
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                 df_india.iloc[10:4]
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To select data based on labels, which means <br>that we have to specify the name of the rows and columns that we need to filter out
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " >
                 df_india.loc[df_india['title','view_count]]
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                Query the columns of a DataFrame with a boolean expression.
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px " > df_india.query['category == 24']
            </td>
        </tr>
    </tbody>
</table>    <br>
    <font size=3 style="font-family:COMIC SANS MS">
    <b>
    <i><u>
        Data Aggregation,comibing dataframe and Groupby:👯‍♂️👯‍👨‍👨‍👦‍👦</u>
      One of the most basic analysis functions is grouping and aggregating data. An aggregation function is one which takes multiple individual values and returns a summary.In pandas, the groupby function can be combined with one or more aggregation functions to quickly and easily summarize data. 
        </i>
    </b>
</font>  <br>



<table style ="width:100%;border:black;border-width:1px; border- style:solid;  border-collapse: collapse" >
    <thead>
        <tr>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">             Description 
            </th>
            <th style="text-align:center;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;background-color:lightgreen ;padding: 10px ">             Method
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To find total count,unique observatoin
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                agg_func_count = {'view_count': ['count', 'nunique']}<br>
                df_merge.groupby(['category']).agg(agg_func_count)
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To find increased number of likes
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
               agg_func_selection = {'likes': ['first', 'last']} <br>
             df_merge.sort_values(by=['channelTitle'],
            ascending=False).groupby(['channelTitle'
                                        ]).agg(agg_func_selection)
            </td>
        </tr>
        <tr>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To merge category dataset with trending dataset
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
               df_merge = df_india.merge(df_category, on = 'categoryId', how = 'inner')
            </td>
        </tr>
        <tr>    
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                To concatenate Us and canada dataset
            </td>
            <td style="text-align:left;border: 1px solid black;font-family:COMIC SANS MS;font-size:100%;padding: 10px ">
                df_con_us_ca=pd.concat([df_us,df_ca])
            </td>
        </tr>    
    </tbody>
</table>
 
 
