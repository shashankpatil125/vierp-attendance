import requests
import json

headers = {
    'EPS-loginid': '38360',
    'EPS-learnerid': '30899',
}

url = 'https://learnerapi.vierp.in/AppLearnerAcademics/learnerAttendenceTable'

payload={
   'attendance': '55.56%',
    'batchid': '836977'
}

response = requests.post(url, headers=headers, json=payload)
response=response.json()
data_dict = json.dumps(response)
temp=json.loads(data_dict)
info = temp['learner']
attendance = temp['crs_list']
print("Course : ", info.get('course_name'))
print("Instructor : ", info.get('instructor_name'))
print("Present : ", info.get('total_present'))
print("Cunducted : ", info.get('total_conducted'))
print("Overall : ", info.get('attendance'))
print("++================|==============++")
print("||     Date       |     Status   ||")
print("++================|==============++")

for i in range(8):
    if(attendance[i].get('attendence')==True):
        print("|  ",attendance[i].get('date'),"  |     true      |")
    else:
        print("|  ",attendance[i].get('date'),"  |     false     |")
    print("+-----------------|---------------+")
