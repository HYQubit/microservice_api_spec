## Quantum Circuit

To perform a quantum circuit calculation, you create a `circuit` object.
You can receive the desired result of the circuit once the task is done.


| ENDPOINTS    |
| ---- |
| [POST /circuit](#create-the-circuit)    |
| [GET  /circuit/:id/status](#retrieve-the-circuit-status)    |
| [GET  /circuit/:id/result](#retrieve-the-circuit-result)    |

### The circuit object

#### Attributes


**qubits** `array of hashes`   (Required)

Detailed breakdown of qubits in the circuits.

`child attributes`

- qubits.**name** `string` 
  
  Name of the qubit
  

**moments** `2d array of hashes`   (Required)

[TODO] 添加说明


### Create the circuit

[TODO] 添加说明


### Retrieve the circuit status

[TODO] 添加说明

### Retrieve the circuit result

[TODO] 添加说明


