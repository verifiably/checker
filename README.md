# Verifiably Checker

This library offers an easy way to verify the results sent by a vfunction. For more details about the process visit the [Attestation Documentation](https://developer.verifiably.com/docs/vfunctions/attestation).

## Installation
To install this library run:

```
pip install verifiably_checker
```

## Example

Once you receive your vfunction results you can easily verify and get the signed values.

``` python
from verifiably_checker import attestation

expected_pcrs = {
    "0":"8ab74c11916303460eb92a8aced8156a2f435cbbaf7bf2e4b62dbcb05781daa3b315f28a333c9e4ff2d36f6b56f241f4"
}

results_file = 'result_att_doc.txt'

with open(results_file, 'r') as f:
    vfunctions_results = f.read()

if attestation.verify_attestation_doc(vfunctions_results, expected_pcrs):
    user_data = attestation.get_user_data(vfunctions_results)

print(user_data)
```
