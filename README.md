import sys
import numpy as np

# Python list
py_list = [1] * 1_000_000
py_size = sys.getsizeof(py_list[0]) * len(py_list)

# NumPy array
np_array = np.ones(1_000_000, dtype=np.int64)
np_size = np_array.nbytes

print(f"Python List Size: {py_size / 1e6:.2f} MB")
print(f"NumPy Array Size: {np_size / 1e6:.2f} MB")


import time

size = 1_000_000

# Python list multiplication
py_list = list(range(size))
start = time.time()
py_result = [x * 2 for x in py_list]
print(f"Python List Time: {time.time() - start:.6f} sec")

# NumPy array multiplication
np_array = np.arange(size)
start = time.time()
np_result = np_array * 2
print(f"NumPy Time: {time.time() - start:.6f} sec")
