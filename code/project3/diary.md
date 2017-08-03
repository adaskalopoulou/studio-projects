How many webpages for lego fans?

How can I fill the whole width of the screen in .md files?

Employees ==> converted to full-time employees

---------

marcel [4:47 PM] 
@jsoma @kromreig @jagerhartman i have a df of events and two columns telling me by which company an event in hosted: one column with a company id and one with its name. there are a few names that are not unique so two or three companies have the same name (but not the same id).

how do i get only the companies with a non-unique name? i tried so many things with double groupbys and value_counts … i’m not even sure what to google for …


jagerhartman [4:49 PM] 
What is your criteria for same name?  Exact same string?  You could value counts and create a series of 1's and 0's by having "df['company name'].value_counts() < 2" ( or <= 1) Then use that to subset the rows of your df


marcel [4:51 PM] 
exact same string. in the df each row is an event. each company hosts multiple events. so a simple value_counts wouldn’t do it, would it? (edited)


new messages
marcel [5:36 PM] 
got it:
```df.groupby(['name', 'id']).count().reset_index()['name'].value_counts()```

---------
