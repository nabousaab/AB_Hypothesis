# AB_Hypothesis
Dropping non-matching lrows


> In the A/B test worksheet we have two columns 'group' and 'landing_page'
> Under 'group' we have treatment and control
> Under 'landing_page' we have old_page and new_page

**The requirement**
Drop the non-matching rows 
- 'treatement' should match new_page & 'control' should match old_page

**The code used**

````

droprows = list(df[((df['group'] == 'treatment') == (df['landing_page'] == 'new_page')) == False].index)
df2 = df.drop(droprows)

```

The above code had cleaned the non matching rows
**how did this code clean up the unmatching rows while we did not include the control and/or old_page**




