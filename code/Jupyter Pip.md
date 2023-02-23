## Pip install inside Jupyter

Jupyter notebook manages a separate python virtual environment.
To install packages inside this venv, do the following:

```python
import sys
!{sys.executable} -m pip install pandas
```