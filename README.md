Initialize PDBMine analysis object:

```
from lib import MultiWindowQuery
da = MultiWindowQuery(pdb_code, [4,5,6,7], PDBMINE_URL, PROJECT_DIR)
```

- `PDBMINE_URL` should point to a running PDBMine process
- 4, 5, 6, and 7 determines what window sizes to use in future PDBMine queries


Compute `phi` and `psi` angles from `.PDB` file
```
da.compute_structures()
```
- this generates `PROJECT_DIR/xray_phi_psi.csv`

Query PDBMine with chosen window sizes (one query for each)
```
da.query_pdbmine
```
- this generates 8 files: `PROJECT_DIR/phi_psi_mined_win[4-7].csv` and `PROJECT_DIR/phi_psi_mined_window_win[4-7].csv`


Perform analysis of protein using library. Several examples are shown in `paper_plots.ipynb`. Once the above files are generates, they can be loaded at any time with `da.load_results()`

