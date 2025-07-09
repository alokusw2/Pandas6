# Pandas6

1 Problem 1 : Delete Duplicate Emails ( https://leetcode.com/problems/delete-duplicate-emails/)
-----------------------------------------------

Write a solution to delete all duplicate emails, keeping only one unique email with the smallest id.

For SQL users, please note that you are supposed to write a DELETE statement and not a SELECT one.

For Pandas users, please note that you are supposed to modify Person in place.

After running your script, the answer shown is the Person table. The driver will first compile and run your piece of code and then show the Person table. The final order of the Person table does not matter.

The result format is in the following example.

 

------------------------------------------------
import pandas as pd

def delete_duplicate_emails(person: pd.DataFrame) -> pd.DataFrame:
    return person.sort_values('id').drop_duplicates(subset='email', keep='first')



------------------------------------------------


2 Problem 2 : The Number of Rich Customers ( https://leetcode.com/problems/the-number-of-rich-customers/ )
-----------------------------------------------
Write a solution to report the number of customers who had at least one bill with an amount strictly greater than 500.

The result format is in the following example.


------------------------------------------------

import pandas as pd

def rich_customers(store: pd.DataFrame) -> pd.DataFrame:
    return pd.DataFrame({
        'rich_count': [store[store['amount'] > 500].drop_duplicates(subset='customer_id').shape[0]]
    })

------------------------------------------------


