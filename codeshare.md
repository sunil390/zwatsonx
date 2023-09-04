gradio ansible
```py
import gradio as gr
import subprocess

def my_function(username, password):
    if username == "admin" and password == "pass1234":
        return True
    else:
        return False

app = gr.Interface(my_function, auth=("admin", "pass1234"))
app.launch()

def call_ansible_playbook(playbook_path):
    try:
        output = subprocess.check_output(["ansible-playbook", playbook_path])
        return output.decode("utf-8")
    except Exception as e:
        return str(e)

interface = gr.Interface(
    fn=call_ansible_playbook,
    inputs="text",
    outputs="text",
    label="Call Ansible playbook",
)

interface.launch()
```

hfstarcoder
```py
import requests
import json

API_URL = "https://api-inference.huggingface.co/models/bigcode/starcoder"
headers = {"Authorization": "Bearer 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"}

def query(payload):
	response = requests.post(API_URL, headers=headers, json=payload)
	return response.json()
	
output = query({
	"inputs": "I am in bangalore and i would like to "
})

print( json.dumps(output, indent=2 ) )
```

palm2one

```py
import google.generativeai as palm
import os
palm.configure(api_key=os.environ['PALM_API_KEY'])

#response = palm.generate_text(prompt="The opposite of hot is")
#print(response.result) #  'cold.'

prompt = """
You are an expert mainframe systems programmer.

Solve the following problem:

IDC3009I message with return code  8 reason code 42

Think about it step by step, and show your work.
"""

completion = palm.generate_text(
    model='models/text-bison-001',
    prompt=prompt,
    temperature=0,
    # The maximum length of the response
    max_output_tokens=800,
)

print(completion.result)

#import pprint
#for model in palm.list_models():
#    pprint.pprint(model)
```
watsonai

```py
from ibm_watson_machine_learning.foundation_models.utils.enums import ModelTypes
from ibm_watson_machine_learning.foundation_models import Model
import json
import os

my_credentials = { 
    "url"    : "https://us-south.ml.cloud.ibm.com", 
    "apikey" : os.environ['WATSON_API_KEY']
}      

model_id    = ModelTypes.FLAN_T5_XXL
gen_parms   = None
project_id  = "5743028f-61df-4358-bc88-101d812b200a"
space_id    = None
verify      = False

model = Model( model_id, my_credentials, gen_parms, project_id, space_id, verify )   
 
prompt_txt = "In today's sales meeting, we "
gen_parms_override = None

generated_response = model.generate( prompt_txt, gen_parms_override )

print( json.dumps( generated_response, indent=2 ) )

```
