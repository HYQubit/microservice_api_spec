## Quantum Circuit

To perform a quantum circuit calculation, you commit a `circuit` object.
You can receive the desired result of the circuit once the task is done.


| ENDPOINTS    |
| ---- |
| [POST /circuit](#commit-the-circuit)    |
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


### Commit the circuit

To perform a quantum circuit calculation, you commit a `circuit` object.
You will receive a circuit id to retrieve the calculation result.

#### Body parameters

**circuit** `circuit object`   (Required)

The [circuit object](#the-circuit-object) to commit.

#### Returns

Returns the circuit id if succeeded. 
This call will return an error if something goes wrong.
A common source of error is an invalid format of committed circuit.

#### Code samples

```bash
# POST /circuit
curl \
  -X POST \
  http://<ip>:<port>/circuit \
  -d '{"circuit": { "qubits": [...], "moments": [[...], [...], ...] }}'
```

#### Example Response

```json
{
  "circuit_id": "6dcb09b5b57875f334f61aebed695e2e4193db5e"
}
```

### Retrieve the circuit status

[TODO] 添加说明

### Retrieve the circuit result

[TODO] 添加说明


