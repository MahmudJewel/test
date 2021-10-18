# Handling multiple submit buttons on django form
## i) Method-1
```
if request.method=='POST':
	if 'Lower' in request.POST:
            	pass
	elif 'Upper' in request.POST:
           	pass
``` 
Where 'Lower' and 'Upper' is the submit button’s name

## ii) Method-2
```
def clean(self):
	if 'Lower' in self.data:
            		pass
	elif 'Upper' in self.data:
           		pass
```
# Example:

## html file
```
<form method="POST" > 
	{% csrf_token %}
          <button class="btn btn-primary" type="submit" name='Upper'>Upper Case</button>
          <button class="btn btn-primary" type="submit" name='Lower'>Lower Case</button>
 </form>
```


## views file
```
def home(request):
    if request.method=='POST':
        #Code
        if 'Lower' in request.POST:
            #Code
        elif 'Upper' in request.POST:
           #Code
```
