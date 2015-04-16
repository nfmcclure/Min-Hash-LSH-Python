import os
import numpy as np
import string

# Generate sample texts
t1 = 'Financial Analyst Job Responsibilities:Analyzes financial status by collecting, monitoring, ' +\
'and studying data; recommending actions. Financial Analyst Job Duties: Determines cost of operations ' +\
'by establishing standard costs; collecting operational data. Identifies financial status by comparing ' +\
'and analyzing actual results with plans and forecasts. Guides cost analysis process by establishing ' +\
'and enforcing policies and procedures; providing trends and forecasts; explaining processes and ' +\
'techniques; recommending actions. Improves financial status by analyzing results; monitoring variances; ' +\
'identifying trends; recommending actions to management. Reconciles transactions by comparing and correcting data.'
t2 = t1
t3 = 'Analyst Job Responsibilities. Analyzes financial status by collecting monitoring ' +\
'and studying data; recommending actions. Financial Analyst Job Duties: Determines cost of operations ' +\
'by establishing standard costs collecting operational data. Identifies financial status by comparing ' +\
'and analyzing actual results with plans and forecasts. Guides cost analysis process by establishing ' +\
'and enforcing policies and procedures; providing trends and forecasts; explaining processes and ' +\
'techniques; recommending actions. Improves financial status by analyzing results; monitoring variances; ' +\
'identifying trends; recommending actions to management. Reconciles transactions by comparing and correcting data.'
t4 = 'Financial Analyst Job Responsibilities:Analyzes financial status by collecting, monitoring, ' +\
'and studying data; recommending actions. Financial Analyst Job Duties: Determines cost of operations ' +\
'by establishing standard costs; collecting data. Identifies financial status by comparing ' +\
'and analyzing actual results with plans and forecasts. Guides cost analysis process by establishing ' +\
'and enforcing policies and procedures; providing trends and forecasts; explaining processes and ' +\
'techniques; recommending actions. Improves financial status by analyzing results; monitoring variances; ' +\
'identifying trends; recommending actions to management. Reconciles transactions by comparing and correcting data.' +\
'Analyzes financial status by collecting, monitoring, ' +\
'and studying data; recommending actions. Financial Analyst Job Duties: Determines cost of operations ' +\
'by establishing standard costs; collecting operational data. Identifies financial status by comparing '
t5 = 'Firefighter Job Responsibilities: Protects citizens by extinguishing fires; executing rescues. ' +\
'Firefighter Job Duties: Prevents fire damage by conducting surveys and inspections for hazards; enforcing codes. ' +\
'Prepares citizens to prevent fire damage by developing and conducting educational and training programs. ' +\
'Ensures availability of water at fire scene by testing hydrants; requesting and expediting repairs; verifying repair. ' +\
'Minimizes fire damage by responding to alarms; driving and operating equipment; regulating water pressure; ' +\
'Ensures operation of equipment by completing preventive maintenance requirements; following manufacturers ' +\
'Maintains operations by following policies and procedures; reporting needed changes. '

texts = [t1, t2, t3, t4, t5]

# Define Shingling function
def shingle(s, l):
    #Generate k-tuple shingles of a string
    l = min(len(s), l)
    return([s[i:i+l] for i in range(len(s) - l + 1)])
    
# Declare punctuation
exclude = set(string.punctuation)

# Generate hash functions
def hash_functions():
    def hash_factory(ni):
        return(lambda x: hash("salt" + str(ni) + str(x) + "salt"))
    return [hash_factory(i) for i in range(n)]

# Create list of shingle lists and Normalize text
shingle_list = [shingle(''.join(ch for ch in d.lower().replace(' ','') if ch not in exclude),4) for d in texts]

# Generate LSH matrix
[[min(fn(t) for t in tuples) for i, fn in enumerate(hash_functions())] for tuples in shingle_list]
