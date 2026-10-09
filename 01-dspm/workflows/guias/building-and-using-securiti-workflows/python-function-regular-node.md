---
title: "Python Function"
slug: "python-function-regular-node"
updated: 2025-10-30T19:07:24Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/python-function-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Python Function

A Python Function node in a Workflow allows you to execute custom Python scripts within the Workflow. The node allows you to insert custom Python logic directly into the Workflow. This can be used to transform data, filter items, perform calculations, integrate with custom APIs, or any other logic that Python supports.

The node receives data from the preceding node in the Workflow. This data can be in the form of individual items, lists, JSON objects, or other formats. The node supports the following modes:

- **Run Once for All Items**: This is the default mode. When your Workflow runs, the code in the code node executes once, regardless of how many input items there are.
- **Run Once for Each Item:** This mode runs your code for every input item.

> [!NOTE]
> **Note**
> 
> The Python function node is supported with the Restricted Python library.

Refer to the node configuration section to understand the node working and properties.

#### Prerequisites

Please refer to the special case considerations section to understand the special considerations while using the node.

#### Example use case

As an example, let’s create a Workflow that processes a list of assets using the **Assets node** each of which has various properties, including a vendor field. You want to maintain a list of assets provided by Google Cloud Storage out of the list of assets produced. The **Python Function node** filters out the required assets and then writes them to a file using the **Spreadsheet File node**.

The following Nodes are used in this use case:

1. [Assets node](/v1/docs/asset)
2. Python Function node
3. [Spreadsheet File node](/v1/docs/spreadsheet-file)

#### Filtering assets by vendor using a Python Function node

1. Use the Assets node to list all the assets in the system.
2. Attach the Python function node to execute a script to filter out the assets based on the vendor field. This node:

![Screenshot_2024-08-01_at_1_25_35_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0a848f2f-7cec-887b-755f-0cad9baa68dd.png)
  - Iterates through each asset.
  - Checks if the **vendor** field equals **google_cloud_storage**.
  - Collects all matching assets into a new list.
3. Connect the Spreadsheet file node to write the assets to a spreadsheet file for further processing.
4. Connect the Nodes and execute the Workflow.

![Screenshot_2024-08-01_at_1_25_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-36049f63-6f1f-87d4-ce2a-efaf8caa8447.png)
5. Upon successful execution, the Workflow Node will provide a successful response. After the Workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

![Screenshot_2024-08-01_at_1_24_52_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8865c9d6-192f-17da-4218-16146059232a.png)

![Screenshot_2025-01-07_at_1_40_35_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6c961507-2563-417f-2566-2f7c171b97b3.png)

#### Node configurations

| Parameters | Description |
| --- | --- |
| Mode | Run once for all items | Choose this mode for the code in the node to execute once, regardless of how many input items there are. |
| Run once for each item | Choose this mode for the code to execute for each item individually. |
| Python Code | Add the Python code to execute. > [!NOTE] > **Note** > > Please note that the node is supported with the Restricted python library. |

#### Special considerations

1. With RestrictedPython library implementation, the following set of functions is supported using the Python Function node:
  - 'random': random
  - 'math': utility_builtins['math']
  - 'reduce': reduce
  - 'itertools': itertools
  - 'lru_cache': lru_cache
  - 'cmp_to_key': cmp_to_key
  - 'json': json
  - 'partial': partial
  - 'textwrap': textwrap
  - 'Counter': Counter
  - 'deque': deque
  - 'defaultdict': defaultdict
  - 'namedtuple': namedtuple
  - 'OrderedDict': OrderedDict
  - 'ChainMap': ChainMap
  - 'copy': copy
  - 'calendar': calendar
  - 'pandas': pandas
  - 'numpy': numpy
  - 'filterfalse': filterfalse
  - 'datetime': datetime
  - 'date': date
  - 'timedelta': timedelta
  - 'pytz': pytz, #timezone
  - 'time': time
  - 'id': id
  - 'sum': sum
  - 'abs': abs
  - 'max': max
  - 'min': min
  - 'round': round
  - 'divmod': divmod
  - 'int': int
  - 'float': float
  - 'bool': bool
  - 'str': str
  - 'list': list
  - 'filter': filter
  - 'tuple': tuple
  - 'set': set
  - 'dict': dict
  - 'len': len
  - 'range': range
  - 'enumerate': enumerate
  - 'sorted': sorted
  - 'any': any
  - 'all': all
  - 'getattr': getattr
  - 'isinstance': isinstance
  - 'type': type
  - 'array': array
  - 'map': map
2. Commonly used keywords such as `print`, `class` or `import` are also not allowed.
3. For the **Run once for each item** mode, the input is required for the below code to run as an array:

```plaintext
def execute(items):    
results = []    
# Basic math operations
results.append({"description": "Sum", "value": sum([1, 2, 3, 4])})    
results.append({"description": "Absolute value", "value": abs(-5)})    
results.append({"description": "Max value", "value": max([1, 2, 3, 4])})    
results.append({"description": "Min value", "value": min([1, 2, 3, 4])})    
results.append({"description": "Rounded value", "value": round(3.14159, 2)})    
results.append({"description": "Divmod", "value": divmod(10, 3)})    
# Type conversions    
results.append({"description": "Integer", "value": int("10")})    
results.append({"description": "Float", "value": float("10.5")})    
results.append({"description": "Boolean", "value": bool(1)})    
results.append({"description": "String", "value": str(100)})    
# List operations    my_list = [1, 2, 3, 4, 5]    
results.append({"description": "Length of list", "value": len(my_list)})    
results.append({"description": "Range", "value": list(range(5))})    
results.append({"description": "Enumerate", "value": list(enumerate(my_list))})    
results.append({"description": "Sorted list", "value": sorted(my_list, reverse=True)})    
results.append({"description": "Any true", "value": any([0, 0, 1])})    
results.append({"description": "All true", "value": all([1, 1, 1])})    
# Dictionary operations    my_dict = {'a': 1, 'b': 2, 'c': 3}    
results.append({"description": "Get attribute", "value": getattr(my_dict, 'get')('a')})    
results.append({"description": "Is instance", "value": isinstance(my_dict, dict)})    
results.append({"description": "Type", "value": type(my_dict).__name__})    
# Data structures    
MyTuple = namedtuple('MyTuple', 'x y')    t = MyTuple(10, 20)    
results.append({"description": "Named tuple", "value": t})    
my_counter = Counter([1, 2, 2, 3, 3, 3])    
results.append({"description": "Counter", "value": my_counter})    
my_deque = deque([1, 2, 3])    
my_deque.appendleft(0)    
results.append({"description": "Deque", "value": list(my_deque)})    
my_defaultdict = defaultdict(int)    
my_defaultdict['a'] += 1    
results.append({"description": "Defaultdict", "value": dict(my_defaultdict)})    
my_ordereddict = OrderedDict([('a', 1), ('b', 2)])    
results.append({"description": "OrderedDict", "value": my_ordereddict})    
my_chainmap = ChainMap({'a': 1}, {'b': 2})    
results.append({"description": "ChainMap", "value": dict(my_chainmap)})    
# Copy    
original = [1, 2, 3]    
copy_of_original = copy.deepcopy(original)    
results.append({"description": "Deep copy", "value": copy_of_original})    
# Calendar    
cal = calendar.month(2024, 7)    
results.append({"description": "Calendar", "value": cal})    
# Pandas and Numpy    
df = pandas.DataFrame(numpy.random.rand(5, 3), columns=['A', 'B', 'C'])    
results.append({"description": "DataFrame", "value": df.to_string()})    
array = numpy.array([1, 2, 3])    
results.append({"description": "Numpy array", "value": array.tolist()})    
# Date and time    
now = datetime.now(pytz.timezone('UTC'))    
results.append({"description": "Current time (UTC)", "value": now.isoformat()})    
delta = timedelta(days=5)    
future_date = now + delta    
results.append({"description": "Future date", "value": future_date.isoformat()})    
# Random    
random_number = random.randint(1, 10)    
results.append({"description": "Random number", "value": random_number})    
# Math    
results.append({"description": "Square root", "value": math.sqrt(16)})    
# Itertools    
combined = list(itertools.chain([1, 2], [3, 4]))    
results.append({"description": "Itertools chain", "value": combined})    
# Functional tools    
def add(x, y): return x + y    
reduced_value = reduce(add, [1, 2, 3, 4])    
results.append({"description": "Reduced value", "value": reduced_value})    
@lru_cache(maxsize=32)    
def cached_function(x):        
return x * x    
results.append({"description": "Cached function", "value": cached_function(4)})    
partially_applied = partial(add, 1)    
results.append({"description": "Partially applied function", "value": partially_applied(5)})    
# JSON    
json_data = json.dumps({'key': 'value'})    
results.append({"description": "JSON data", "value": json_data})    
# Textwrap    
wrapped_text = textwrap.fill("This is a long line that needs to be wrapped.", width=20)    
results.append({"description": "Wrapped text", "value": wrapped_text})    
return [{"json": result} for result in results]
# Run the test 
scriptitems = []  # Assuming items is an empty list as per the provided 
example
output = execute(items)
return output[item['json']['myVariable']]
```

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
