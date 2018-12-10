# Banking

## Objects

### Step (A step might be a string with the path to a json file representing a step object)
| Key | Type | Description | Optional | Default Value |
| :---: | :---: | :---: | :---: | :---: |
| type | String | The type of the step. See below for options. | no | - |
| nextStep | Step | The step to take after this one has been evaluated. This does wait for asyncronious tasks to complete. | yes | - |

The type values are appended to the step object.

#### Types

##### request

| Key | Type | Description | Optional | Default Value |
| :---: | :---: | :---: | :---: | :---: |
| url | String | The url. | no | - |
| method | String | The HTTP method. | yes | GET |
| resultVariable | String | The state variable to put the result in. | yes | result |
| onSuccess | Step | The step when the url request is successful. | yes | - |
| onFailure | Step | The step when the url request is not successful. | yes | - |

##### regex

| Key | Type | Description | Optional | Default Value |
| :---: | :---: | :---: | :---: | :---: |
| variable | String | The variable to apply the regular expression to. | no | - |
| expression | String | The expression. | no | - |
| resultVariable | String | The state variable to put the result in. This will contain an array of arrays containing all group data  | yes | result |
| onSuccess | Step | The step when the regex is successful. | yes | - |
| onFailure | Step | The step when the regex is not successful. | yes | - |

##### iterate

| Key | Type | Description | Optional | Default Value |
| :---: | :---: | :---: | :---: | :---: |
| variable | String | The variable of the array to iterate through. | no | - |
| resultVariable | String | The variable name of the iterated item. | no | - |
| step | Step | The step to take for each iteration. | no | - |
| onCompletion | Step | The step to take after all iterations. | no | - |

##### requireInputs

| Key | Type | Description | Optional | Default Value |
| :---: | :---: | :---: | :---: | :---: |
| variable | String | The variable of the array to iterate through. | no | - |
| inputs | Array[Input] | The inputs to require. | no | - |
| onSuccess | Step | The step when requiring is successful. | yes | - |
| onFailure | Step | The step when requiring is not successful. | yes | - |

##### deletion

| Key | Type | Description | Optional | Default Value |
| :---: | :---: | :---: | :---: | :---: |
| variable | String | The variable to delete. | no | - |

##### alert

| Key | Type | Description | Optional | Default Value |
| :---: | :---: | :---: | :---: | :---: |
| text | String | The alert to show. | no | - |

##### abort

Aborts the entire opertaion.

##### complete

Completes the entire opertaion.

### Input

| Key | Type | Description | Optional | Default Value |
| :---: | :---: | :---: | :---: | :---: |
| name | String | The name of the variable. | no | - |
| title | String | The title to display. | no | - |
| isPassword | Boolean | Whether the input represents a password. | yes | false |
| shouldSave | Boolean | Whether the input should be saved. | yes | false |
