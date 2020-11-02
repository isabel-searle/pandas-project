# data-cleaning-pandas

The more challangable part of the project has been the cleaning process.

Even if I have spent hours I feel the .csv is still a big mess.

First of all I checked all the columns and I realized I had a lot of messy and missing information. I could see that there was some cases not  really representative, with poor information so I decided to remove 14 columns.

Later with the years, I could understand that there were very old cases with a lot of missing data, so that I decided to analyse from 1950. 


Where I have spent more time with no success and I gave up was trying to clean the date column. You can see some of the ways I tried to clean it. So I created a new column that I filled with the following function:
```
def months_column(x,y):
    df_clean["MONTH"] = np.where(df_clean["DATE"].str.contains(x), y, df_clean["MONTH"])
```
The problem with this function is that I have to run it once in this way:
```
df_clean["MONTH"] = np.where(df_clean["DATE"].str.contains("Jan"), "Jan", df_clean["DATE"])
```
And then, use the function in order avoid rewriting data.


Finally I just tried to clean every column in the same way, by finding some strings in them, changing the category names and making it more homogeneous, with less types of categories. 

I clean some columns that later I didn't use. But I didn't what I was dealing with.

I had many different issues. For example the one I made a screenshot "stranger_thing.png". Still I don't understand why is not working.

I've been all the weekend stuck with the cleaning process. So the analysis will be a bite poor.

The data in some countries is not comparable with others. Then I'm going to analyse those countries with higher number of attacks (Australia and USA)


These are some functions that I couldn't use properly:

```
def month_clean():
    months=["Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"]
    for i in months:
        if re.search(i,df_clean["MONTH"]):
            return i
        else:
            return unknown


python
def cleaning_months(*x):
    months = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']
    for i in x:
        if i in months:
            i=i
        else:
            i="unknown"


df_clean["MONTH"]=df_clean["MONTH"].apply(cleaning_months)


df_clean["DATE_CLEAN"]=datetime.datetime.strptime(df_clean["DATE"],'%d-%b-%Y').strftime('%Y-%m-%d')
m = df % 3 == 0
df.where(m, -df)
df_clean["Months"] = np.where(df_clean["Date"].str.contains(x), y, df_clean["Date"])

def date_clean():
    for i in x:
        try:
            i.split("-")
        except

type(df_clean["DATE"])

df['Date'].str.extract(r'^(\d{4})', expand=False)


```