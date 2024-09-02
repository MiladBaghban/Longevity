
Example: Read the date and time of the user's birth in a desired format from the input 
         string, and then calculate the total number of seconds that have passed in his 
         life and print it for him in the output. <br />
<br />
Solution: 
    
<pre>import re     # library of python for calculate the calculation of below <br />
from datetime import datetime

def calculate_seconds_since_birth(birth_date, current_date):
    birth_datetime = datetime.strptime(birth_date, '%Y-%m-%d %H:%M:%S')
    current_datetime = datetime.strptime(current_date, '%Y-%m-%d %H:%M:%S')
    time_difference = current_datetime - birth_datetime
    total_seconds = time_difference.total_seconds()
    
    return total_seconds

birth_date = input("please enter your birth time (with format YYYY-MM-DD HH:MM:SS): ")
current_date = datetime.now().strftime('%Y-%m-%d %H:%M:%S')
total_seconds = calculate_seconds_since_birth(birth_date, current_date)

print("The total number of seconds since you were born: ", total_seconds, "second")
