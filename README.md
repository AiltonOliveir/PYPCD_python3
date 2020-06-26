# PYPCD_python3
This repository is a **version** of https://github.com/dimatura/pypcd for Python 3. If you want, visit the original project.

### What is the PYPCD ?:
Pure Python module to read and write point clouds stored in the PCD file format, used by the Point Cloud Library.

### Example 1:
```python
from pypcd import pypcd
# also can read from file handles.
pc = pypcd.PointCloud.from_path('foo.pcd')
# pc.pc_data has the data as a structured array
# pc.fields, pc.count, etc have the metadata

# center the x field
pc.pc_data['x'] -= pc.pc_data['x'].mean()

# save as binary compressed
pc.save_pcd('bar.pcd', compression='binary_compressed')
```

```python
from pypcd import pypcd
...
pcd_path = tmpdir + '/' + vehicle[0] + '.pcd'
pc = pypcd.PointCloud.from_path(pcd_path)

#Filter1 : Removing Floor 
ind = np.where(pc.pc_data['z'] > 0.2)
fCloud = pc.pc_data[ind]
tmpCloud = [[i['x'], i['y'], i['z']] for i in fCloud]
```

### Full code example:
You can consulte a full code example [here](https://github.com/AiltonOliveir/ITU-Challenge-ML5G-PHY/tree/master/Customized_frontend).
The simulation scenario is vehicle mobility in the urban environment.

### Improvements and changes:
Feel free to submit a pull request, this version was made for personal use, but i intend to provide support even as possible!

### Original documentation:
[Here](https://pypi.org/project/pypcd/)
