# AB_Hypothesis
Dropping a non-matching rows

One of the main points in AB testing exercise is to clean the data, and I have stumbled with the below code that needs a bit of explanation

- In the A/B test worksheet we have two columns 'group' and 'landing_page'
- Under 'group' we have treatment and control
- Under 'landing_page' we have old_page and new_page


## Technoligy needed:
Pythom


## The requirement
Drop the non-matching rows 
- 'treatement' should match new_page & 'control' should match old_page

## The code used

````

droprows = list(df[((df['group'] == 'treatment') == (df['landing_page'] == 'new_page')) == False].index)
df2 = df.drop(droprows)

````


The above code had cleaned the non matching rows including the control group ones
**My question is: how did this code clean up the unmatching rows while we did not include the control and/or old_page ?**




